<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes">
  <title>小萌AI · 智能安装</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: radial-gradient(circle at 40% 30%, #1a1f35 0%, #0a0d1a 100%);
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
      position: relative;
      overflow-x: hidden;
    }

    /* 动态光效背景 */
    body::before {
      content: "";
      position: fixed;
      top: -20%;
      left: -10%;
      width: 120%;
      height: 120%;
      background: 
        radial-gradient(ellipse at 30% 20%, rgba(99, 102, 241, 0.1) 0%, transparent 50%),
        radial-gradient(ellipse at 70% 70%, rgba(168, 85, 247, 0.08) 0%, transparent 50%),
        radial-gradient(ellipse at 50% 50%, rgba(79, 110, 246, 0.05) 0%, transparent 50%);
      animation: bgShift 15s ease-in-out infinite;
      pointer-events: none;
    }

    @keyframes bgShift {
      0%, 100% { opacity: 0.8; }
      50% { opacity: 1.2; }
    }

    .card {
      max-width: 420px;
      width: 100%;
      background: rgba(255, 255, 255, 0.04);
      backdrop-filter: blur(24px);
      -webkit-backdrop-filter: blur(24px);
      border-radius: 36px;
      padding: 36px 28px 32px;
      box-shadow: 
        0 20px 40px rgba(0, 0, 0, 0.5),
        0 0 0 1px rgba(255, 255, 255, 0.08),
        inset 0 0 0 1px rgba(255, 255, 255, 0.02);
      text-align: center;
      display: flex;
      flex-direction: column;
      gap: 28px;
      position: relative;
      z-index: 1;
      transition: transform 0.05s ease;
    }

    /* AI 生成图片展示 */
    .ai-image-box {
      width: 100%;
      border-radius: 24px;
      overflow: hidden;
      box-shadow: 
        0 12px 30px rgba(0, 0, 0, 0.6),
        0 0 0 1px rgba(255, 255, 255, 0.1),
        0 0 60px rgba(99, 102, 241, 0.15);
      position: relative;
      transition: box-shadow 0.3s ease;
    }

    .ai-image-box:hover {
      box-shadow: 
        0 16px 36px rgba(0, 0, 0, 0.7),
        0 0 0 1px rgba(255, 255, 255, 0.2),
        0 0 80px rgba(99, 102, 241, 0.25);
    }

    .ai-image-box img {
      width: 100%;
      height: auto;
      display: block;
      aspect-ratio: 1 / 1;
      object-fit: cover;
    }

    /* 图片上的光晕标签 */
    .ai-badge {
      position: absolute;
      top: 14px;
      right: 14px;
      background: rgba(0, 0, 0, 0.6);
      backdrop-filter: blur(10px);
      -webkit-backdrop-filter: blur(10px);
      border-radius: 20px;
      padding: 6px 14px;
      font-size: 12px;
      font-weight: 600;
      color: #fff;
      letter-spacing: 0.5px;
      border: 1px solid rgba(255, 255, 255, 0.2);
      display: flex;
      align-items: center;
      gap: 5px;
    }

    .ai-badge::before {
      content: "✨";
      font-size: 11px;
    }

    .step-block {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .step-label {
      font-size: 14px;
      font-weight: 500;
      color: #a5b4fc;
      letter-spacing: 0.2px;
      text-transform: uppercase;
    }

    .btn {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      width: 100%;
      border: none;
      border-radius: 18px;
      padding: 17px 22px;
      font-weight: 600;
      font-size: 17px;
      text-decoration: none;
      transition: all 0.25s ease;
      cursor: pointer;
      position: relative;
      overflow: hidden;
      letter-spacing: 0.2px;
    }

    .btn::after {
      content: "";
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
      transition: left 0.5s;
    }

    .btn:hover::after {
      left: 100%;
    }

    .btn:active {
      transform: scale(0.97);
    }

    .btn-testflight {
      background: linear-gradient(135deg, #4f6ef6, #6366f1);
      color: white;
      box-shadow: 0 8px 22px rgba(79, 110, 246, 0.35);
    }

    .btn-testflight:hover {
      box-shadow: 0 12px 28px rgba(79, 110, 246, 0.5);
      transform: translateY(-2px);
    }

    .btn-app {
      background: linear-gradient(135deg, #10b981, #34c759);
      color: white;
      box-shadow: 0 8px 22px rgba(16, 185, 129, 0.35);
    }

    .btn-app:hover {
      box-shadow: 0 12px 28px rgba(16, 185, 129, 0.5);
      transform: translateY(-2px);
    }

    .divider {
      color: #6b7280;
      font-size: 12px;
      display: flex;
      align-items: center;
      gap: 12px;
      opacity: 0.7;
    }

    .divider::before,
    .divider::after {
      content: "";
      flex: 1;
      height: 1px;
      background: rgba(255, 255, 255, 0.12);
    }

    .note {
      font-size: 12px;
      color: #6b7280;
      line-height: 1.6;
    }
  </style>
</head>
<body>
  <div class="card">
    <!-- AI 生成图片展示 -->
    <div class="ai-image-box">
      <img src="https://file.ahelpers.com/convert/outputs/image/2026-04-27/pwbiqajp4v_1777284158478.jpg?auth_key=1777284158-0-0-5af2c63a73287905b98ba58b31812a13" alt="小萌AI 智能插图">
      <div class="ai-badge">AI 生成</div>
    </div>

    <!-- 第1步：下载 TestFlight -->
    <div class="step-block">
      <div class="step-label">第 1 步 · 安装 TestFlight</div>
      <a href="https://apps.apple.com/app/testflight/id899247664" target="_blank" rel="noopener noreferrer" class="btn btn-testflight">
        📱 下载 TestFlight
      </a>
    </div>

    <!-- 第2步：下载小萌AI -->
    <div class="step-block">
      <div class="step-label">第 2 步 · 安装小萌AI</div>
      <a href="https://testflight.apple.com/join/SRbna4BN" target="_blank" rel="noopener noreferrer" class="btn btn-app">
        🚀 下载我的软件
      </a>
    </div>

    <div class="divider">需要 iOS 16 / macOS 13 以上</div>
    <div class="note">
      请按顺序点击，先安装 TestFlight 才能接受邀请
    </div>
  </div>
</body>
</html>
