<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes">
  <title>DataCollector Beta 安装</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #f5f5f7;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
    }

    .card {
      max-width: 400px;
      width: 100%;
      background: white;
      border-radius: 24px;
      padding: 40px 28px 32px;
      box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
      text-align: center;
      display: flex;
      flex-direction: column;
      gap: 28px;
    }

    .step-block {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .step-label {
      font-size: 15px;
      font-weight: 600;
      color: #1d1d1f;
      letter-spacing: -0.2px;
    }

    .btn {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      width: 100%;
      border: none;
      border-radius: 16px;
      padding: 16px 20px;
      font-weight: 600;
      font-size: 17px;
      text-decoration: none;
      transition: opacity 0.2s, transform 0.1s;
      cursor: pointer;
    }

    .btn:active {
      transform: scale(0.98);
    }

    .btn-testflight {
      background: #007aff;
      color: white;
    }

    .btn-testflight:hover {
      opacity: 0.9;
    }

    .btn-app {
      background: #34c759;
      color: white;
    }

    .btn-app:hover {
      opacity: 0.9;
    }

    .divider {
      color: #8e8e93;
      font-size: 13px;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .divider::before,
    .divider::after {
      content: "";
      flex: 1;
      height: 1px;
      background: #e5e5ea;
    }

    .note {
      font-size: 12px;
      color: #8e8e93;
      line-height: 1.5;
    }
  </style>
</head>
<body>
  <div class="card">
    <!-- 第1步：下载 TestFlight -->
    <div class="step-block">
      <div class="step-label">第 1 步 · 安装 TestFlight</div>
      <a href="https://apps.apple.com/app/testflight/id899247664" target="_blank" rel="noopener noreferrer" class="btn btn-testflight">
        📱 下载 TestFlight
      </a>
    </div>

    <!-- 第2步：下载软件 -->
    <div class="step-block">
      <div class="step-label">第 2 步 · 安装 DataCollector</div>
      <a href="https://testflight.apple.com/join/SRbna4BN" target="_blank" rel="noopener noreferrer" class="btn btn-app">
        🚀 加入 Beta 版测试
      </a>
    </div>

    <div class="divider">需要 iOS 16 / macOS 13 以上</div>
    <div class="note">
      请按顺序点击，先安装 TestFlight 才能接受 Beta 邀请
    </div>
  </div>
</body>
</html>
