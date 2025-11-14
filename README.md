<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <meta name="format-detection" content="telephone=no, email=no">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <title>一日情侣牵线平台 - 同城交友体验</title>
    
    <!-- DNS预解析和预连接 -->
    <link rel="dns-prefetch" href="//cdn.bootcdn.net">
    <link rel="dns-prefetch" href="//2a.mazhifupay.com">
    <link rel="dns-prefetch" href="//ui-avatars.com">
    <link rel="dns-prefetch" href="//via.placeholder.com">
    <link rel="dns-prefetch" href="//s3.bmp.ovh">
    
    <link rel="preconnect" href="https://cdn.bootcdn.net" crossorigin>
    <link rel="preconnect" href="https://2a.mazhifupay.com" crossorigin>
    <link rel="preconnect" href="https://ui-avatars.com" crossorigin>
    <link rel="preconnect" href="https://via.placeholder.com" crossorigin>
    <link rel="preconnect" href="https://s3.bmp.ovh" crossorigin>
    
    <!-- 替换为国内可用的CDN -->
    <link rel="stylesheet" href="https://cdn.bootcdn.net/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- 或者使用本地字体图标库（如果有） -->
    <!-- <link rel="stylesheet" href="fonts/font-awesome.min.css"> -->
    <style>
        /* 保留所有原有CSS样式 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "PingFang SC", "Helvetica Neue", Arial, sans-serif;
            -webkit-tap-highlight-color: transparent; /* 移除移动端点击高亮 */
        }
        
        :root {
            --primary: #667eea;
            --primary-light: #a5b4fc;
            --secondary: #764ba2;
            --accent: #f093fb;
            --text: #2d3748;
            --text-light: #718096;
            --bg: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
            --card-bg: rgba(255, 255, 255, 0.95);
            --shadow: 0 4px 20px rgba(102, 126, 234, 0.1);
            --success: #34d399;
            --warning: #fbbf24;
            --danger: #f87171;
        }
        
        body {
            background: var(--bg);
            color: var(--text);
            line-height: 1.5;
            padding: 0;
            font-family: "PingFang SC", "Helvetica Neue", Arial, sans-serif;
            margin: 0;
            min-height: 100vh;
            font-family: var(--font-family);
            font-smooth: always;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            letter-spacing: 0.02em; /* 优化字间距 */
            overflow-x: hidden;
            position: relative;
            font-size: 15px; /* 基础字体大小 */
        }
        
        .container {
            max-width: 100%;
            padding: 10px;
            padding-bottom: 70px;
            overflow-x: hidden;
        }
        
        .alert-message {
            display: flex;
            align-items: center;
            margin-top: 10px;
            padding: 10px 12px;
            background-color: rgba(251, 191, 36, 0.1);
            border-left: 4px solid var(--warning);
            border-radius: 8px;
            font-size: 13px;
            color: var(--warning);
            font-weight: var(--font-weight-medium);
        }
        
        .alert-message i {
            margin-right: 10px;
            font-size: 16px;
        }
        
        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 18px 10px;
            text-align: center;
            border-radius: 0 0 25px 25px;
            box-shadow: 0 8px 30px rgba(102, 126, 234, 0.35);
            margin-bottom: 18px;
            position: relative;
            overflow: hidden;
            border-bottom: 2px solid rgba(255, 255, 255, 0.3);
            backdrop-filter: blur(10px);
        }
        
        header::before {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.15) 0%, rgba(255,255,255,0) 70%);
            transform: rotate(30deg);
        }
        
        header::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.6), transparent);
        }
        
        .user-info {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 10px;
        }
        
        .user-avatar {
            width: 55px;
            height: 55px;
            border-radius: 50%;
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.8rem;
            box-shadow: 0 6px 15px rgba(245, 87, 108, 0.4);
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }
        
        .user-avatar:active {
            transform: scale(0.9);
            box-shadow: 0 3px 8px rgba(255, 20, 147, 0.6);
            border-color: rgba(255, 255, 255, 0.5);
        }
        
        .user-details {
            flex: 1;
            margin-left: 15px;
            text-align: left;
        }
        
        .user-name {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .user-level {
            background: rgba(255,255,255,0.3);
            padding: 3px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            display: inline-block;
        }
        
        .notification-icon {
            background: rgba(255,255,255,0.2);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            transition: all 0.2s ease;
        }
        
        .notification-icon:active {
            transform: scale(0.95);
            background: rgba(255,255,255,0.3);
        }
        
        .header-content h1 {
            font-size: 1.8rem;
            margin-bottom: 8px;
            text-shadow: 0 3px 15px rgba(0, 0, 0, 0.2);
            cursor: pointer;
            transition: all 0.3s ease;
            color: white;
            font-weight: 800;
            letter-spacing: 1px;
        }
        
        .header-content h1:active {
            transform: scale(0.95);
        }
        
        .header-content p {
            font-size: 1.1rem;
            opacity: 0.95;
            text-shadow: 0 1px 5px rgba(0,0,0,0.4);
            font-weight: 500;
            color: #fff;
            letter-spacing: 0.5px;
        }
        
        .card {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 15px;
            margin-bottom: 12px;
            box-shadow: var(--shadow);
            border: 1px solid rgba(226, 232, 240, 0.5);
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
            /* 优化移动端触摸体验 */
            -webkit-tap-highlight-color: transparent;
            touch-action: manipulation;
        }
        
        .card::before {
            content: "";
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 107, 157, 0.15), transparent);
            transition: left 0.5s ease;
        }
        
        .card::after {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, #ff6b9d, #c026d3);
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        
        .card:hover::before {
            left: 100%;
        }
        
        .card:hover::after {
            opacity: 1;
        }
        
        .card:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(255, 107, 157, 0.35);
            border-color: rgba(255, 107, 157, 0.5);
        }
        
        .section-title {
            font-size: 1.2rem;
            font-weight: var(--font-weight-bold);
            margin-bottom: 16px;
            color: var(--text);
            display: flex;
            align-items: center;
            padding-bottom: 8px;
            border-bottom: 1px solid rgba(255, 45, 142, 0.1);
            letter-spacing: -0.5px;
        }
        
        .section-title i {
            margin-right: 10px;
            color: var(--primary);
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-size: 1.4rem;
        }
        
        .city-selector {
            position: relative;
        }
        
        /* 城市搜索样式 */
        .city-search {
            margin: 10px 0;
            position: relative;
        }
        
        .search-input-wrapper {
            position: relative;
            display: flex;
            align-items: center;
            background-color: #f5f5f5;
            border-radius: 20px;
            padding: 0 15px;
        }
        
        .search-input-wrapper i {
            color: #999;
            margin-right: 10px;
        }
        
        #citySearchInput {
            flex: 1;
            border: none;
            background: transparent;
            padding: 10px 0;
            outline: none;
            font-size: 14px;
        }
        
        .search-results {
            position: absolute;
            top: 100%;
            left: 0;
            right: 0;
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.15);
            z-index: 1000;
            max-height: 250px;
            overflow-y: auto;
            margin-top: 5px;
        }
        
        .search-result-item {
            padding: 12px 15px;
            cursor: pointer;
            display: flex;
            align-items: center;
            border-bottom: 1px solid #f0f0f0;
            transition: background-color 0.2s;
        }
        
        .search-result-item:last-child {
            border-bottom: none;
        }
        
        .search-result-item:hover {
            background-color: #f8f8f8;
        }
        
        .result-type {
            background-color: #e0f7fa;
            color: #006064;
            padding: 2px 8px;
            border-radius: 4px;
            font-size: 12px;
            margin-right: 10px;
        }
        
        .result-name {
            flex: 1;
            font-size: 14px;
        }
        
        .result-parent {
            color: #999;
            font-size: 12px;
            background-color: #f5f5f5;
            padding: 2px 8px;
            border-radius: 4px;
        }
        
        .province-list {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 12px;
            margin-bottom: 20px;
        }
        
        .province-item {
            padding: 12px 8px;
            text-align: center;
            background: linear-gradient(to bottom, #f8f8f8, #f0f0f0);
            border-radius: 12px;
            font-size: 0.9rem;
            transition: all 0.3s;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
            border: 1px solid rgba(255, 45, 142, 0.1);
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .province-item:active {
            transform: scale(0.98);
        }
        
        .province-item.active {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            box-shadow: 0 4px 10px rgba(255, 45, 142, 0.3);
        }
        
        .city-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin-top: 15px;
        }
        
        .city-card {
            background: linear-gradient(135deg, #f8f8f8, #f0f0f0);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s;
            border: 1px solid rgba(255, 45, 142, 0.1);
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .city-card:active {
            transform: scale(0.98);
        }
        
        .city-card:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 15px rgba(0,0,0,0.1);
        }
        
        .city-card.active {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
        }
        
        .city-icon {
            font-size: 2rem;
            margin-bottom: 10px;
            color: var(--primary);
        }
        
        .city-card.active .city-icon {
            color: white;
        }
        
        .city-name {
            font-size: 1rem;
            font-weight: 600;
        }
        
        .payment-info {
            text-align: center;
            padding: 15px 0;
        }
        
        .amount {
            font-size: 2.5rem;
            font-weight: bold;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin: 15px 0;
        }
        
        .btn {
            display: block;
            width: 100%;
            padding: 18px 24px;
            border: none;
            border-radius: 16px;
            font-size: 1.1rem;
            font-weight: 700;
            text-align: center;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
            position: relative;
            overflow: hidden;
            letter-spacing: 0.5px;
            text-transform: uppercase;
        }
        
        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.6s;
        }
        
        .btn:hover::before {
            left: 100%;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
        }
        
        .btn:active {
            transform: translateY(-1px);
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.2);
        }
        
        .trust-badges {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
            padding-top: 20px;
            border-top: 1px solid rgba(37, 99, 235, 0.1);
        }
        
        .trust-badge {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 8px;
            color: white;
            font-size: 0.85rem;
            padding: 12px 15px;
            border-radius: 12px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
        }
        
        .trust-badge:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.25);
        }
        
        .trust-badge i {
            font-size: 1.5rem;
            color: white;
        }
        
        .trust-badge .badge-text {
            font-weight: 600;
            font-size: 0.9rem;
            text-shadow: 0 1px 2px rgba(0, 0, 0, 0.3);
        }
        
        .trust-badge i {
            font-size: 1.2rem;
            background: linear-gradient(135deg, var(--success) 0%, #34d399 100%);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .user-reviews {
            margin-top: 35px;
            padding: 25px;
            border-radius: 16px;
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 6px 25px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .review-list {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        
        .review-item {
            background: rgba(37, 99, 235, 0.05);
            padding: 15px;
            border-radius: 10px;
            border-left: 4px solid var(--primary);
        }
        
        .review-content {
            font-size: 0.95rem;
            line-height: 1.5;
            color: var(--text);
            margin-bottom: 8px;
        }
        
        .review-author {
            font-size: 0.85rem;
            color: var(--text-light);
            text-align: right;
        }
        
        .payment-btn {
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 18px;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .payment-btn i {
            font-size: 1.4rem;
        }
        
        .payment-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(37, 99, 235, 0.2);
        }
        
        .payment-btn:active {
            transform: translateY(0);
        }
        
        .security-info {
            margin: 20px 0;
            padding: 15px;
            background: rgba(37, 99, 235, 0.05);
            border-radius: 10px;
            border-left: 4px solid var(--success);
        }
        
        .security-badges {
            display: flex;
            justify-content: space-around;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
        }
        
        .security-badge {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 0.9rem;
            color: var(--text);
        }
        
        .security-badge i {
            color: var(--success);
            font-size: 1.1rem;
        }
        
        /* 退款保障 */
        .refund-guarantees {
            margin: 20px 0;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .guarantee-items {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            margin-top: 15px;
        }
        
        .guarantee-item {
            display: flex;
            align-items: center;
            padding: 15px 20px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            margin: 10px;
        }
        
        .guarantee-item i {
            font-size: 20px;
            margin-right: 15px;
            color: var(--primary-color);
        }
        
        .guarantee-item span {
            color: var(--text-color);
            font-size: 14px;
        }
        
        .security-footer {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            padding: 40px 0;
            margin-top: 50px;
        }
        
        .security-footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .security-footer h3 {
            text-align: center;
            font-size: 1.8rem;
            margin-bottom: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        
        .security-features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
        }
        
        .security-feature {
            display: flex;
            align-items: flex-start;
            gap: 15px;
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 10px;
            backdrop-filter: blur(10px);
        }
        
        .security-feature i {
            font-size: 2rem;
            color: var(--success);
            flex-shrink: 0;
        }
        
        .security-feature h4 {
            margin: 0 0 10px 0;
            font-size: 1.2rem;
        }
        
        .security-feature p {
            margin: 0;
            opacity: 0.9;
            line-height: 1.5;
        }
        
        .legal-info {
            text-align: center;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
            padding-top: 20px;
            opacity: 0.8;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, #ff6b9d 0%, #c084fc 50%, #8b5cf6 100%);
            color: white;
            font-weight: 700;
            box-shadow: 0 6px 25px rgba(139, 92, 246, 0.45);
            text-shadow: 0 1px 2px rgba(0,0,0,0.3);
            border: 2px solid rgba(255, 255, 255, 0.25);
        }
        
        .btn-primary:hover {
            background: linear-gradient(135deg, #ff528f 0%, #b75cff 50%, #7c3aed 100%);
            box-shadow: 0 12px 40px rgba(139, 92, 246, 0.6);
        }
        
        .btn-primary:active {
            background: linear-gradient(135deg, #ff4285 0%, #a855ff 50%, #6d28d9 100%);
            box-shadow: 0 4px 20px rgba(139, 92, 246, 0.5);
        }
        
        .btn-secondary {
            background: linear-gradient(to bottom, #ffffff, #f8fafc);
            color: var(--text);
            margin-top: 15px;
            border: 2px solid rgba(0, 0, 0, 0.1);
        }
        
        .btn-secondary:hover {
            background: linear-gradient(to bottom, #f8fafc, #f1f5f9);
            border-color: rgba(0, 0, 0, 0.15);
        }
        
        .btn-secondary:active {
            background: linear-gradient(to bottom, #e2e8f0, #cbd5e1);
            border-color: rgba(0, 0, 0, 0.2);
        }
        
        .order-list {
            max-height: 400px;
            overflow-y: auto;
        }
        
        .order-item {
            padding: 18px;
            border-bottom: 1px solid rgba(255, 45, 142, 0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s;
        }
        
        .order-item:hover {
            background: rgba(255, 45, 142, 0.05);
            border-radius: 12px;
        }
        
        .order-item:last-child {
            border-bottom: none;
        }
        
        .order-info h3 {
            font-size: 1rem;
            margin-bottom: 8px;
        }
        
        .order-info p {
            font-size: 0.85rem;
            color: var(--text-light);
        }
        
        .order-status {
            font-size: 0.85rem;
            padding: 6px 12px;
            border-radius: 20px;
            font-weight: 600;
        }
        
        .status-paid {
            background: rgba(7, 193, 96, 0.1);
            color: #07c160;
        }
        
        .status-refunded {
            background: rgba(255, 59, 48, 0.1);
            color: #ff3b30;
        }
        
        .refund-btn {
            background: none;
            border: 1px solid #ff3b30;
            color: #ff3b30;
            padding: 6px 12px;
            border-radius: 8px;
            font-size: 0.8rem;
            cursor: pointer;
            transition: all 0.3s;
            transition: all 0.2s ease;
        }
        
        .refund-btn:active {
            background: #ff3b30;
            color: white;
            transform: scale(0.95);
        }
        
        .hidden {
            display: none !important;
        }
        
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.8);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            padding: 20px;
            backdrop-filter: blur(10px);
            animation: modalFadeIn 0.3s ease-out;
            /* 优化移动端触摸体验 */
            -webkit-overflow-scrolling: touch;
        }
        
        @keyframes modalFadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .modal-content {
            background: linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%);
            border-radius: 20px;
            padding: 30px;
            width: 100%;
            max-width: 420px;
            text-align: center;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            border: 1px solid rgba(255,255,255,0.2);
            animation: modalSlideIn 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
            /* 优化移动端触摸体验 */
            -webkit-tap-highlight-color: transparent;
            touch-action: manipulation;
        }
        
        .modal-content::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, var(--primary) 0%, var(--secondary) 100%);
        }
        
        @keyframes modalSlideIn {
            from { 
                opacity: 0; 
                transform: translateY(-50px) scale(0.9); 
            }
            to { 
                opacity: 1; 
                transform: translateY(0) scale(1); 
            }
        }
        
        .modal h2 {
            margin-bottom: 15px;
            color: var(--text);
            font-size: 1.4rem;
            font-weight: 600;
            background: linear-gradient(135deg, var(--text) 0%, var(--text-light) 100%);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .modal p {
            margin-bottom: 25px;
            color: var(--text-light);
            font-size: 1rem;
            line-height: 1.5;
        }
        
        .modal-buttons {
            display: flex;
            gap: 15px;
            margin-top: 10px;
        }
        
        .modal-buttons .btn {
            flex: 1;
            border-radius: 12px;
            font-weight: 600;
            padding: 12px 20px;
            transition: all 0.3s ease;
            border: none;
            font-size: 0.95rem;
        }
        
        .modal-buttons .btn-primary {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            box-shadow: 0 4px 15px rgba(255, 45, 142, 0.3);
        }
        
        .modal-buttons .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(255, 45, 142, 0.4);
        }
        
        .modal-buttons .btn-secondary {
            background: rgba(108, 117, 125, 0.1);
            color: var(--text-light);
            border: 1px solid rgba(108, 117, 125, 0.2);
        }
        
        .modal-buttons .btn-secondary:hover {
            background: rgba(108, 117, 125, 0.2);
            transform: translateY(-1px);
        }
        
        .success-icon {
            font-size: 4rem;
            color: var(--primary);
            margin-bottom: 15px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .payment-details {
            background: rgba(255, 45, 142, 0.05);
            border-radius: 10px;
            padding: 15px;
            margin: 15px 0;
            border-left: 4px solid var(--primary);
        }
        
        .detail-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-size: 0.9rem;
        }
        
        .detail-label {
            color: var(--text-light);
            font-weight: 500;
        }
        
        .detail-value {
            color: var(--text);
            font-weight: 600;
        }
        
        .refund-notice {
            background: rgba(255, 193, 7, 0.1);
            border-radius: 8px;
            padding: 10px;
            margin: 15px 0;
            border-left: 4px solid #ffc107;
            font-size: 0.85rem;
            color: #ff9800;
        }
        
        .message-notification {
            position: fixed;
            top: 80px;
            right: 20px;
            background: white;
            border-radius: 10px;
            padding: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
            z-index: 1000;
            animation: slideInRight 0.3s ease-out;
            max-width: 300px;
            border-left: 4px solid var(--primary);
        }
        
        .notification-content {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .notification-content i {
            color: var(--primary);
            font-size: 1.2rem;
        }
        
        .notification-content span {
            flex: 1;
            font-size: 0.9rem;
            color: var(--text);
        }
        
        .notification-close {
            background: none;
            border: none;
            font-size: 1.2rem;
            color: var(--text-light);
            cursor: pointer;
            padding: 0;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .notification-close:hover {
            color: var(--text);
        }
        
        @keyframes slideInRight {
            from {
                transform: translateX(100%);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }
        
        .loading {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255,255,255,.3);
            border-radius: 50%;
            border-top-color: #fff;
            animation: spin 1s ease-in-out infinite;
            margin-right: 10px;
        }
        
        @keyframes spin {
            to { transform: rotate(360deg); }
        }
        
        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: white;
            display: flex;
            justify-content: space-around;
            padding: 12px 0;
            box-shadow: 0 -2px 20px rgba(0,0,0,0.1);
            z-index: 100;
            /* 防止被手机键盘遮挡 */
            transform: translateZ(0);
            -webkit-transform: translateZ(0);
            /* 确保在输入时保持可见 */
            will-change: transform;
        }
        
        /* 移动设备输入时的特殊处理 */
        @media (max-height: 600px) {
            .bottom-nav {
                padding: 8px 0;
                position: fixed;
                bottom: 0;
                left: 0;
                right: 0;
                z-index: 9999;
                background: rgba(255, 255, 255, 0.95);
                backdrop-filter: blur(10px);
                border-top: 1px solid rgba(0, 0, 0, 0.1);
            }
            
            .nav-item {
                font-size: 0.7rem;
            }
            
            .nav-item i {
                font-size: 1.2rem;
            }
        }
        
        /* 全局移动端响应式优化 */
        @media (max-width: 768px) {
            /* 优化容器内边距 */
            .container {
                padding: 10px;
                padding-bottom: 80px;
                overflow-x: hidden;
            }
            
            /* 优化头部样式 */
            header {
                padding: 20px 10px;
                border-radius: 0 0 20px 20px;
            }
            
            .header-content h1 {
                font-size: 1.5rem;
            }
            
            .header-content p {
                font-size: 1rem;
            }
            
            /* 优化卡片样式 */
            .card {
                padding: 20px;
                margin-bottom: 15px;
            }
            
            /* 优化标题样式 */
            .section-title {
                font-size: 1.2rem;
                margin-bottom: 18px;
            }
            
            /* 优化按钮样式 */
            .btn {
                padding: 12px 20px;
                font-size: 0.95rem;
            }
            
            /* 优化表单元素 */
            input, textarea, select {
                font-size: 16px !important; /* 防止iOS缩放 */
                padding: 12px;
            }
            
            /* 优化模态框 */
            .modal {
                padding: 10px;
            }
            
            .modal-content {
                padding: 20px;
                border-radius: 15px;
            }
            
            /* 优化牵线服务区域 */
            .matchmaker-payment {
                padding: 15px;
            }
            
            .matchmaker-payment-features {
                grid-template-columns: 1fr;
            }
            
            /* 优化成功案例 */
            .stories-grid {
                grid-template-columns: 1fr;
            }
            
            /* 优化支付金额显示 */
            .matchmaker-payment-amount {
                font-size: 2.2rem;
            }
        }
        
        /* 超小屏幕优化 */
        @media (max-width: 480px) {
            /* 进一步优化字体大小 */
            body {
                font-size: 14px;
            }
            
            .header-content h1 {
                font-size: 1.3rem;
            }
            
            .section-title {
                font-size: 1.1rem;
            }
            
            /* 优化按钮大小，确保移动端易于点击 */
            .btn {
                padding: 14px 24px;
                font-size: 1rem;
                min-height: 48px;
            }
            
            /* 优化表单元素，确保移动端易于输入 */
            input, textarea, select {
                min-height: 48px;
                padding: 14px;
            }
            
            /* 优化底部导航，确保移动端易于点击 */
            .bottom-nav {
                padding: 8px 0;
            }
            
            .nav-item {
                font-size: 0.75rem;
                padding: 8px;
            }
            
            .nav-item i {
                font-size: 1.3rem;
                margin-bottom: 3px;
            }
            
            /* 优化卡片在超小屏幕上的显示 */
             .card {
                 padding: 16px;
                 margin-bottom: 12px;
             }
            
            /* 优化支付按钮 */
            .matchmaker-payment-methods {
                flex-direction: column;
            }
            
            .matchmaker-payment-method {
                margin-bottom: 10px;
            }
            
            /* 优化模态框按钮布局 */
            .modal-buttons {
                flex-direction: column;
            }
            
            /* 优化底部导航 */
            .nav-item {
                padding: 8px 5px;
            }
            
            .nav-item span {
                font-size: 0.65rem;
            }
        }
        
        /* 确保内容区域有足够的底部间距 */
        .main-content {
            padding-bottom: 70px !important;
        }
        
        /* 确保导航栏始终在最上层 */
        #bottomNav {
            z-index: 1000;
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            background: var(--card-bg);
            border-top: 1px solid rgba(255, 107, 157, 0.2);
            box-shadow: 0 -2px 15px rgba(255, 107, 157, 0.15);
        }
        
        /* 简化文字样式 */
        .gradient-text {
            color: var(--primary);
            font-weight: 600;
        }
        
        /* 简化标题样式 */
        h1, h2, h3, h4, h5, h6 {
            font-weight: 600;
            margin-bottom: 12px;
            color: var(--text);
        }
        
        h1 {
            font-size: 1.85rem;
            font-weight: var(--font-weight-bold);
            line-height: 1.2;
        }
        
        h2 {
            font-size: 1.45rem;
            line-height: 1.25;
        }
        
        h3 {
            font-size: 1.25rem;
            line-height: 1.3;
        }
        
        h4 {
            font-size: 1.1rem;
            font-weight: var(--font-weight-medium);
            line-height: 1.35;
        }
        
        /* 文字美化 - 正文样式增强 */
        p {
            margin-bottom: 12px;
            color: var(--text);
            font-size: 0.95rem;
            line-height: 1.5;
            font-weight: var(--font-weight-regular);
        }
        
        /* 简化段落样式 */
        .enhanced-paragraph {
            font-size: 0.9rem;
            line-height: 1.5;
            color: var(--text-light);
            margin-bottom: 10px;
        }
        
        /* 简化强调文本 */
        .highlight {
            font-weight: 600;
            color: var(--primary);
        }
        
        /* 可折叠区块样式 */
        .collapsible-section {
            margin-bottom: 1rem;
            border-radius: var(--border-radius);
            overflow: hidden;
            background-color: var(--card-bg-color);
            box-shadow: var(--box-shadow-light);
        }
        
        .collapsible-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        
        .collapsible-header:hover {
            background-color: var(--hover-color);
        }
        
        .collapsible-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease, padding 0.3s ease;
        }
        
        .collapsible-content.show {
            max-height: 500px;
            padding: 0 1rem 1rem;
        }
        
        .collapse-icon {
            transition: transform 0.3s ease;
        }
        
        .collapse-icon.rotate {
            transform: rotate(180deg);
        }

        /* 简化链接样式 */
        a {
            color: var(--primary);
            text-decoration: none;
            transition: color 0.3s ease;
            font-weight: 500;
        }
        
        a:hover {
            color: var(--secondary);
        }
        
        /* 文字美化 - 按钮文字样式增强 */
        .btn {
            font-weight: 700;
            letter-spacing: 0.7px;
            text-transform: uppercase;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            text-rendering: optimizeLegibility;
            -webkit-font-smoothing: antialiased;
        }
        
        /* 文字美化 - 卡片内文字样式 */
        .card p {
            color: var(--text-light);
        }
        
        /* 移除动画效果 */
        
        /* 简化强调文字 */
        .highlight {
            color: var(--primary);
            font-weight: 600;
        }
        
        /* 文字美化 - 标签文字 */
        .tag {
            font-size: 0.85rem;
            font-weight: 600;
            letter-spacing: 0.5px;
            text-transform: uppercase;
        }
        
        /* 文字美化 - 状态文字 */
        .status-text {
            font-size: 0.9rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        
        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            color: var(--text-light);
            font-size: 0.8rem;
            transition: all 0.3s;
            padding: 5px;
            border-radius: 10px;
            transition: all 0.2s ease;
        }
        
        .nav-item:active {
            background: rgba(255, 45, 142, 0.1);
            transform: scale(0.95);
        }
        
        .nav-item.active {
            color: var(--primary);
        }
        
        .nav-item i {
            font-size: 1.4rem;
            margin-bottom: 5px;
        }
        
        .profile-section {
            text-align: center;
            padding: 20px 0;
        }
        
        .profile-avatar {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent) 0%, var(--primary) 100%);
            margin: 0 auto 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2.5rem;
            box-shadow: 0 8px 20px rgba(255, 45, 142, 0.3);
        }
        
        .profile-name {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .profile-location {
            color: var(--text-light);
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .profile-location i {
            margin-right: 5px;
            color: var(--primary);
        }
        
        .stats {
            display: flex;
            justify-content: space-around;
            margin: 25px 0;
        }
        
        .stat-item {
            text-align: center;
        }
        
        .stat-value {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .stat-label {
            font-size: 0.85rem;
            color: var(--text-light);
        }
        
        .tips {
            background: rgba(255, 45, 142, 0.05);
            padding: 15px;
            border-radius: 12px;
            margin: 20px 0;
            font-size: 0.9rem;
            color: var(--text-light);
            border-left: 4px solid var(--primary);
        }
        
        footer {
            text-align: center;
            padding: 20px 0;
            color: var(--text-light);
            font-size: 0.8rem;
        }
        
        .lock-icon {
            position: absolute;
            top: 10px;
            right: 10px;
            color: var(--primary);
            font-size: 1.2rem;
        }
        
        .error-message {
            background: rgba(255, 59, 48, 0.1);
            color: #ff3b30;
            padding: 12px;
            border-radius: 8px;
            margin: 15px 0;
            text-align: center;
            font-size: 0.9rem;
            border-left: 4px solid #ff3b30;
        }
        
        .payment-processing {
            text-align: center;
            padding: 20px;
        }

        /* 牵线服务通知样式 - 全新现代设计 */
        .modal-content.premium-style {
            background: transparent;
            border: none;
            box-shadow: none;
        }
        
        .matchmaker-notification.modern-notification {
            background: linear-gradient(135deg, #ffffff, #fff5f5);
            border-radius: 25px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(255, 102, 130, 0.2);
            max-width: 550px;
            margin: 0 auto;
            position: relative;
            overflow: hidden;
            border: 2px solid rgba(255, 102, 130, 0.2);
            max-height: 85vh; /* 设置模态框最大高度为视口高度的85% */
            display: flex;
            flex-direction: column;
            /* 优化移动端滚动体验 */
            -webkit-overflow-scrolling: touch;
            scrollbar-width: thin;
        }
        
        /* 确保通知内容区域能够伸缩，按钮区域保持在底部 */
        /* 已合并到下面的完整样式定义中 */
        
        /* 装饰性心形元素 */
        .notification-decoration {
            position: absolute;
            top: -20px;
            right: -20px;
            left: -20px;
            height: 80px;
            overflow: hidden;
            z-index: 0;
        }
        
        .heart-decoration {
            position: absolute;
            background: rgba(255, 102, 130, 0.08);
            transform: rotate(45deg);
            animation: floatUpDown 6s ease-in-out infinite;
        }
        
        .heart-decoration::before,
        .heart-decoration::after {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: inherit;
            border-radius: 50%;
        }
        
        .heart-decoration::before {
            top: -50%;
            left: 0;
        }
        
        .heart-decoration::after {
            top: 0;
            left: -50%;
        }
        
        .heart-1 {
            width: 40px;
            height: 40px;
            top: 20px;
            left: 20%;
            animation-delay: 0s;
        }
        
        .heart-2 {
            width: 30px;
            height: 30px;
            top: 30px;
            left: 50%;
            animation-delay: 2s;
        }
        
        .heart-3 {
            width: 25px;
            height: 25px;
            top: 25px;
            left: 80%;
            animation-delay: 4s;
        }
        
        /* 标题区域 */
        .notification-header.modern-header {
            text-align: center;
            margin-bottom: 25px;
            position: relative;
            z-index: 1;
        }
        
        .notification-header.modern-header h2 {
            font-size: 28px;
            color: #333;
            margin: 0 0 10px 0;
            font-weight: 700;
            letter-spacing: -0.5px;
        }
        
        .header-subtitle {
            font-size: 16px;
            color: #888;
            margin: 0;
            font-weight: 400;
        }
        
        .gold-icon {
            color: #ffd700;
            margin-right: 8px;
            font-size: 24px;
        }
        
        .gradient-text {
            background: linear-gradient(90deg, #ff6b6b, #ff9966);
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 800;
        }
        
        /* 主要内容区域 */
        .notification-content.modern-content {
            position: relative;
            padding: 20px 0;
            z-index: 1;
            flex: 1; /* 确保内容区域能够伸缩 */
            max-height: 60vh; /* 设置最大高度为视口高度的60% */
            overflow-y: auto; /* 添加垂直滚动 */
            -webkit-overflow-scrolling: touch; /* 优化移动端滚动体验 */
        }
        
        /* 视觉元素 */
        .notification-visual {
            display: flex;
            justify-content: center;
            margin-bottom: 25px;
            height: 120px;
            position: relative;
        }
        
        .visual-container {
            position: relative;
            width: 100px;
            height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .red-heart, .pink-heart, .blue-heart {
            position: absolute;
            font-size: 50px;
        }
        
        .red-heart {
            color: #ff3860;
            animation: pulse 2s ease-in-out infinite;
        }
        
        .pink-heart {
            color: #ff7eb3;
            animation: pulse 2s ease-in-out infinite 0.5s;
        }
        
        .blue-heart {
            color: #3273dc;
            animation: pulse 2s ease-in-out infinite 1s;
        }
        
        /* 文字内容 */
        .notification-message {
            text-align: center;
        }
        
        .message-text {
            font-size: 17px;
            line-height: 1.7;
            margin: 20px 0;
        }
        
        .romantic-text {
            color: #444;
            font-weight: 500;
        }
        
        .greeting {
            color: #ff6b6b;
            font-weight: 600;
        }
        
        .highlight {
            background: linear-gradient(120deg, #ffb347, #ffcc33);
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: bold;
        }
        
        /* 服务亮点 */
        .service-highlights {
            display: flex;
            justify-content: space-around;
            margin: 30px 0;
            padding: 0 10px;
        }
        
        .highlight-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            width: 30%;
        }
        
        .highlight-item i {
            font-size: 24px;
            color: #ff6b6b;
            margin-bottom: 10px;
            background: rgba(255, 107, 107, 0.1);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .highlight-item span {
            font-size: 14px;
            color: #555;
            line-height: 1.4;
        }
        
        /* 特别提示文字 */
        .italic-text {
            font-style: italic;
            background: linear-gradient(135deg, #fff5f5, #fff0f0);
            padding: 15px;
            border-radius: 15px;
            margin: 25px auto;
            max-width: 90%;
            box-shadow: 0 2px 10px rgba(255, 107, 107, 0.1);
        }
        
        .seductive-text {
            color: #ff6b6b;
            position: relative;
        }
        
        .flame-icon {
            color: #ff6b6b;
            margin-right: 8px;
            font-size: 18px;
        }
        
        .love-icon {
            color: #ff6b6b;
            margin-left: 8px;
            font-size: 18px;
        }
        
        .special-text {
            color: #e84393;
            font-weight: 600;
        }
        
        .underline {
            text-decoration: underline;
            text-decoration-style: wavy;
            text-decoration-color: #ff6b6b;
            text-underline-offset: 4px;
        }
        
        /* 免责声明 */
        .notification-disclaimer {
            margin-top: 25px;
            padding: 15px;
            background: rgba(0, 0, 0, 0.03);
            border-radius: 10px;
            text-align: center;
        }
        
        .notification-disclaimer small {
            color: #999;
            font-size: 13px;
            line-height: 1.5;
        }
        
        /* 按钮区域 */
        .notification-actions.modern-actions {
            text-align: center;
            margin-top: 30px;
            position: relative;
            z-index: 1;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 102, 130, 0.1);
        }
        
        .premium-button {
            background: linear-gradient(135deg, #ff6b6b, #ff8e53);
            border: none;
            color: white;
            padding: 14px 40px;
            border-radius: 30px;
            font-size: 17px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(255, 107, 107, 0.4);
            position: relative;
            overflow: hidden;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        
        .premium-button:before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: 0.5s;
        }
        
        .premium-button:hover:before {
            left: 100%;
        }
        
        .premium-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(255, 107, 107, 0.5);
        }
        
        /* 动画效果 */
        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
                opacity: 1;
            }
            50% {
                transform: scale(1.2);
                opacity: 0.8;
            }
        }
        
        @keyframes floatUpDown {
            0%, 100% {
                transform: translateY(0) rotate(45deg);
            }
            50% {
                transform: translateY(-10px) rotate(45deg);
            }
        }
        
        .seductive-button {
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(255, 62, 108, 0.4);
            position: relative;
        }
        
        /* 动画效果定义 */
        @keyframes heartbeat {
            0% { transform: scale(1); }
            14% { transform: scale(1.3); }
            28% { transform: scale(1); }
            42% { transform: scale(1.3); }
            70% { transform: scale(1); }
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        /* 动画类 */
        .heartbeat {
            animation: heartbeat 1.2s ease-in-out infinite;
        }
        
        .pulse-animation {
            animation: pulse 2s infinite;
        }
        
        .seductive-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: all 0.5s ease;
        }
        
        .seductive-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(255, 62, 108, 0.5);
            background: linear-gradient(45deg, #ff6b81, #ff3e6c);
        }
        
        .seductive-button:hover::before {
            left: 100%;
        }
        
        .seductive-button:active {
            transform: translateY(-1px);
            box-shadow: 0 4px 15px rgba(255, 62, 108, 0.4);
        }

        .notification-actions .btn-primary:hover {
            background: linear-gradient(45deg, #ff2a5c, #ff5a71);
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(255, 62, 108, 0.4);
        }

        .notification-actions .btn-primary:active {
            transform: translateY(0);
        }

        /* 心跳动画 */
        @keyframes heartbeat {
            0% {
                transform: scale(1);
            }
            14% {
                transform: scale(1.1);
            }
            28% {
                transform: scale(1);
            }
            42% {
                transform: scale(1.1);
            }
            70% {
                transform: scale(1);
            }
        }
        
        /* 支付过渡页面样式 */
        .payment-redirect {
            text-align: center;
        }
        
        .payment-icon {
            font-size: 4rem;
            margin-bottom: 20px;
            color: var(--primary);
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .countdown-area {
            margin: 30px 0;
        }
        
        .countdown-area p {
            font-size: 1.1rem;
            color: var(--text);
            margin-bottom: 15px;
            font-weight: 500;
        }
        
        .countdown-area #redirectCountdown {
            color: var(--primary);
            font-weight: 600;
            font-size: 1.3rem;
        }
        
        .progress-bar {
            width: 100%;
            height: 10px;
            background-color: #f0f0f0;
            border-radius: 5px;
            overflow: hidden;
            box-shadow: inset 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary) 0%, var(--secondary) 100%);
            border-radius: 5px;
            transition: width 1s linear;
            width: 100%;
        }
        
        .payment-status {
            font-size: 1.1rem;
            margin: 15px 0;
            font-weight: 600;
        }
        
        .status-success {
            color: #07c160;
        }
        
        .status-failed {
            color: #ff3b30;
        }
        
        .payment-methods {
            display: flex;
            gap: 10px;
            margin: 20px 0;
        }
        
        .payment-method {
            flex: 1;
            padding: 15px;
            text-align: center;
            border: 2px solid #f0f0f0;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s;
            transition: all 0.2s ease;
        }
        
        .payment-method:active {
            transform: scale(0.98);
        }
        
        .payment-method.active {
            border-color: var(--primary);
            background: rgba(255, 45, 142, 0.05);
        }
        
        .payment-method i {
            font-size: 2rem;
            margin-bottom: 10px;
            color: var(--primary);
        }
        
        .payment-form {
            display: none;
            margin-top: 20px;
        }
        
        .payment-form.active {
            display: block;
        }
        
        /* 反馈中心样式 */
        .login-prompt {
            text-align: center;
            padding: 40px 20px;
            color: var(--text-light);
        }
        
        /* 反馈中心增强样式 */
        .feedback-page-navigation {
            display: flex;
            background: #f8f8f8;
            border-radius: 12px;
            padding: 5px;
            margin-bottom: 20px;
        }
        
        .feedback-page-tab {
            flex: 1;
            text-align: center;
            padding: 12px;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 5px;
        }
        
        .feedback-page-tab.active {
            background: white;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
            color: var(--primary);
        }
        
        .feedback-page-tab i {
            font-size: 1.2rem;
        }
        
        .feedback-mode-content {
            display: none;
        }
        
        .feedback-mode-content.active {
            display: block;
        }

        /* 反馈促销区域样式 */
        .feedback-promo {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.9), rgba(255, 255, 255, 0.7));
            border: 2px solid rgba(255, 45, 142, 0.2);
            border-radius: 15px;
            padding: 20px;
            margin: 20px 0;
            text-align: center;
            box-shadow: 0 4px 15px rgba(255, 45, 142, 0.1);
            transition: all 0.3s ease;
        }

        .feedback-promo:hover {
            box-shadow: 0 8px 25px rgba(255, 45, 142, 0.2);
            transform: translateY(-2px);
        }

        .promo-badge {
            display: inline-block;
            padding: 5px 15px;
            border-radius: 20px;
            color: white;
            font-weight: bold;
            font-size: 12px;
            margin-bottom: 10px;
            animation: pulse 2s infinite;
        }

        .promo-text {
            font-size: 16px;
            margin-bottom: 15px;
            line-height: 1.6;
        }

        .feedback-promo .btn {
            padding: 10px 30px;
            font-size: 16px;
            font-weight: bold;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .feedback-promo .btn:hover {
            transform: scale(1.05);
            box-shadow: 0 6px 20px rgba(255, 45, 142, 0.4);
        }
        
        .feedback-info {
            background: rgba(255, 45, 142, 0.05);
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 20px;
        }
        
        .feedback-stats {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-size: 0.9rem;
        }
        
        .feedback-exhibition-link {
            text-align: center;
            margin-bottom: 20px;
            padding: 20px;
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1) 0%, rgba(118, 75, 162, 0.1) 100%);
            border-radius: 10px;
            border: 2px dashed #667eea;
        }

        .feedback-exhibition-link .btn {
            font-size: 1.1em;
            padding: 12px 30px;
            font-weight: bold;
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.3);
            transition: all 0.3s ease;
        }

        .feedback-exhibition-link .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.4);
        }

        /* 反馈展览模态框 */
        .feedback-exhibition-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.95);
            z-index: 10000;
            overflow-y: auto;
            padding: 20px;
            opacity: 0;
            transition: opacity 0.5s ease;
        }

        .feedback-exhibition-modal.active {
            display: block;
            opacity: 1;
        }

        .feedback-exhibition-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px 0;
        }

        .feedback-exhibition-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            color: white;
        }

        .feedback-exhibition-header h2 {
            font-size: 1.8rem;
            margin: 0;
        }

        .feedback-exhibition-close {
            font-size: 2rem;
        }

        /* 法律条款模态框样式 */
        .legal-terms-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            z-index: 10000;
            overflow-y: auto;
            padding: 20px;
            backdrop-filter: blur(10px);
        }

        .legal-terms-modal.active {
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .legal-terms-content {
            background: linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%);
            border-radius: 20px;
            padding: 30px;
            width: 100%;
            max-width: 800px;
            max-height: 80vh;
            overflow-y: auto;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            position: relative;
        }

        .legal-terms-header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 1px solid rgba(0,0,0,0.1);
        }

        .legal-terms-header h3 {
            margin: 0;
            color: var(--text);
            font-size: 1.6rem;
            font-weight: 600;
        }

        .legal-terms-body {
            margin-bottom: 30px;
        }

        .terms-section {
            margin-bottom: 25px;
        }

        .terms-section h4 {
            color: var(--primary);
            margin-bottom: 10px;
            font-size: 1.1rem;
            font-weight: 600;
        }

        .terms-section p {
            color: var(--text-light);
            margin-bottom: 10px;
            line-height: 1.6;
            font-size: 0.95rem;
        }

        .legal-terms-footer {
            border-top: 1px solid rgba(0,0,0,0.1);
            padding-top: 20px;
        }

        .terms-checkbox {
            margin-bottom: 20px;
            text-align: left;
        }

        .terms-checkbox input {
            margin-right: 10px;
            transform: scale(1.2);
        }

        .terms-checkbox label {
            color: var(--text);
            font-size: 0.95rem;
            cursor: pointer;
        }

        .terms-actions {
            text-align: center;
        }

        .terms-actions .btn {
            padding: 12px 40px;
            font-size: 1rem;
            font-weight: 600;
        }

        /* 底部法律信息样式 */
        .footer-legal {
            background: linear-gradient(135deg, rgba(255,255,255,0.95) 0%, rgba(248,249,250,0.95) 100%);
            padding: 20px;
            text-align: center;
            border-top: 1px solid rgba(0,0,0,0.1);
            margin-top: 40px;
        }

        .footer-legal p {
            margin: 5px 0;
            color: var(--text-light);
            font-size: 0.85rem;
        }

        .footer-legal a {
            color: var(--primary);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-legal a:hover {
            color: var(--secondary);
            text-decoration: underline;
        }

        .feedback-exhibition-close {
            cursor: pointer;
            background: none;
            border: none;
            color: white;
            padding: 0;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            transition: background-color 0.3s;
        }
.feedback-exhibition-close:hover {
    background-color: rgba(255, 255, 255, 0.2);
}

.feedback-exhibition-close:hover {
    background-color: rgba(255, 255, 255, 0.2);
}

.feedback-exhibition-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 25px;
    margin-bottom: 30px;
}

@media (max-width: 768px) {
    .feedback-exhibition-grid {
        grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
        gap: 18px;
        margin-bottom: 25px;
    }
}

@media (max-width: 480px) {
    .feedback-exhibition-grid {
        grid-template-columns: 1fr;
        gap: 15px;
        margin-bottom: 20px;
    }
}

.feedback-exhibition-item {
    background-color: rgba(255, 255, 255, 0.12);
    border-radius: 15px;
    overflow: hidden;
    transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275), box-shadow 0.4s ease;
    cursor: pointer;
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.2);
}

        .feedback-exhibition-item:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.6);
        }

        .feedback-exhibition-image-container {
            position: relative;
            overflow: hidden;
            height: 220px;
            display: flex;
            gap: 5px;
        }

        @media (max-width: 768px) {
            .feedback-exhibition-image-container {
                height: 190px;
            }
        }

        @media (max-width: 480px) {
            .feedback-exhibition-image-container {
                height: 170px;
            }
        }

        .feedback-exhibition-image {
            flex: 1;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s ease;
        }

        .feedback-exhibition-item:hover .feedback-exhibition-image {
            transform: scale(1.1);
        }

        .feedback-exhibition-image-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to bottom, rgba(0,0,0,0.2) 0%, rgba(0,0,0,0.7) 100%);
            opacity: 0;
            transition: opacity 0.4s ease;
            pointer-events: none;
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            padding: 20px;
            color: white;
        }
        
        .feedback-exhibition-image-overlay i {
            font-size: 24px;
            margin-bottom: 8px;
            text-shadow: 0 2px 10px rgba(0,0,0,0.7);
        }

        .feedback-exhibition-item:hover .feedback-exhibition-image-overlay {
            opacity: 1;
        }
        
        /* 用户信息样式 */
        .feedback-user-info {
            display: flex;
            align-items: center;
            padding: 15px;
            gap: 15px;
        }
        
        .feedback-user-avatar {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid rgba(255, 255, 255, 0.3);
        }
        
        .feedback-user-details {
            flex: 1;
        }
        
        .feedback-user-name-container {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 5px;
        }
        
        .feedback-user-name {
            font-size: 16px;
            font-weight: bold;
            color: #ffffff;
        }
        
        .feedback-verified-badge {
            display: flex;
            align-items: center;
            gap: 5px;
            font-size: 12px;
            color: #4ade80;
        }
        
        .feedback-location-date {
            font-size: 12px;
            color: rgba(255, 255, 255, 0.7);
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .feedback-location-date i {
            margin-right: 3px;
        }
        
        .feedback-rating {
            display: flex;
            gap: 3px;
            margin-bottom: 8px;
        }
        
        .feedback-rating .fa-star {
            font-size: 14px;
            transition: color 0.3s ease;
        }
        
        .feedback-rating .fa-star.filled {
            color: #fbbf24;
            text-shadow: 0 0 10px rgba(251, 191, 36, 0.6);
        }
        
        .feedback-rating .fa-star.empty {
            color: rgba(255, 255, 255, 0.2);
        }
        
        .feedback-comment {
            padding: 0 15px 20px;
            color: rgba(255, 255, 255, 0.85);
            font-size: 14px;
            line-height: 1.6;
            font-style: italic;
            border-left: 3px solid rgba(255, 255, 255, 0.2);
            margin: 0 15px;
        }
        
        /* 查看更多按钮 */
        .feedback-exhibition-more {
            text-align: center;
            padding: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .feedback-exhibition-more .btn {
            padding: 10px 30px;
            font-size: 16px;
            font-weight: 600;
        }
        
        /* VIP提示模态框 */
        .vip-prompt-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 11000;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }
        
        .vip-prompt-modal.active {
            opacity: 1;
            visibility: visible;
        }
        
        /* VIP提示内容 */
        .vip-prompt-content {
            background: white;
            border-radius: 12px;
            max-width: 450px;
            width: 90%;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
            overflow: hidden;
        }
        
        /* VIP提示头部 */
        .vip-prompt-header {
            background: linear-gradient(135deg, #ff6b6b, #ffa500);
            color: white;
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .vip-prompt-header h3 {
            margin: 0;
            font-size: 20px;
            font-weight: 700;
        }
        
        /* VIP提示关闭按钮 */
        .vip-prompt-close {
            background: rgba(255, 255, 255, 0.2);
            border: none;
            color: white;
            font-size: 20px;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background 0.3s ease;
        }
        
        .vip-prompt-close:hover {
            background: rgba(255, 255, 255, 0.3);
        }
        
        /* VIP提示主体 */
        .vip-prompt-body {
            padding: 30px;
        }
        
        .vip-prompt-body p {
            margin: 0 0 15px 0;
            font-size: 16px;
            line-height: 1.5;
            color: #333;
        }
        
        /* VIP特权列表 */
        .vip-privileges {
            margin: 20px 0;
            padding-left: 25px;
        }
        
        .vip-privileges li {
            margin-bottom: 12px;
            font-size: 15px;
            line-height: 1.5;
            color: #555;
        }
        
        .vip-privileges i {
            color: #28a745;
            margin-right: 8px;
        }
        
        /* VIP提示操作按钮 */
        .vip-prompt-actions {
            display: flex;
            gap: 12px;
            margin-top: 25px;
        }
        
        .vip-prompt-actions .btn {
            flex: 1;
            padding: 12px;
            font-size: 15px;
            font-weight: 600;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .vip-prompt-actions .btn-primary {
            background: linear-gradient(135deg, #ff6b6b, #ffa500);
            color: white;
        }
        
        .vip-prompt-actions .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(255, 107, 107, 0.4);
        }
        
        .vip-prompt-actions .btn-secondary {
            background: #6c757d;
            color: white;
        }
        
        .vip-prompt-actions .btn-secondary:hover {
            background: #5a6268;
            transform: translateY(-2px);
        }

        /* 放大查看模态框 */
        .image-preview-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.95);
            z-index: 11000;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .image-preview-modal.active {
            display: flex;
        }

        .image-preview-content {
            position: relative;
            max-width: 90%;
            max-height: 90%;
        }

        .image-preview {
            max-width: 100%;
            max-height: 80vh;
            object-fit: contain;
        }

        .image-preview-close {
            position: absolute;
            top: -40px;
            right: 0;
            font-size: 2rem;
            cursor: pointer;
            background: none;
            border: none;
            color: white;
            padding: 0;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            transition: background-color 0.3s;
        }

        .image-preview-close:hover {
            background-color: rgba(255, 255, 255, 0.2);
        }

        .feedback-tip {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 0.85rem;
            color: var(--text-light);
        }
        
        .feedback-tip i {
            color: var(--primary);
        }
        
        .feedback-list {
            display: grid;
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .feedback-item {
            background: white;
            border-radius: 12px;
            padding: 15px;
            border: 1px solid rgba(255, 45, 142, 0.1);
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .feedback-item:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 15px rgba(255, 45, 142, 0.1);
        }
        
        .feedback-item-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }
        
        .feedback-title {
            font-weight: 600;
            font-size: 1rem;
            color: var(--text);
        }
        
        .feedback-date {
            font-size: 0.8rem;
            color: var(--text-light);
        }
        
        .feedback-preview {
            display: flex;
            gap: 10px;
            align-items: flex-start;
        }
        
        .feedback-text {
            flex: 1;
            font-size: 0.9rem;
            color: var(--text-light);
            line-height: 1.4;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            line-clamp: 2;
            -webkit-box-orient: vertical;
            overflow: hidden;
        }
        
        .feedback-image {
            width: 60px;
            height: 60px;
            border-radius: 8px;
            object-fit: cover;
            background: #f0f0f0;
        }
        
        .vip-restricted {
            position: relative;
            border-radius: 12px;
            overflow: hidden;
        }
        
        .vip-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.7);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: white;
            text-align: center;
            padding: 20px;
            z-index: 10;
        }
        
        .vip-overlay i {
            font-size: 3rem;
            margin-bottom: 15px;
            color: #ffd700;
        }
        
        .vip-overlay h3 {
            margin-bottom: 10px;
            font-size: 1.2rem;
        }
        
        .vip-overlay p {
            margin-bottom: 15px;
            font-size: 0.9rem;
            opacity: 0.9;
        }
        
        .feedback-upload {
            background: white;
            border-radius: 12px;
            padding: 20px;
            border: 2px dashed rgba(255, 45, 142, 0.3);
            margin-top: 20px;
        }
        
        .feedback-upload-title {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 20px;
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--primary);
        }
        
        .feedback-upload-title i {
            font-size: 1.3rem;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--text);
        }
        
        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 12px;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            font-size: 0.9rem;
            transition: all 0.3s;
        }
        
        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 2px rgba(255, 45, 142, 0.1);
        }
        
        /* 手机号验证状态样式 */
        .form-group input.valid {
            border-color: #28a745;
            box-shadow: 0 0 0 2px rgba(40, 167, 69, 0.1);
        }
        
        .form-group input.invalid {
            border-color: #dc3545;
            box-shadow: 0 0 0 2px rgba(220, 53, 69, 0.1);
        }
        
        .form-group input.valid:focus {
            border-color: #28a745;
            box-shadow: 0 0 0 2px rgba(40, 167, 69, 0.2);
        }
        
        .form-group input.invalid:focus {
            border-color: #dc3545;
            box-shadow: 0 0 0 2px rgba(220, 53, 69, 0.2);
        }
        
        .photo-upload-area {
            border: 2px dashed #e0e0e0;
            border-radius: 8px;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .photo-upload-area:hover {
            border-color: var(--primary);
        }
        
        .photo-upload-preview {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            color: var(--text-light);
        }
        
        .photo-upload-preview i {
            font-size: 2rem;
            color: var(--primary);
        }
        
        .photo-list {
            display: flex;
            gap: 10px;
            margin-top: 10px;
            flex-wrap: wrap;
        }
        
        .photo-item {
            position: relative;
            width: 80px;
            height: 80px;
            border-radius: 8px;
            overflow: hidden;
        }
        
        .photo-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .photo-remove {
            position: absolute;
            top: 5px;
            right: 5px;
            background: rgba(0,0,0,0.7);
            color: white;
            border: none;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 0.8rem;
        }
        
        .form-actions {
            display: flex;
            gap: 15px;
        }
        
        .form-actions .btn {
            flex: 1;
        }
        
        /* 反馈详情页面样式 */
        .feedback-detail {
            background: white;
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 20px;
        }
        
        .feedback-detail-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid rgba(255, 45, 142, 0.1);
        }
        
        .feedback-detail-title {
            font-size: 1.3rem;
            font-weight: 600;
            color: var(--text);
        }
        
        .feedback-detail-meta {
            display: flex;
            gap: 15px;
            font-size: 0.9rem;
            color: var(--text-light);
        }
        
        .feedback-detail-content {
            margin-bottom: 20px;
            line-height: 1.6;
            color: var(--text);
        }
        
        .feedback-detail-images {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 10px;
            margin-bottom: 20px;
        }
        
        .feedback-detail-image {
            width: 100%;
            height: 150px;
            border-radius: 8px;
            object-fit: cover;
            background: #f0f0f0;
        }
        
        .feedback-detail-actions {
            display: flex;
            gap: 10px;
            justify-content: flex-end;
        }
        
        .feedback-detail-back {
            background: #f8f8f8;
            color: var(--text);
        }
        
        .login-prompt-content i {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .login-prompt-content h3 {
            margin: 15px 0 10px;
            font-size: 1.3rem;
        }
        
        .feedback-content {
            padding: 20px;
        }
        
        .feedback-page-navigation {
            display: flex;
            background: #f8f9fa;
            border-radius: 12px;
            padding: 5px;
            margin-bottom: 20px;
        }
        
        .feedback-page-tab {
            flex: 1;
            text-align: center;
            padding: 12px;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            color: var(--text-light);
        }
        
        .feedback-page-tab.active {
            background: white;
            color: var(--primary);
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        
        .feedback-page-tab i {
            display: block;
            font-size: 1.2rem;
            margin-bottom: 5px;
        }
        
        .feedback-mode-content {
            display: none;
        }
        
        .feedback-mode-content.active {
            display: block;
        }
        
        .feedback-info {
            background: rgba(255, 45, 142, 0.05);
            padding: 15px;
            border-radius: 12px;
            margin-bottom: 20px;
            border-left: 4px solid var(--primary);
        }
        
        .feedback-stats {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-weight: 600;
        }
        
        .feedback-tip {
            font-size: 0.9rem;
            color: var(--text-light);
            display: flex;
            align-items: center;
        }
        
        .feedback-tip i {
            margin-right: 8px;
            color: var(--primary);
        }
        
        .feedback-list {
            margin-bottom: 20px;
        }
        
        .feedback-item {
            background: white;
            border-radius: 12px;
            padding: 15px;
            margin-bottom: 15px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        
        .feedback-item-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }
        
        .feedback-item-title {
            font-weight: 600;
            font-size: 1.1rem;
        }
        
        .feedback-item-date {
            color: var(--text-light);
            font-size: 0.9rem;
        }
        
        .feedback-item-content {
            color: var(--text);
            line-height: 1.5;
            margin-bottom: 10px;
        }
        
        .feedback-item-photos {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
            gap: 10px;
            margin-top: 10px;
        }
        
        .feedback-photo {
            width: 100%;
            height: 80px;
            object-fit: cover;
            border-radius: 8px;
        }
        
        .vip-restricted {
            position: relative;
        }
        
        .vip-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(255,255,255,0.95);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 20px;
            border-radius: 12px;
        }
        
        .vip-overlay i {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 15px;
        }
        
        .vip-overlay h3 {
            margin-bottom: 10px;
            font-size: 1.2rem;
        }
        
        /* 牵线服务反馈页面样式 */
        #matchmakerFeedbackPage {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .matchmaker-feedback-content {
            background: white;
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
            overflow: hidden;
        }
        
        .matchmaker-feedback-header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
            color: white;
            padding: 30px;
            text-align: center;
        }
        
        .matchmaker-feedback-header h2 {
            margin: 0 0 10px 0;
            font-size: 2rem;
            font-weight: 700;
        }
        
        .matchmaker-feedback-header p {
            margin: 0;
            opacity: 0.9;
            font-size: 1.1rem;
        }
        
        .matchmaker-feedback-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            padding: 30px;
            background: #f8f9fa;
        }
        
        .stat-item {
            text-align: center;
            background: white;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }
        
        .stat-value {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 5px;
        }
        
        .stat-label {
            color: var(--text-light);
            font-size: 0.9rem;
        }
        
        .matchmaker-feedback-controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 30px;
            border-bottom: 1px solid #eee;
            background: white;
        }
        
        .feedback-filters {
            display: flex;
            gap: 15px;
            align-items: center;
        }
        
        .feedback-filters select {
            padding: 8px 15px;
            border: 1px solid #e0e0e0;
            border-radius: 6px;
            background: white;
        }
        
        .matchmaker-feedback-list {
            padding: 30px;
            min-height: 400px;
        }
        
        .matchmaker-feedback-item {
            background: white;
            border: 1px solid #eee;
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 20px;
            transition: all 0.3s;
        }
        
        .matchmaker-feedback-item:hover {
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transform: translateY(-2px);
        }
        
        .feedback-item-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .feedback-user-info {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .feedback-user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: 600;
            font-size: 1.2rem;
        }
        
        .feedback-user-name {
            font-weight: 600;
            color: var(--text);
        }
        
        .feedback-date {
            color: var(--text-light);
            font-size: 0.9rem;
        }
        
        .feedback-content {
            color: var(--text);
            line-height: 1.6;
            margin-bottom: 15px;
        }
        
        .feedback-rating {
            color: #ffc107;
            font-size: 1.2rem;
            margin-bottom: 10px;
        }
        
        .feedback-tags {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
        }
        
        .feedback-tag {
            background: var(--primary-light);
            color: var(--primary);
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 0.8rem;
            font-weight: 500;
        }
        
        /* 群聊服务反馈页面样式 */
        #groupFeedbackPage {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .group-feedback-content {
            background: white;
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
            overflow: hidden;
        }
        
        .group-feedback-header {
            background: linear-gradient(135deg, #4CAF50 0%, #45a049 100%);
            color: white;
            padding: 30px;
            text-align: center;
        }
        
        .group-feedback-header h2 {
            margin: 0 0 10px 0;
            font-size: 2rem;
            font-weight: 700;
        }
        
        .group-feedback-header p {
            margin: 0;
            opacity: 0.9;
            font-size: 1.1rem;
        }
        
        .group-feedback-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            padding: 30px;
            background: #f8f9fa;
        }
        
        .group-feedback-controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 30px;
            border-bottom: 1px solid #eee;
            background: white;
        }
        
        .group-feedback-list {
            padding: 30px;
            min-height: 400px;
        }
        
        .group-feedback-item {
            background: white;
            border: 1px solid #eee;
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 20px;
            transition: all 0.3s;
        }
        
        .group-feedback-item:hover {
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transform: translateY(-2px);
        }
        
        .group-feedback-item-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .group-feedback-user-info {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .group-feedback-user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(135deg, #4CAF50 0%, #45a049 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: 600;
            font-size: 1.2rem;
        }
        
        .group-feedback-user-name {
            font-weight: 600;
            color: var(--text);
        }
        
        .group-feedback-date {
            color: var(--text-light);
            font-size: 0.9rem;
        }
        
        .group-feedback-content-text {
            color: var(--text);
            line-height: 1.6;
            margin-bottom: 15px;
        }
        
        .group-feedback-rating {
            color: #ffc107;
            font-size: 1.2rem;
            margin-bottom: 10px;
        }
        
        .group-feedback-tags {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
        }
        
        .group-feedback-tag {
            background: #e8f5e8;
            color: #4CAF50;
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 0.8rem;
            font-weight: 500;
        }
        
        .vip-status-info {
            background: #fff3cd;
            border: 1px solid #ffeaa7;
            border-radius: 8px;
            padding: 15px;
            margin: 20px 30px;
            text-align: center;
        }
        
        .vip-status-info h4 {
            margin: 0 0 10px 0;
            color: #856404;
        }
        
        .vip-status-info p {
            margin: 0 0 15px 0;
            color: #856404;
        }
        
        .feedback-upload {
            background: #f8f9fa;
            border-radius: 12px;
            padding: 20px;
            margin-top: 20px;
        }
        
        .feedback-upload-title {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            font-weight: 600;
            font-size: 1.1rem;
        }
        
        .feedback-upload-title i {
            margin-right: 10px;
            color: var(--primary);
        }
        
        .photo-upload-area {
            border: 2px dashed #ddd;
            border-radius: 8px;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .photo-upload-area:hover {
            border-color: var(--primary);
        }
        
        .photo-upload-preview {
            color: var(--text-light);
        }
        
        .photo-upload-preview i {
            font-size: 2rem;
            margin-bottom: 10px;
            display: block;
        }
        
        .photo-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
            gap: 10px;
            margin-top: 15px;
        }
        
        .photo-item {
            position: relative;
        }
        
        .photo-item img {
            width: 100%;
            height: 100px;
            object-fit: cover;
            border-radius: 8px;
        }
        
        .photo-remove {
            position: absolute;
            top: 5px;
            right: 5px;
            background: rgba(0,0,0,0.7);
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            cursor: pointer;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--text);
        }
        
        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1rem;
            transition: all 0.3s;
        }
        
        .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(255, 45, 142, 0.1);
        }
        
        .success-section {
            text-align: center;
            padding: 20px 0;
        }
        
        /* 注册和编辑表单样式 */
        .register-form, .edit-form {
            text-align: left;
            padding: 15px 0;
        }
        
        .avatar-upload {
            text-align: center;
            margin-bottom: 20px;
        }
        
        .avatar-preview {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent) 0%, var(--primary) 100%);
            margin: 0 auto 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2.5rem;
            box-shadow: 0 8px 20px rgba(255, 45, 142, 0.3);
            overflow: hidden;
        }
        
        .avatar-preview img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .avatar-upload-btn {
            display: inline-block;
            padding: 8px 20px;
            background: var(--primary);
            color: white;
            border-radius: 20px;
            cursor: pointer;
            font-size: 0.9rem;
            transition: all 0.3s;
            transition: all 0.2s ease;
        }
        
        .avatar-upload-btn:active {
            transform: scale(0.95);
        }
        
        .gender-select {
            display: flex;
            gap: 10px;
            margin-bottom: 15px;
        }
        
        .gender-option {
            flex: 1;
            padding: 12px;
            text-align: center;
            border: 2px solid #f0f0f0;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            transition: all 0.2s ease;
        }
        
        .gender-option:active {
            transform: scale(0.98);
        }
        
        .gender-option.active {
            border-color: var(--primary);
            background: rgba(255, 45, 142, 0.05);
        }
        
        .form-actions {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }
        
        .form-actions .btn {
            flex: 1;
        }
        
        /* 声明和免责声明样式 */
        .agreement-section {
            margin: 15px 0;
            padding: 15px;
            background: #f8f9fa;
            border-radius: 8px;
            border: 1px solid #e9ecef;
        }
        
        .agreement-title {
            font-weight: bold;
            margin-bottom: 10px;
            color: #495057;
            font-size: 1rem;
        }
        
        .agreement-content {
            max-height: 120px;
            overflow-y: auto;
            font-size: 0.85rem;
            line-height: 1.4;
            color: #6c757d;
            padding: 10px;
            background: white;
            border-radius: 4px;
            border: 1px solid #dee2e6;
        }
        
        .agreement-checkbox {
            display: flex;
            align-items: center;
            margin-top: 10px;
            padding: 10px;
            background: white;
            border-radius: 4px;
            border: 1px solid #dee2e6;
        }
        
        .agreement-checkbox input[type="checkbox"] {
            margin-right: 8px;
            width: 16px;
            height: 16px;
        }
        
        .agreement-checkbox label {
            font-size: 0.85rem;
            color: #007bff;
            cursor: pointer;
            text-decoration: underline;
        }
        
        .agreement-checkbox label:hover {
            color: #0056b3;
        }
        
        .agreement-checkbox.required label::after {
            content: " *";
            color: #dc3545;
        }
        
        .agreement-error {
            color: #dc3545;
            font-size: 0.8rem;
            margin-top: 5px;
            display: none;
        }
        
        .login-prompt {
            text-align: center;
            margin-top: 20px;
            padding: 15px;
            background: rgba(255, 45, 142, 0.05);
            border-radius: 12px;
        }
        
        .login-prompt p {
            margin-bottom: 15px;
            color: var(--text-light);
        }
        
        /* 聊天记录折叠面板样式 */
        .chat-collapse {
            margin-top: 20px;
        }
        
        .collapse-item {
            border: 1px solid rgba(255, 45, 142, 0.1);
            border-radius: 12px;
            margin-bottom: 15px;
            overflow: hidden;
        }
        
        .collapse-header {
            padding: 15px;
            background: #f8f8f8;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            transition: all 0.3s;
            transition: all 0.2s ease;
        }
        
        .collapse-header:active {
            background: rgba(255, 45, 142, 0.1);
        }
        
        .collapse-header:hover {
            background: rgba(255, 45, 142, 0.05);
        }
        
        .collapse-header h3 {
            font-size: 1rem;
            margin: 0;
            display: flex;
            align-items: center;
        }
        
        .collapse-header h3 i {
            margin-right: 10px;
            color: var(--primary);
        }
        
        .collapse-header .collapse-arrow {
            transition: transform 0.3s;
        }
        
        .collapse-header.active .collapse-arrow {
            transform: rotate(180deg);
        }
        
        .collapse-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
            background: white;
        }
        
        .collapse-content.active {
            max-height: 500px;
        }
        
        .chat-messages {
            padding: 15px;
        }
        
        .chat-message {
            display: flex;
            margin-bottom: 15px;
        }
        
        .chat-message.self {
            justify-content: flex-end;
        }
        
        .chat-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent) 0%, var(--primary) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1rem;
            margin-right: 10px;
        }
        
        .chat-message.self .chat-avatar {
            margin-right: 0;
            margin-left: 10px;
            order: 2;
        }
        
        .message-content {
            background: #f0f0f0;
            padding: 10px 15px;
            border-radius: 18px;
            max-width: 70%;
        }
        
        .chat-message.self .message-content {
            background: var(--primary);
            color: white;
        }
        
        .message-sender {
            font-size: 0.8rem;
            font-weight: 600;
            margin-bottom: 5px;
            color: var(--text-light);
        }
        
        .chat-message.self .message-sender {
            text-align: right;
        }
        
        .message-time {
            font-size: 0.7rem;
            color: var(--text-light);
            margin-top: 5px;
            text-align: right;
        }
        
        .chat-message.self .message-time {
            text-align: left;
        }
        
        /* 聊天记录页面样式 */
        .chat-header {
            display: flex;
            align-items: center;
            padding: 15px;
            border-bottom: 1px solid rgba(255, 45, 142, 0.1);
        }
        
        .back-button {
            background: none;
            border: none;
            font-size: 1.2rem;
            color: var(--primary);
            cursor: pointer;
            margin-right: 15px;
            transition: all 0.2s ease;
        }
        
        .back-button:active {
            transform: scale(0.9);
        }
        
        .chat-title {
            font-size: 1.1rem;
            font-weight: 600;
        }
        
        .chat-section {
            max-height: 500px;
            overflow-y: auto;
            padding: 15px;
        }
        
        .no-chat-data {
            text-align: center;
            padding: 40px 20px;
            color: var(--text-light);
        }
        
        .no-chat-data i {
            font-size: 3rem;
            margin-bottom: 15px;
            color: #e0e0e0;
        }
        
        /* 优化选择群聊样式 */
        .group-card {
            background: linear-gradient(135deg, #f8f8f8, #f0f0f0);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 15px;
            transition: all 0.3s;
            border: 1px solid rgba(255, 45, 142, 0.1);
            text-align: center;
        }
        
        .group-card:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 15px rgba(0,0,0,0.1);
        }
        
        .group-card.active {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
        }
        
        .group-icon {
            font-size: 2.5rem;
            margin-bottom: 10px;
            color: var(--primary);
        }
        
        .group-card.active .group-icon {
            color: white;
        }
        
        .group-name {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .group-members {
            font-size: 0.85rem;
            color: var(--text-light);
        }
        
        .group-card.active .group-members {
            color: rgba(255, 255, 255, 0.8);
        }
        
        /* 红娘牵线功能样式 */
        .matchmaker-section {
            text-align: center;
        }
        
        .matchmaker-card {
            background: #fefefe;
            border-radius: 20px;
            padding: 24px;
            margin-bottom: 20px;
            text-align: center;
            box-shadow: 0 2px 12px rgba(0, 0, 0, 0.05);
            border: 1px solid rgba(0, 0, 0, 0.08);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .matchmaker-card:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 24px rgba(0, 0, 0, 0.08);
        }
        
        .matchmaker-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent) 0%, var(--primary) 100%);
            margin: 0 auto 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2.5rem;
            box-shadow: 0 8px 20px rgba(79, 70, 229, 0.3);
            overflow: hidden;
            border: 4px solid white;
        }
        
        .matchmaker-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .matchmaker-name {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 8px;
            color: var(--text);
        }
        
        .matchmaker-info {
            display: flex;
            justify-content: center;
            margin-bottom: 15px;
            color: var(--text-light);
            font-size: 0.9rem;
        }
        
        .matchmaker-info span {
            margin: 0 10px;
        }
        
        /* VIP开通提示样式 */
        .matchmaker-vip-prompt {
            background: linear-gradient(135deg, #fff5f8, #fff0f5);
            border-radius: 15px;
            padding: 25px;
            margin: 20px 0;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            border: 1px solid rgba(255, 45, 142, 0.1);
        }
        
        /* 信任徽章样式 */
        .trust-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-bottom: 25px;
            justify-content: center;
            padding: 15px;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
        }
        
        .trust-badges .badge {
            display: inline-flex;
            align-items: center;
            padding: 8px 15px;
            background-color: rgba(255, 107, 157, 0.12);
            border-radius: 24px;
            font-size: 0.9rem;
            font-weight: 500;
            color: var(--text);
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 107, 157, 0.2);
        }
        
        .trust-badges .badge:hover {
            background-color: rgba(255, 107, 157, 0.25);
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(255, 107, 157, 0.2);
            border-color: rgba(255, 107, 157, 0.4);
        }
        
        .trust-badges .badge i {
            margin-right: 7px;
            color: var(--success);
            font-size: 1.1rem;
        }
        
        /* 限时优惠样式 */
        .limited-time-offer {
            background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
            color: #fff;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(255, 154, 158, 0.3);
        }
        
        .limited-time-offer i {
            color: #fff0f3;
            font-size: 1.2rem;
            margin-right: 8px;
        }
        
        .countdown-timer {
            margin-top: 8px;
            font-weight: bold;
            font-size: 0.9rem;
            color: #fff0f3;
        }
        
        /* 价格样式 */
        .matchmaker-payment-amount {
            position: relative;
            text-align: center;
            margin-bottom: 25px;
        }
        
        .current-price {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .original-price {
            font-size: 1.2rem;
            color: #999;
            text-decoration: line-through;
            margin-left: 10px;
        }
        
        .discount-tag {
            background-color: #ff4560;
            color: white;
            padding: 3px 10px;
            border-radius: 15px;
            font-size: 0.8rem;
            margin-left: 10px;
        }
        
        /* 特权特性样式增强 */
        .payment-feature {
            display: flex;
            align-items: center;
            margin-bottom: 12px;
            padding: 8px 15px;
            border-radius: 8px;
            transition: all 0.3s ease;
        }
        
        .payment-feature:hover {
            background-color: rgba(255, 45, 142, 0.05);
            transform: translateX(5px);
        }
        
        .highlight-feature {
            background: linear-gradient(135deg, rgba(255, 45, 142, 0.1), rgba(255, 45, 142, 0.05));
            border-left: 3px solid var(--primary);
        }
        
        .payment-feature i {
            font-size: 1.2rem;
            margin-right: 12px;
            width: 24px;
            text-align: center;
        }
        
        /* 成功案例样式 */
        .success-stories {
            margin: 30px 0;
            padding: 20px;
            background-color: #fff5f8;
            border-radius: 12px;
        }
        
        .success-stories h4 {
            color: var(--primary);
            margin-bottom: 15px;
            font-size: 1.1rem;
            text-align: center;
        }
        
        .stories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
        }
        
        .story-item {
            background: white;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
            transition: transform 0.3s ease;
        }
        
        .story-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }
        
        .story-text {
            color: #333;
            font-style: italic;
            margin-bottom: 10px;
            line-height: 1.5;
        }
        
        .story-author {
            color: #666;
            font-size: 0.9rem;
            text-align: right;
        }
        
        /* 用户评价样式 */
        .user-reviews {
            margin: 25px 0;
            text-align: center;
        }
        
        .review-stats {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
        }
        
        .rating {
            display: flex;
            align-items: baseline;
            gap: 10px;
        }
        
        .stars {
            color: #ffb400;
            font-size: 1.8rem;
            letter-spacing: 3px;
        }
        
        .rating-number {
            font-size: 1.5rem;
            font-weight: bold;
            color: #333;
        }
        
        .review-count {
            color: #666;
            font-size: 0.9rem;
        }
        
        .vip-promo-header h3 {
            color: var(--primary);
            margin-bottom: 10px;
            font-size: 1.3rem;
        }
        
        .vip-promo-header p {
            color: var(--text-light);
            margin-bottom: 20px;
            font-size: 0.95rem;
        }
        
        .vip-benefits {
            margin: 20px 0;
        }
        
        .benefits-list {
            list-style: none;
            padding: 0;
        }
        
        .benefits-list li {
            display: flex;
            align-items: flex-start;
            margin-bottom: 12px;
            color: var(--text-primary);
            font-size: 0.9rem;
        }
        
        .benefits-list li i {
            color: var(--primary);
            margin-right: 10px;
            margin-top: 2px;
        }
        
        .vip-price {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-top: 25px;
        }
        
        .price-amount {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .price-period {
            margin-left: 5px;
            color: var(--text-light);
            font-size: 1rem;
        }
        
        /* 资料上传表单样式 */
        .matchmaker-profile-form {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin: 20px 0;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            border: 1px solid rgba(255, 45, 142, 0.1);
        }
        
        .form-header h3 {
            color: var(--primary);
            margin-bottom: 8px;
            font-size: 1.3rem;
        }
        
        .form-header p {
            color: var(--text-light);
            margin-bottom: 20px;
            font-size: 0.95rem;
        }
        
        .form-content {
            text-align: left;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--text-primary);
        }
        
        .form-group input[type="text"],
        .form-group input[type="number"],
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 10px 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            background: white;
            transition: border-color 0.3s;
        }
        
        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
        }
        
        .form-group input[type="file"] {
            border: none;
            padding: 5px 0;
        }
        
        .preferences-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
        }
        
        .preference-item label {
            font-size: 0.9rem;
            margin-bottom: 5px;
        }
        
        /* 资料摘要样式 */
        .matchmaker-profile-summary {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin: 20px 0;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            border: 1px solid rgba(255, 45, 142, 0.1);
        }
        
        .summary-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .summary-header h4 {
            color: var(--primary);
            font-size: 1.2rem;
            margin: 0;
        }
        
        .profile-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
        }
        
        .info-item {
            display: flex;
            flex-direction: column;
            text-align: left;
        }
        
        .info-label {
            font-size: 0.85rem;
            color: var(--text-light);
            margin-bottom: 5px;
        }
        
        .info-value {
            font-weight: 500;
            color: var(--text-primary);
            font-size: 1rem;
        }
        
        /* 匹配结果样式 */
        .matchmaker-match-result {
            background: linear-gradient(135deg, #f0f9ff, #f0f5ff);
            border-radius: 15px;
            padding: 25px;
            margin: 20px 0;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            border: 1px solid rgba(59, 130, 246, 0.1);
        }
        
        .result-header h4 {
            color: #3b82f6;
            font-size: 1.2rem;
            margin-bottom: 15px;
        }
        
        .match-status {
            margin: 20px 0;
        }
        
        .status-message {
            font-size: 1.1rem;
            color: var(--text-primary);
            margin-bottom: 10px;
        }
        
        .status-tip {
            font-size: 0.9rem;
            color: var(--text-light);
        }
        
        /* VIP限制样式 */
        .vip-restricted {
            opacity: 0.6;
            pointer-events: none;
            position: relative;
        }
        
        .vip-restricted::after {
            content: 'VIP专享';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: var(--primary);
            color: white;
            padding: 5px 10px;
            border-radius: 10px;
            font-size: 0.8rem;
            font-weight: 500;
        }
        
        .matchmaker-tags {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 20px;
        }
        
        .matchmaker-tag {
            background: rgba(255, 45, 142, 0.1);
            color: var(--primary);
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 0.8rem;
        }
        
        .matchmaker-actions {
            display: flex;
            gap: 15px;
        }
        
        .matchmaker-actions .btn {
            flex: 1;
            padding: 12px;
        }
        
        .matchmaker-like {
            background: linear-gradient(135deg, #07c160 0%, #0baa53 100%);
            color: white;
        }
        
        .matchmaker-skip {
            background: linear-gradient(to bottom, #f8f8f8, #f0f0f0);
            color: var(--text);
        }
        
        .matchmaker-login-prompt {
            text-align: center;
            padding: 40px 20px;
        }
        
        .matchmaker-login-prompt i {
            font-size: 4rem;
            color: #e0e0e0;
            margin-bottom: 20px;
        }
        
        .matchmaker-login-prompt h3 {
            margin-bottom: 15px;
            color: var(--text-light);
        }
        
        .matchmaker-login-prompt p {
            margin-bottom: 20px;
            color: var(--text-light);
        }
        
        .matchmaker-stats {
            display: flex;
            justify-content: space-around;
            margin: 20px 0;
            padding: 15px;
            background: rgba(255, 45, 142, 0.05);
            border-radius: 12px;
        }
        
        .matchmaker-stat {
            text-align: center;
        }
        
        .matchmaker-stat-value {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .matchmaker-stat-label {
            font-size: 0.85rem;
            color: var(--text-light);
        }
        
        /* 红娘牵线支付样式 */
        .matchmaker-payment {
            background: linear-gradient(135deg, #fefefe 0%, #f9fafb 100%);
            border-radius: 20px;
            padding: 25px;
            margin: 20px 0;
            text-align: center;
            border: 1px solid rgba(0, 0, 0, 0.08);
            box-shadow: 0 2px 12px rgba(0, 0, 0, 0.05);
        }
        
        .matchmaker-payment-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: var(--text);
        }
        
        .matchmaker-payment-amount {
            font-size: 2.8rem;
            font-weight: bold;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            margin: 20px 0;
        }
        
        .matchmaker-payment-features {
            text-align: left;
            margin: 25px 0;
        }
        
        .payment-feature {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            font-size: 0.95rem;
            color: var(--text);
        }
        
        .payment-feature i {
            color: var(--primary);
            margin-right: 10px;
            font-size: 1.1rem;
        }
        
        .matchmaker-payment-methods {
            display: flex;
            gap: 10px;
            margin: 20px 0;
        }
        
        .matchmaker-payment-method {
            flex: 1;
            padding: 15px;
            text-align: center;
            border: 2px solid #f0f0f0;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s;
            transition: all 0.2s ease;
            /* 优化移动端触摸体验 */
            -webkit-tap-highlight-color: transparent;
            touch-action: manipulation;
        }
        
        .matchmaker-payment-method:active {
            transform: scale(0.98);
        }
        
        .matchmaker-payment-method.active {
            border-color: rgba(79, 70, 229, 0.6);
            background: rgba(79, 70, 229, 0.03);
        }
        
        .matchmaker-payment-method i {
            font-size: 2rem;
            margin-bottom: 10px;
            color: var(--primary);
        }
        
        .matchmaker-payment-form {
            display: none;
            margin-top: 20px;
        }
        
        .matchmaker-payment-form.active {
            display: block;
        }
        
        /* 客服系统样式 */

        

        
        /* 群聊选择折叠区域样式 */
        .city-collapse {
            margin-top: 15px;
        }
        
        .collapse-toggle {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 12px 15px;
            background: linear-gradient(to bottom, #f8f8f8, #f0f0f0);
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s;
            margin-bottom: 10px;
            transition: all 0.2s ease;
        }
        
        .collapse-toggle:active {
            background: rgba(255, 45, 142, 0.1);
            transform: scale(0.98);
        }
        
        .collapse-toggle:hover {
            background: rgba(255, 45, 142, 0.05);
        }
        
        .collapse-toggle i {
            transition: transform 0.3s;
        }
        
        .collapse-toggle.active i {
            transform: rotate(180deg);
        }
        
        .collapse-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
        }
        
        .collapse-content.active {
            max-height: 500px;
        }
        
        /* 城市选择和聊天记录分离样式 */
        .view-chat-btn {
            margin-top: 15px;
            padding: 12px;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 12px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
            transition: all 0.2s ease;
        }
        
        .view-chat-btn:active {
            transform: scale(0.98);
        }
        
        .view-chat-btn:disabled {
            background: #ccc;
            cursor: not-allowed;
        }
        
        .view-chat-btn:not(:disabled):hover {
            background: var(--secondary);
        }
        
        /* 红娘牵线用户卡片样式优化 */
        .matchmaker-user-card {
            background: linear-gradient(135deg, #fcfcfc, #f8f9fa);
            border-radius: 20px;
            padding: 20px;
            margin-bottom: 20px;
            text-align: center;
            box-shadow: 0 2px 12px rgba(0,0,0,0.04);
            border: 1px solid rgba(0, 0, 0, 0.06);
            position: relative;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .matchmaker-user-card:active {
            transform: scale(0.98);
        }

        /* 男女用户卡片样式区分 */
        .user-card-male {
            border: 2px solid rgba(74, 144, 226, 0.6) !important;
            box-shadow: 0 4px 15px rgba(74, 144, 226, 0.2) !important;
        }

        .user-card-female {
            border: 2px solid #e91e63 !important;
            box-shadow: 0 4px 15px rgba(233, 30, 99, 0.3) !important;
        }

        /* 性别徽章样式 */
        .gender-badge {
            position: absolute;
            bottom: 5px;
            right: 5px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 50%;
            padding: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }

        /* 性别图标样式 */
        .gender-icon {
            font-size: 16px;
        }

        .male-icon {
            color: #4a90e2;
        }

        .female-icon {
            color: #e91e63;
        }

        /* 性别文字样式 */
        .gender-text {
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .matchmaker-user-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            margin: 0 auto 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            border: 3px solid var(--primary);
            box-shadow: 0 8px 20px rgba(255, 45, 142, 0.3);
        }
        
        .matchmaker-user-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .matchmaker-user-name {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .matchmaker-user-info {
            display: flex;
            justify-content: center;
            margin-bottom: 15px;
            color: var(--text-light);
            font-size: 0.9rem;
        }
        
        .matchmaker-user-info span {
            margin: 0 10px;
        }
        
        .matchmaker-user-tags {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 20px;
        }
        
        .matchmaker-user-tag {
            background: rgba(255, 45, 142, 0.1);
            color: var(--primary);
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 0.8rem;
        }
        
        .matchmaker-user-actions {
            display: flex;
            gap: 15px;
        }
        
        .matchmaker-user-actions .btn {
            flex: 1;
            padding: 12px;
        }
        
        .matchmaker-user-like {
            background: linear-gradient(135deg, #07c160 0%, #0baa53 100%);
            color: white;
        }
        
        .matchmaker-user-skip {
            background: linear-gradient(to bottom, #f8f8f8, #f0f0f0);
            color: var(--text);
        }
        
        .matchmaker-user-bio {
            background: rgba(255, 45, 142, 0.05);
            padding: 15px;
            border-radius: 12px;
            margin: 20px 0;
            font-size: 0.9rem;
            color: var(--text-light);
            border-left: 4px solid var(--primary);
        }
        
        /* 红娘牵线用户列表样式 */
        .matchmaker-user-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .matchmaker-user-list-item {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 20px;
            text-align: center;
            box-shadow: var(--shadow);
            border: 1px solid rgba(79, 70, 229, 0.1);
            transition: all 0.3s;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .matchmaker-user-list-item:active {
            transform: scale(0.98);
        }
        
        .matchmaker-user-list-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 40px rgba(79, 70, 229, 0.2);
        }
        
        .matchmaker-user-list-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            margin: 0 auto 10px;
            overflow: hidden;
            border: 3px solid var(--primary);
            box-shadow: 0 4px 15px rgba(79, 70, 229, 0.3);
        }
        
        .matchmaker-user-list-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .matchmaker-user-list-name {
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 5px;
            color: var(--text);
        }
        
        .matchmaker-user-list-info {
            color: var(--text-light);
            font-size: 0.85rem;
            margin-bottom: 10px;
        }
        
        .matchmaker-user-list-tags {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 5px;
            margin-bottom: 10px;
        }
        
        .matchmaker-user-list-tag {
            background: rgba(255, 45, 142, 0.1);
            color: var(--primary);
            padding: 3px 8px;
            border-radius: 12px;
            font-size: 0.7rem;
        }
        
        /* 新增：用户详情页面样式 */
        .user-detail-section {
            text-align: center;
            padding: 20px 0;
        }
        
        .user-detail-avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            margin: 0 auto 20px;
            overflow: hidden;
            border: 5px solid var(--primary);
            box-shadow: 0 10px 30px rgba(255, 45, 142, 0.3);
        }
        
        .user-detail-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .user-detail-name {
            font-size: 1.6rem;
            font-weight: 700;
            margin-bottom: 10px;
            color: var(--primary);
        }
        
        .user-detail-info {
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
            color: var(--text-light);
            font-size: 1rem;
        }
        
        .user-detail-info span {
            margin: 0 15px;
        }
        
        .user-detail-bio {
            background: rgba(255, 45, 142, 0.05);
            padding: 20px;
            border-radius: 15px;
            margin: 25px 0;
            font-size: 1rem;
            color: var(--text);
            border-left: 4px solid var(--primary);
            text-align: left;
        }
        
        .user-detail-tags {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 25px;
        }
        
        .user-detail-tag {
            background: rgba(255, 45, 142, 0.1);
            color: var(--primary);
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
        }
        
        .user-detail-actions {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .user-detail-actions .btn {
            flex: 1;
            padding: 15px;
        }
        
        /* 新增：城市选择区域样式 */
        .matchmaker-city-selector {
            margin: 20px 0;
            padding: 20px;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.95), rgba(255, 245, 250, 0.95));
            border-radius: 20px;
            border: 1px solid rgba(255, 105, 180, 0.2);
            box-shadow: 0 4px 15px rgba(255, 105, 180, 0.1);
            backdrop-filter: blur(10px);
        }
        
        .matchmaker-city-selector-title {
            font-size: 1.25rem;
            font-weight: 700;
            margin-bottom: 20px;
            color: #333;
            text-align: center;
            font-family: 'PingFang SC', 'Microsoft YaHei', sans-serif;
            letter-spacing: 0.5px;
        }
        
        .matchmaker-city-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 12px;
        }
        
        .matchmaker-city-item {
            padding: 12px 8px;
            text-align: center;
            background: white;
            border-radius: 12px;
            font-size: 0.9rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            color: #555;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
        }
        
        .matchmaker-city-item:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 15px rgba(255, 105, 180, 0.2);
            border-color: rgba(255, 105, 180, 0.3);
        }
        
        .matchmaker-city-item:active {
            transform: scale(0.97);
        }
        
        .matchmaker-city-item.active {
            background: linear-gradient(135deg, #ff69b4, #ff1493);
            color: white;
            border-color: #ff69b4;
            box-shadow: 0 6px 20px rgba(255, 105, 180, 0.4);
        }

        /* 性别筛选区域样式 */
        .matchmaker-gender-filter {
            margin: 20px 0;
            padding: 20px;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.95), rgba(245, 245, 255, 0.95));
            border-radius: 20px;
            border: 1px solid rgba(100, 149, 237, 0.2);
            box-shadow: 0 4px 15px rgba(100, 149, 237, 0.1);
        }

        .matchmaker-gender-filter-title {
            font-size: 1.25rem;
            font-weight: 700;
            margin-bottom: 20px;
            color: #333;
            text-align: center;
            font-family: 'PingFang SC', 'Microsoft YaHei', sans-serif;
            letter-spacing: 0.5px;
        }

        .matchmaker-gender-buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
        }

        .gender-btn {
            flex: 1;
            max-width: 150px;
            padding: 15px 20px;
            border: 2px solid transparent;
            border-radius: 15px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            background: white;
            color: #555;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
        }

        .gender-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.15);
        }

        .gender-btn.active {
            color: white;
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.2);
        }

        .gender-btn.gender-all.active {
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-color: #667eea;
        }

        .gender-btn.gender-male {
            color: #4a90e2;
        }

        .gender-btn.gender-male:hover {
            border-color: rgba(74, 144, 226, 0.3);
            box-shadow: 0 4px 15px rgba(74, 144, 226, 0.2);
        }

        .gender-btn.gender-male.active {
            background: linear-gradient(135deg, #4a90e2, #357abd);
            border-color: #4a90e2;
            color: white;
        }

        .gender-btn.gender-female {
            color: #e91e63;
        }

        .gender-btn.gender-female:hover {
            border-color: rgba(233, 30, 99, 0.3);
            box-shadow: 0 4px 15px rgba(233, 30, 99, 0.2);
        }

        .gender-btn.gender-female.active {
            background: linear-gradient(135deg, #e91e63, #c2185b);
            border-color: #e91e63;
            color: white;
        }

        .gender-btn i {
            font-size: 1.2rem;
        }
        
        /* 新增：VIP限制提示样式 */
        .vip-restricted {
            position: relative;
        }
        
        .vip-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.7);
            border-radius: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: white;
            text-align: center;
            padding: 20px;
            z-index: 10;
        }
        
        .vip-overlay i {
            font-size: 3rem;
            margin-bottom: 15px;
            color: var(--primary);
        }
        
        .vip-overlay h3 {
            margin-bottom: 10px;
            font-size: 1.3rem;
        }
        
        .vip-overlay p {
            margin-bottom: 20px;
            font-size: 0.9rem;
            opacity: 0.9;
        }
        
        /* 新增：脉冲动画 */
        @keyframes pulse {
            0% {
                box-shadow: 0 0 0 0 rgba(255, 45, 142, 0.7);
            }
            70% {
                box-shadow: 0 0 0 10px rgba(255, 45, 142, 0);
            }
            100% {
                box-shadow: 0 0 0 0 rgba(255, 45, 142, 0);
            }
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
        
        /* 新增：登录类型切换样式 */
        .login-type-tabs {
            display: flex;
            margin-bottom: 20px;
            border-bottom: 1px solid #e0e0e0;
        }
        
        .login-type-tab {
            flex: 1;
            padding: 12px 0;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
            border-bottom: 3px solid transparent;
            font-weight: 600;
        }
        
        .login-type-tab.active {
            border-bottom: 3px solid var(--primary);
            color: var(--primary);
        }
        
        /* 新增：订单查询样式 */
        .order-search {
            margin-bottom: 20px;
            display: flex;
            gap: 10px;
        }
        
        .order-search-input {
            flex: 1;
            padding: 12px 15px;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1rem;
        }
        
        .order-search-btn {
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 8px;
            padding: 0 20px;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .order-search-btn:active {
            transform: scale(0.95);
        }
        
        .order-details {
            background: rgba(255, 45, 142, 0.05);
            border-radius: 12px;
            padding: 20px;
            margin-top: 20px;
            display: none;
        }
        
        .order-details.active {
            display: block;
        }
        
        .order-detail-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            padding-bottom: 10px;
            border-bottom: 1px solid rgba(255, 45, 142, 0.1);
        }
        
        .order-detail-label {
            font-weight: 600;
            color: var(--text-light);
        }
        
        .order-detail-value {
            color: var(--text);
        }
        
        .no-order-found {
            text-align: center;
            padding: 40px 20px;
            color: var(--text-light);
        }
        
        .no-order-found i {
            font-size: 3rem;
            margin-bottom: 15px;
            color: #e0e0e0;
        }
        
        /* 客服系统样式 */
        .customer-service-container {
            position: fixed;
            bottom: 80px;
            right: 20px;
            z-index: 1000;
        }
        
        .customer-service-btn {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 12px 20px;
            border-radius: 25px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 14px;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .customer-service-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(102, 126, 234, 0.6);
        }
        
        .customer-service-chat {
            position: absolute;
            bottom: 60px;
            right: 0;
            width: 320px;
            background: white;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            overflow: hidden;
        }
        
        .chat-header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .chat-title {
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: 500;
        }
        
        .chat-close {
            background: none;
            border: none;
            color: white;
            cursor: pointer;
            font-size: 16px;
            padding: 5px;
        }
        
        .chat-messages {
            height: 300px;
            overflow-y: auto;
            padding: 15px;
            background: #f8f9fa;
        }
        
        .message {
            margin-bottom: 15px;
            display: flex;
        }
        
        .customer-message {
            justify-content: flex-start;
        }
        
        .user-message {
            justify-content: flex-end;
        }
        
        .message-content {
            max-width: 80%;
            background: white;
            padding: 10px 15px;
            border-radius: 18px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        
        .customer-message .message-content {
            background: #667eea;
            color: white;
        }
        
        .user-message .message-content {
            background: #e9ecef;
            color: #333;
        }
        
        .system-message {
            justify-content: center;
        }
        
        .system-message .message-content {
            background: #fff3cd;
            color: #856404;
            border: 1px solid #ffeaa7;
            font-size: 12px;
            padding: 8px 12px;
            max-width: 60%;
        }
        
        .message-text {
            margin-bottom: 5px;
            line-height: 1.4;
        }
        
        .message-time {
            font-size: 11px;
            opacity: 0.7;
        }
        
        .chat-input-container {
            padding: 15px;
            background: white;
            border-top: 1px solid #e9ecef;
        }
        
        .chat-input-wrapper {
            display: flex;
            gap: 10px;
            align-items: center;
        }
        
        .chat-input {
            flex: 1;
            padding: 10px 15px;
            border: 1px solid #ddd;
            border-radius: 20px;
            outline: none;
            font-size: 14px;
        }
        
        .chat-input:focus {
            border-color: #667eea;
        }
        
        .chat-send-btn {
            background: #667eea;
            color: white;
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background 0.3s ease;
        }
        
        .chat-send-btn:hover {
            background: #5a6fd8;
        }
        
        .chat-send-btn:disabled {
            background: #ccc;
            cursor: not-allowed;
        }
    </style>
</head>
<body>
    <header>
        <div class="user-info">
            <div class="user-avatar" id="userAvatar">
                <i class="fas fa-user"></i>
            </div>
            <div class="user-details">
                <div class="user-name" id="headerUserName">请登录</div>
                <div class="user-level" id="headerUserLevel">普通用户</div>
            </div>
            <div class="notification-icon" id="notificationIcon">
                <i class="fas fa-bell"></i>
            </div>
        </div>
        <div class="header-content">
                <h1 id="mainTitle">进微信同城群聊 · 同城交友</h1>
                <p>想认识同城好友？查看附近当地微信群聊天记录，开启同城交友</p>
            </div>
    </header>
    
    <div class="container">
        <!-- 城市选择区域 - 现代化优化版 -->
        <div class="card city-selector-card modern-card">
            <div class="section-title modern-title">
                <i class="fas fa-map-marker-alt location-icon"></i> 
                <span class="title-text gradient-text">进微信同城群聊</span>
                <div class="location-badge">
                    <i class="fas fa-users"></i>
                    <span id="onlineCount" class="online-count">417</span>
                </div>
            </div>
            
            <div class="city-selector city-selector-modern">
                <!-- 当前选择显示 - 更美观的卡片样式 -->
                <div class="current-selection modern-selection" id="currentSelection">
                    <div class="selection-header">
                        <i class="fas fa-map-pin selection-icon gradient-text"></i>
                        <span class="selection-label gradient-text">同城位置</span>
                    </div>
                    <div class="selection-value-container">
                        <span class="selection-value modern-value gradient-text" id="selectionValue">未选择城市</span>
                        <div class="location-indicator">
                            <i class="fas fa-caret-right indicator-icon gradient-text"></i>
                        </div>
                    </div>
                </div>
                
                <!-- 省份列表 - 现代化横向滚动 -->
                <div class="province-list-wrapper">
                    <div class="scroll-hint">
                        <span>滑动选择省份</span>
                        <i class="fas fa-hand-pointer"></i>
                    </div>
                    <div class="province-list-scrollable modern-scrollable">
                        <div class="province-list modern-province-list" id="provinceList">
                            <!-- 省份列表将通过JS动态生成 -->
                        </div>
                    </div>
                </div>
                
                <!-- 城市搜索区域 - 优化搜索体验 -->
                <div class="city-search city-search-modern">
                    <div class="search-input-wrapper modern-search">
                        <i class="fas fa-search search-icon"></i>
                        <input type="text" id="citySearchInput" placeholder="🔍 搜索城市名称或拼音..." class="modern-search-input" style="font-weight: 500;">
                    </div>
                    <div class="search-results" id="searchResultsContainer">
                        <!-- 搜索结果将动态生成 -->
                    </div>
                </div>
                
                <!-- 城市折叠区域 - 更优雅的交互设计 -->
                <div class="city-collapse panel-collapse modern-collapse">
                    <div class="collapse-toggle panel-header modern-toggle" id="cityCollapseToggle">
                        <div class="toggle-left">
                            <i class="fas fa-building city-icon"></i>
                            <span>选择城市</span>
                            <span class="city-count">(<span id="cityCountDisplay">0</span>个)</span>
                        </div>
                        <div class="toggle-right">
                            <span class="toggle-text">展开</span>
                            <i class="fas fa-chevron-down toggle-icon"></i>
                        </div>
                    </div>
                    <div class="collapse-content panel-content modern-content" id="cityCollapseContent">
                        <!-- 热门城市快速选择 - 更美观的设计 -->
                        <div class="hot-cities-section modern-hot-cities">
                            <div class="hot-cities-header">
                                <i class="fas fa-fire hot-icon"></i>
                                <div class="hot-cities-label">热门城市</div>
                            </div>
                            <div class="hot-cities modern-hot-list" id="hotCitiesList">
                                <!-- 热门城市将动态生成 -->
                            </div>
                        </div>
                        
                        <!-- 城市列表 - 网格优化 -->
                        <div class="city-grid modern-city-grid" id="cityGrid">
                            <!-- 城市列表将通过JS动态生成 -->
                        </div>
                    </div>
                </div>
                
                <!-- 进微信同城群聊按钮 -->
                <button class="view-chat-btn" id="viewChatBtn" disabled>
                    <i class="fab fa-weixin"></i>
                    <span>进微信同城群聊</span>
                </button>
            </div>
        </div>
        
        <!-- 支付信息区域 -->
        <div class="card">
            <div class="section-title gradient-text">
                <i class="fas fa-gem"></i> 进微信同城群聊特权
            </div>
            <div class="payment-info">
                <p class="enhanced-paragraph"><span class="highlight">进微信同城群聊</span>，认识更多同城好友</p>
                <div class="amount gradient-text">¥39.99</div>
                <p class="enhanced-paragraph">支付后即可<span class="highlight">解锁当地微信群聊天记录</span>，开启同城交友之旅</p>
                
                <!-- 信任标识 -->
                <div class="trust-badges">
                    <div class="trust-badge gradient-bg">
                        <i class="fas fa-shield-alt"></i>
                        <span class="badge-text">安全认证</span>
                    </div>
                    <div class="trust-badge gradient-bg">
                        <i class="fas fa-lock"></i>
                        <span class="badge-text">隐私保护</span>
                    </div>
                    <div class="trust-badge gradient-bg">
                        <i class="fas fa-check-circle"></i>
                        <span class="badge-text">同城真实</span>
                    </div>
                    <div class="trust-badge gradient-bg">
                        <i class="fas fa-users"></i>
                        <span class="badge-text">超10万用户</span>
                    </div>
                </div>
            </div>
            
            <!-- 支付方式选择 -->
            <div class="payment-methods">
                <div class="payment-method active" data-method="alipay">
                    <i class="fab fa-alipay"></i>
                    <div>支付宝</div>
                </div>
                <div class="payment-method" data-method="wxpay">
                    <i class="fab fa-weixin"></i>
                    <div>微信支付</div>
                </div>
            </div>
            
            <!-- 支付宝支付表单 -->
            <div class="payment-form active" id="alipayForm">
                <button class="btn btn-primary" id="alipayBtn">
                    <i class="fab fa-alipay"></i>
                    <span>立即进微信同城群聊 ¥39.99</span>
                </button>
            </div>
            
            <!-- 微信支付表单 -->
            <div class="payment-form" id="wxpayForm">
                <button class="btn btn-primary" id="wxpayBtn">
                    <i class="fab fa-weixin"></i>
                    <span>立即进微信同城群聊 ¥39.99</span>
                </button>
            </div>
            
            <button class="btn btn-secondary" id="orderBtn">查看我的订单</button>
            
            <!-- 声明和免责声明 -->
            <div class="agreement-section">
                <div class="agreement-title">
                    <i class="fas fa-info-circle"></i> 法律声明与免责声明
                </div>
                
                <div class="agreement-content hidden" id="paymentAgreementContent">
                    <div class="agreement-summary">
                        <p><strong>重要提示：</strong>在使用本平台服务前，请仔细阅读以下声明内容。</p>
                        <p>本平台严格遵守国家法律法规，提供婚恋交友信息服务。用户需对自身行为承担法律责任，平台仅提供信息交流服务...</p>
                    </div>
                    
                    <div class="agreement-details">
                        <p><strong>法律声明：</strong></p>
                        <ul>
                            <li>本平台严格遵守《中华人民共和国网络安全法》、《个人信息保护法》、《民法典》等相关法律法规</li>
                            <li>用户需保证所提供信息的真实性和合法性，不得冒用他人身份或提供虚假信息</li>
                            <li>禁止发布涉及色情、暴力、赌博、诈骗、传销等违法信息及不当言论</li>
                            <li>用户需对自身行为承担全部法律责任，包括但不限于民事、行政、刑事责任</li>
                            <li>平台有权对违规内容进行删除，对违规用户进行警告、限制功能或封禁处理</li>
                            <li>用户应妥善保管账号信息，不得转让、出租或出借账号给他人使用</li>
                            <li>禁止利用平台进行商业推广、广告宣传等未经授权的商业活动</li>
                            <li>用户应遵守平台社区规范，维护良好的交流环境</li>
                        </ul>
                        
                        <p><strong>免责声明：</strong></p>
                        <ul>
                            <li>本平台仅提供信息交流服务，不承担用户间纠纷责任，用户应自行协商解决</li>
                            <li>用户需自行判断信息真实性，平台不保证用户发布信息的准确性、完整性和时效性</li>
                            <li>因用户行为造成的任何损失，包括但不限于财产损失、人身伤害等，平台概不负责</li>
                            <li>平台有权根据法律法规变化或业务需要调整服务内容，恕不另行通知</li>
                            <li>因不可抗力、网络故障、黑客攻击等导致的服务中断，平台不承担责任</li>
                            <li>用户应遵守社会公德，文明交流，不得进行骚扰、诽谤等不当行为</li>
                            <li>平台不保证服务的连续性、及时性、安全性，用户需自行承担使用风险</li>
                            <li>用户应自行备份重要信息，平台不承担数据丢失责任</li>
                        </ul>
                        
                        <p><strong>隐私保护：</strong></p>
                        <ul>
                            <li>平台将依法保护用户个人信息，未经用户同意不得向第三方泄露</li>
                            <li>用户应保护个人隐私，不要轻易透露身份证号、银行卡号等敏感信息</li>
                            <li>平台有权依法向司法机关提供用户信息以配合调查</li>
                            <li>用户有权查询、更正、删除个人信息的权利</li>
                            <li>平台将采取合理措施保护用户信息安全，但无法保证绝对安全</li>
                        </ul>
                        
                        <p><strong>安全提示：</strong></p>
                        <ul>
                            <li>建议用户在线下见面时选择公共场所，注意人身和财产安全</li>
                            <li>如遇不当内容或行为，请及时通过举报功能反馈，平台将及时处理</li>
                            <li>如发现违法犯罪行为，请立即向公安机关举报</li>
                            <li>用户应理性对待情感关系，谨慎处理个人隐私</li>
                            <li>禁止进行金钱交易，谨防网络诈骗</li>
                        </ul>
                        
                        <p><strong>服务条款：</strong></p>
                        <ul>
                            <li>用户注册即表示同意本平台的服务条款和隐私政策</li>
                            <li>平台有权收集和使用用户信息以提供更好的服务，具体详见隐私政策</li>
                            <li>VIP服务购买后不支持退款，请谨慎选择</li>
                            <li>平台保留最终解释权和修改权</li>
                            <li>用户应遵守平台使用规则，不得恶意攻击系统或干扰正常运营</li>
                        </ul>
                    </div>
                </div>
                
                <div class="agreement-checkbox required">
                    <input type="checkbox" id="paymentAgreementCheckbox">
                    <label for="paymentAgreementCheckbox">我已阅读同意上述法律声明和免责声明</label>
                </div>
                
                <div class="agreement-error" id="paymentAgreementError">
                    <i class="fas fa-exclamation-triangle"></i> 请先阅读并同意法律声明和免责声明
                </div>
            </div>
            
            <!-- 安全保障说明 -->
            <div class="security-info">
                <div class="security-badges">
                    <div class="security-badge">
                        <i class="fas fa-shield-alt"></i>
                        <span>私密加密支付</span>
                    </div>
                    <div class="security-badge">
                        <i class="fas fa-lock"></i>
                        <span>隐私保护</span>
                    </div>
                    <div class="security-badge">
                        <i class="fas fa-user-shield"></i>
                        <span>同城真实</span>
                    </div>
                </div>
            </div>
            
            <!-- 退款保障 -->
            <div class="refund-guarantees">
                <div class="section-title gradient-text">
                    <i class="fas fa-shield-alt"></i> 服务保障
                </div>
                <div class="guarantee-items">
                    <div class="guarantee-item">
                        <i class="fas fa-undo-alt"></i>
                        <span>24小时不满意随时退款</span>
                    </div>
                    <div class="guarantee-item">
                        <i class="fas fa-database"></i>
                        <span>资源齐全</span>
                    </div>
                    <div class="guarantee-item">
                        <i class="fas fa-robot"></i>
                        <span>自动退款系统</span>
                    </div>
                </div>
            </div>
            
            <!-- 用户评价 -->
            <div class="user-reviews">
                <div class="section-title">
                    <i class="fas fa-star"></i> 用户真实反馈
                </div>
                <div class="review-list">
                    <div class="review-item animated-text" style="animation-delay: 0.1s;">
                        <div class="review-content enhanced-paragraph">深夜聊天很刺激，认识了很多<span class="gradient-text">有趣的密友</span>！</div>
                        <div class="review-author gradient-text">- 张**（北京）</div>
                    </div>
                    <div class="review-item animated-text" style="animation-delay: 0.2s;">
                        <div class="review-content enhanced-paragraph">私密聊天体验很棒，推荐给<span class="highlight">喜欢刺激</span>的朋友</div>
                        <div class="review-author gradient-text">- 李**（上海）</div>
                    </div>
                    <div class="review-item animated-text" style="animation-delay: 0.3s;">
                        <div class="review-content enhanced-paragraph">深夜陪伴很贴心，聊天氛围<span class="gradient-text">很放松</span></div>
                        <div class="review-author gradient-text">- 王**（广州）</div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- 订单区域（默认隐藏） -->
        <div class="card hidden" id="orderSection">
            <div class="section-title">
                <i class="fas fa-list-alt"></i> 我的订单
            </div>
            
            <!-- 订单查询功能 -->
            <div class="order-search">
                <input type="text" class="order-search-input" id="orderSearchInput" placeholder="输入订单号查询">
                <button class="order-search-btn" id="orderSearchBtn">查询</button>
            </div>
            
            <!-- 订单详情显示区域 -->
            <div class="order-details" id="orderDetails">
                <!-- 订单详情将通过JS动态生成 -->
            </div>
            
            <div class="order-list" id="orderList">
                <!-- 订单列表将通过JS动态生成 -->
            </div>
            <button class="btn btn-secondary" id="backBtn">返回</button>
        </div>
        
        <!-- 个人资料区域（默认隐藏） -->
        <div class="card hidden" id="profileSection">
            <div class="profile-section" id="profileContent">
                <!-- 登录状态下的个人资料内容 -->
                <div class="profile-avatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="profile-name" id="profileUserName">请登录</div>
                <div class="profile-location">
                    <i class="fas fa-map-marker-alt"></i> <span id="profileUserLocation">未设置</span>
                </div>
                
                <div class="stats">
                    <div class="stat-item">
                        <div class="stat-value">0</div>
                        <div class="stat-label">好友</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">0</div>
                        <div class="stat-label">群组</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value">0</div>
                        <div class="stat-label">动态</div>
                    </div>
                </div>
                
                <div class="tips">
                    <i class="fas fa-lightbulb"></i> 完善个人资料可以让更多人认识你哦！
                </div>
                
                <button class="btn btn-primary" id="editProfileBtn">编辑个人资料</button>
                <button class="btn btn-secondary" id="logoutBtn" style="margin-top: 10px;">退出登录</button>
            </div>
            
            <!-- 未登录状态下的注册/登录内容 -->
            <div class="register-form hidden" id="registerContent">
                <div class="section-title">
                    <i class="fas fa-user-plus"></i> 注册新账号
                </div>
                
                <div class="avatar-upload">
                    <div class="avatar-preview" id="avatarPreview">
                        <i class="fas fa-user"></i>
                    </div>
                    <input type="file" id="avatarInput" accept="image/*" style="display: none;">
                    <div class="avatar-upload-btn" id="avatarUploadBtn">上传头像</div>
                </div>
                
                <div class="form-group">
                    <label for="registerUsername">用户名</label>
                    <input type="text" id="registerUsername" placeholder="请输入用户名">
                </div>
                
                <div class="form-group">
                    <label for="registerPassword">密码</label>
                    <input type="password" id="registerPassword" placeholder="请输入密码">
                </div>
                
                <div class="form-group">
                    <label for="registerConfirmPassword">确认密码</label>
                    <input type="password" id="registerConfirmPassword" placeholder="请再次输入密码">
                </div>
                
                <div class="form-group">
                    <label for="registerPhone">手机号码</label>
                    <input type="tel" id="registerPhone" placeholder="请输入手机号码">
                </div>
                
                <div class="form-group">
                    <label>性别</label>
                    <div class="gender-select">
                        <div class="gender-option active" data-gender="male">男</div>
                        <div class="gender-option" data-gender="female">女</div>
                        <div class="gender-option" data-gender="other">其他</div>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="registerAge">年龄</label>
                    <input type="number" id="registerAge" placeholder="请输入年龄" min="18" max="80">
                </div>
                
                <div class="form-group">
                    <label for="registerLocation">所在城市</label>
                    <input type="text" id="registerLocation" placeholder="请输入所在城市">
                </div>
                
                <div class="form-group">
                    <label for="registerBio">个人简介</label>
                    <textarea id="registerBio" placeholder="介绍一下你自己..." rows="3"></textarea>
                </div>
                
                <!-- 声明和免责声明 -->
                <div class="agreement-section">
                    <div class="agreement-title">
                        <i class="fas fa-exclamation-circle"></i> 法律声明与免责声明
                    </div>
                    
                    <div class="agreement-content hidden" id="registerAgreementContent">
                        <div class="agreement-summary">
                            <p><strong>重要提示：</strong>在使用本平台服务前，请仔细阅读以下声明内容。双击"我已阅读同意上述法律声明和免责声明"复选框即可查看完整内容。</p>
                            <p class="agreement-preview">本平台严格遵守国家法律法规，提供婚恋交友信息服务。用户需对自身行为承担法律责任，平台仅提供信息交流服务...</p>
                        </div>
                        
                        <div class="agreement-details">
                            <p><strong>法律声明：</strong></p>
                            <ul>
                                <li>本平台严格遵守《中华人民共和国网络安全法》、《个人信息保护法》、《民法典》等相关法律法规</li>
                                <li>用户需保证所提供信息的真实性和合法性，不得冒用他人身份或提供虚假信息</li>
                                <li>禁止发布涉及色情、暴力、赌博、诈骗、传销等违法信息及不当言论</li>
                                <li>用户需对自身行为承担全部法律责任，包括但不限于民事、行政、刑事责任</li>
                                <li>平台有权对违规内容进行删除，对违规用户进行警告、限制功能或封禁处理</li>
                                <li>用户应妥善保管账号信息，不得转让、出租或出借账号给他人使用</li>
                                <li>禁止利用平台进行商业推广、广告宣传等未经授权的商业活动</li>
                                <li>用户应遵守平台社区规范，维护良好的交流环境</li>
                            </ul>
                            
                            <p><strong>免责声明：</strong></p>
                            <ul>
                                <li>本平台仅提供信息交流服务，不承担用户间纠纷责任，用户应自行协商解决</li>
                                <li>用户需自行判断信息真实性，平台不保证用户发布信息的准确性、完整性和时效性</li>
                                <li>因用户行为造成的任何损失，包括但不限于财产损失、人身伤害等，平台概不负责</li>
                                <li>平台有权根据法律法规变化或业务需要调整服务内容，恕不另行通知</li>
                                <li>因不可抗力、网络故障、黑客攻击等导致的服务中断，平台不承担责任</li>
                                <li>用户应遵守社会公德，文明交流，不得进行骚扰、诽谤等不当行为</li>
                                <li>平台不保证服务的连续性、及时性、安全性，用户需自行承担使用风险</li>
                                <li>用户应自行备份重要信息，平台不承担数据丢失责任</li>
                            </ul>
                            
                            <p><strong>隐私保护：</strong></p>
                            <ul>
                                <li>平台将依法保护用户个人信息，未经用户同意不得向第三方泄露</li>
                                <li>用户应保护个人隐私，不要轻易透露身份证号、银行卡号等敏感信息</li>
                                <li>平台有权依法向司法机关提供用户信息以配合调查</li>
                                <li>用户有权查询、更正、删除个人信息的权利</li>
                                <li>平台将采取合理措施保护用户信息安全，但无法保证绝对安全</li>
                            </ul>
                            
                            <p><strong>安全提示：</strong></p>
                            <ul>
                                <li>建议用户在线下见面时选择公共场所，注意人身和财产安全</li>
                                <li>如遇不当内容或行为，请及时通过举报功能反馈，平台将及时处理</li>
                                <li>如发现违法犯罪行为，请立即向公安机关举报</li>
                                <li>用户应理性对待情感关系，谨慎处理个人隐私</li>
                                <li>禁止进行金钱交易，谨防网络诈骗</li>
                            </ul>
                            
                            <p><strong>服务条款：</strong></p>
                            <ul>
                                <li>用户注册即表示同意本平台的服务条款和隐私政策</li>
                                <li>平台有权收集和使用用户信息以提供更好的服务，具体详见隐私政策</li>
                                <li>VIP服务购买后不支持退款，请谨慎选择</li>
                                <li>平台保留最终解释权和修改权</li>
                                <li>用户应遵守平台使用规则，不得恶意攻击系统或干扰正常运营</li>
                            </ul>
                        </div>
                    </div>
                    
                    <div class="agreement-checkbox required">
                        <input type="checkbox" id="registerAgreementCheckbox">
                        <label for="registerAgreementCheckbox">我已阅读同意上述法律声明和免责声明</label>
                    </div>
                    
                    <div class="agreement-error" id="registerAgreementError">
                        <i class="fas fa-exclamation-triangle"></i> 请先阅读并同意法律声明和免责声明
                    </div>
                </div>
                
                <div class="form-actions">
                    <button class="btn btn-primary" id="registerSubmitBtn">注册</button>
                    <button class="btn btn-secondary" id="registerCancelBtn">取消</button>
                </div>
                
                <div class="login-prompt">
                    <p>已有账号？</p>
                    <button class="btn btn-secondary" id="showLoginBtn">立即登录</button>
                </div>
            </div>
            
            <!-- 登录表单 -->
            <div class="register-form hidden" id="loginContent">
                <!-- 登录类型切换 -->
                <div class="login-type-tabs">
                    <div class="login-type-tab active" data-type="user">用户登录</div>
                </div>
                
                <!-- 用户登录表单 -->
                <div class="login-form" id="userLoginForm">
                    <div class="section-title">
                        <i class="fas fa-sign-in-alt"></i> 用户登录
                    </div>
                    
                    <div class="form-group">
                        <label for="loginUsername">用户名</label>
                        <input type="text" id="loginUsername" placeholder="请输入用户名">
                    </div>
                    
                    <div class="form-group">
                        <label for="loginPassword">密码</label>
                        <input type="password" id="loginPassword" placeholder="请输入密码">
                    </div>
                    
                    <!-- 声明和免责声明 -->
                    <div class="agreement-section">
                        <div class="agreement-title">
                            <i class="fas fa-exclamation-circle"></i> 法律声明与免责声明
                        </div>
                        
                        <div class="agreement-content hidden" id="loginAgreementContent">
                            <div class="agreement-summary">
                                <p><strong>重要提示：</strong>在使用本平台服务前，请仔细阅读以下声明内容。双击"我已阅读同意上述法律声明和免责声明"复选框即可查看完整内容。</p>
                                <p class="agreement-preview">本平台严格遵守国家法律法规，提供婚恋交友信息服务。用户需对自身行为承担法律责任，平台仅提供信息交流服务...</p>
                            </div>
                            
                            <div class="agreement-details">
                                <p><strong>法律声明：</strong></p>
                                <ul>
                                    <li>本平台严格遵守《中华人民共和国网络安全法》、《个人信息保护法》、《民法典》等相关法律法规</li>
                                    <li>用户需保证所提供信息的真实性和合法性，不得冒用他人身份或提供虚假信息</li>
                                    <li>禁止发布涉及色情、暴力、赌博、诈骗、传销等违法信息及不当言论</li>
                                    <li>用户需对自身行为承担全部法律责任，包括但不限于民事、行政、刑事责任</li>
                                    <li>平台有权对违规内容进行删除，对违规用户进行警告、限制功能或封禁处理</li>
                                    <li>用户应妥善保管账号信息，不得转让、出租或出借账号给他人使用</li>
                                    <li>禁止利用平台进行商业推广、广告宣传等未经授权的商业活动</li>
                                    <li>用户应遵守平台社区规范，维护良好的交流环境</li>
                                </ul>
                                
                                <p><strong>免责声明：</strong></p>
                                <ul>
                                    <li>本平台仅提供信息交流服务，不承担用户间纠纷责任，用户应自行协商解决</li>
                                    <li>用户需自行判断信息真实性，平台不保证用户发布信息的准确性、完整性和时效性</li>
                                    <li>因用户行为造成的任何损失，包括但不限于财产损失、人身伤害等，平台概不负责</li>
                                    <li>平台有权根据法律法规变化或业务需要调整服务内容，恕不另行通知</li>
                                    <li>因不可抗力、网络故障、黑客攻击等导致的服务中断，平台不承担责任</li>
                                    <li>用户应遵守社会公德，文明交流，不得进行骚扰、诽谤等不当行为</li>
                                    <li>平台不保证服务的连续性、及时性、安全性，用户需自行承担使用风险</li>
                                    <li>用户应自行备份重要信息，平台不承担数据丢失责任</li>
                                </ul>
                                
                                <p><strong>隐私保护：</strong></p>
                                <ul>
                                    <li>平台将依法保护用户个人信息，未经用户同意不得向第三方泄露</li>
                                    <li>用户应保护个人隐私，不要轻易透露身份证号、银行卡号等敏感信息</li>
                                    <li>平台有权依法向司法机关提供用户信息以配合调查</li>
                                    <li>用户有权查询、更正、删除个人信息的权利</li>
                                    <li>平台将采取合理措施保护用户信息安全，但无法保证绝对安全</li>
                                </ul>
                                
                                <p><strong>安全提示：</strong></p>
                                <ul>
                                    <li>建议用户在线下见面时选择公共场所，注意人身和财产安全</li>
                                    <li>如遇不当内容或行为，请及时通过举报功能反馈，平台将及时处理</li>
                                    <li>如发现违法犯罪行为，请立即向公安机关举报</li>
                                    <li>用户应理性对待情感关系，谨慎处理个人隐私</li>
                                    <li>禁止进行金钱交易，谨防网络诈骗</li>
                                </ul>
                                
                                <p><strong>服务条款：</strong></p>
                                <ul>
                                    <li>用户注册即表示同意本平台的服务条款和隐私政策</li>
                                    <li>平台有权收集和使用用户信息以提供更好的服务，具体详见隐私政策</li>
                                    <li>VIP服务购买后不支持退款，请谨慎选择</li>
                                    <li>平台保留最终解释权和修改权</li>
                                    <li>用户应遵守平台使用规则，不得恶意攻击系统或干扰正常运营</li>
                                </ul>
                            </div>
                        </div>
                        
                        <div class="agreement-checkbox required">
                            <input type="checkbox" id="loginAgreementCheckbox">
                            <label for="loginAgreementCheckbox">我已阅读并同意上述法律声明、免责声明以及双方同意原则，包括但不限于互动同意、数据使用同意和服务变更同意条款</label>
                        </div>
                        
                        <div class="agreement-error" id="loginAgreementError">
                            <i class="fas fa-exclamation-triangle"></i> 请先阅读并同意法律声明和免责声明
                        </div>
                    </div>
                    
                    <div class="form-actions">
                        <button class="btn btn-primary" id="loginSubmitBtn">登录</button>
                        <button class="btn btn-secondary" id="loginCancelBtn">取消</button>
                    </div>
                    
                    <div class="login-prompt">
                        <p>还没有账号？</p>
                        <button class="btn btn-secondary" id="showRegisterBtn">立即注册</button>
                    </div>
                </div>
            </div>
            
            <!-- 编辑个人资料表单 -->
            <div class="edit-form hidden" id="editProfileContent">
                <div class="section-title">
                    <i class="fas fa-edit"></i> 编辑个人资料
                </div>
                
                <div class="avatar-upload">
                    <div class="avatar-preview" id="editAvatarPreview">
                        <i class="fas fa-user"></i>
                    </div>
                    <input type="file" id="editAvatarInput" accept="image/*" style="display: none;">
                    <div class="avatar-upload-btn" id="editAvatarUploadBtn">更换头像</div>
                </div>
                
                <div class="form-group">
                    <label for="editUsername">用户名</label>
                    <input type="text" id="editUsername" placeholder="请输入用户名">
                </div>
                
                <div class="form-group">
                    <label>性别</label>
                    <div class="gender-select">
                        <div class="gender-option" data-gender="male">男</div>
                        <div class="gender-option" data-gender="female">女</div>
                        <div class="gender-option" data-gender="other">其他</div>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="editAge">年龄</label>
                    <input type="number" id="editAge" placeholder="请输入年龄" min="18" max="80">
                </div>
                
                <div class="form-group">
                    <label for="editLocation">所在城市</label>
                    <input type="text" id="editLocation" placeholder="请输入所在城市">
                </div>
                
                <div class="form-group">
                    <label for="editBio">个人简介</label>
                    <textarea id="editBio" placeholder="介绍一下你自己..." rows="3"></textarea>
                </div>
                
                <div class="form-actions">
                    <button class="btn btn-primary" id="editSubmitBtn">保存</button>
                    <button class="btn btn-secondary" id="editCancelBtn">取消</button>
                </div>
            </div>
        </div>
        
        <!-- 聊天记录区域（默认隐藏） -->
        <div class="card hidden" id="chatSection">
            <div class="chat-header">
                <button class="back-button" id="chatBackBtn">
                    <i class="fas fa-arrow-left"></i>
                </button>
                <div class="chat-title" id="chatTitle">群聊记录</div>
            </div>
            <div class="chat-section" id="chatContent">
                <!-- 聊天记录内容将通过JS动态生成 -->
            </div>
        </div>
        
        <!-- 反馈中心区域（默认隐藏） -->
        <div class="card hidden" id="feedbackSection">
            <div class="section-title gradient-text">
                <i class="fas fa-comments"></i> 用户真实体验反馈
            </div>
            
            <!-- 反馈中心内容（基本框架） -->
            <div class="feedback-content" id="feedbackContent">
                <!-- 用户真实反馈展览链接 -->
                <div class="feedback-exhibition-link">
                    <a href="#" class="btn btn-primary gradient-bg" onclick="showFeedbackExhibition(); return false;">
                        <i class="fas fa-images"></i>
                        <span>查看用户真实反馈展览</span>
                    </a>
                </div>
                
                <div class="feedback-info">
                    <div class="feedback-tip">
                        <i class="fas fa-info-circle"></i>
                        <span>反馈功能正在优化中，敬请期待</span>
                    </div>
                </div>
                
                <!-- 微信群聊用户反馈 -->
                <div class="feedback-mode-content active" id="groupFeedbackContent">
                    <div class="feedback-info">
                        <div class="feedback-tip enhanced-paragraph">
                            <i class="fas fa-star gradient-text"></i>
                            <span>已有<span class="highlight">10,000+</span>用户加入我们的同城群聊，开启了他们的社交之旅！</span>
                        </div>
                        <div class="feedback-promo">
                            <div class="promo-badge gradient-bg">限时优惠</div>
                            <div class="promo-text">
                                <span class="gradient-text">开通VIP</span> 即可无限制参与所有同城群聊，遇见志同道合的朋友！
                            </div>
                            <button class="btn btn-primary gradient-bg" onclick="openPaymentModal('group')">
                                <i class="fas fa-rocket"></i> 立即开通VIP
                            </button>
                        </div>
                    </div>
                    
                    <!-- 反馈列表 -->
                    <div class="feedback-list" id="groupFeedbackList">
                        <!-- 反馈内容将通过JS动态生成 -->
                    </div>
                </div>
                
                <!-- 红娘牵线服务反馈 -->
                <div class="feedback-mode-content" id="matchmakerFeedbackContent">
                    <div class="feedback-info">
                        <div class="feedback-tip">
                            <i class="fas fa-info-circle"></i>
                            <span>查看牵线服务反馈，提交反馈需要开通红娘牵线VIP服务</span>
                        </div>
                    </div>
                    
                    <!-- 反馈列表 -->
                    <div class="feedback-list" id="matchmakerFeedbackList">
                        <!-- 反馈内容将通过JS动态生成 -->
                    </div>
                </div>
                
                <!-- 上传反馈区域 -->
                <div class="feedback-upload">
                    <div class="feedback-upload-title">
                        <i class="fas fa-plus-circle"></i>
                        <span>上传反馈</span>
                    </div>
                    
                    <div class="feedback-upload-form">
                        <div class="form-group">
                            <label for="feedbackTitle">反馈标题</label>
                            <input type="text" id="feedbackTitle" placeholder="请输入反馈标题">
                        </div>
                        
                        <div class="form-group">
                            <label for="feedbackContent">反馈内容</label>
                            <textarea id="feedbackContent" placeholder="请输入反馈内容..." rows="4"></textarea>
                        </div>
                        
                        <div class="form-group">
                            <label>上传照片</label>
                            <div class="photo-upload-area" id="photoUploadArea">
                                <div class="photo-upload-preview" id="photoPreview">
                                    <i class="fas fa-camera"></i>
                                    <span>点击上传照片</span>
                                </div>
                                <input type="file" id="photoInput" accept="image/*" multiple style="display: none;">
                            </div>
                            <div class="photo-list" id="photoList">
                                <!-- 已上传照片列表 -->
                            </div>
                        </div>
                        

                        
                        <div class="form-actions">
                            <button class="btn btn-primary" id="submitFeedbackBtn">提交反馈</button>
                            <button class="btn btn-secondary" id="cancelFeedbackBtn">取消</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        

        



        <!-- 一日情侣牵线区域（默认隐藏） -->
        <div class="card hidden" id="matchmakerSection">
            <div class="section-title gradient-text">
                <i class="fas fa-heart"></i> 牵线成为一日情侣
            </div>
            
            <!-- 红娘牵线支付区域（已移至顶部） -->
            <div class="matchmaker-payment">
                <!-- 信任徽章区域 -->
                <div class="trust-badges">
                    <span class="badge"><i class="fas fa-shield-alt"></i> 实名认证</span>
                    <span class="badge"><i class="fas fa-user-check"></i> 人工审核</span>
                    <span class="badge"><i class="fas fa-thumbs-up"></i> 98.5%好评</span>
                    <span class="badge"><i class="fas fa-lock"></i> 安全支付</span>
                    <span class="badge"><i class="fas fa-heart"></i> 成功匹配3万+</span>
                </div>
                
                <!-- 限时优惠提示 -->
                <div class="limited-time-offer">
                    <i class="fas fa-bolt"></i> 
                    <span>限时优惠：原价¥499.99，限时特惠¥299.99</span>
                    <div class="countdown-timer">剩余时间: <span id="countdown">23:59:59</span></div>
                </div>
                
                <div class="matchmaker-payment-title gradient-text">一日情侣专属体验</div>
                <div class="matchmaker-payment-amount">
                    <span class="current-price">¥199.99</span>
                    <span class="original-price">¥399.99</span>
                    <span class="discount-tag">4.8折</span>
                </div>
                
                <div class="matchmaker-payment-features">
                    <div class="payment-feature highlight-feature">
                        <i class="fas fa-heart"></i>
                        <span>一日情侣专属体验</span>
                    </div>
                    <div class="payment-feature">
                        <i class="fas fa-user-friends"></i>
                        <span>同城异性精准匹配</span>
                    </div>
                    <div class="payment-feature">
                        <i class="fas fa-clock"></i>
                        <span>24小时浪漫体验期</span>
                    </div>
                    <div class="payment-feature">
                        <i class="fas fa-comments"></i>
                        <span>专属聊天空间</span>
                    </div>
                    <div class="payment-feature">
                        <i class="fas fa-map-marker-alt"></i>
                        <span>同城线下约会建议</span>
                    </div>
                    <div class="payment-feature">
                        <i class="fas fa-gift"></i>
                        <span>专属情侣任务</span>
                    </div>
                    <div class="payment-feature">
                        <i class="fas fa-lock"></i>
                        <span>全程隐私安全保护</span>
                    </div>
                </div>
                
                <!-- 成功案例展示 (可折叠) -->
                <div class="collapsible-section success-stories">
                    <div class="collapsible-header" onclick="toggleCollapse(this)">
                        <h4 class="gradient-text">✓ 一日情侣体验故事</h4>
                        <i class="fas fa-chevron-down collapse-icon"></i>
                    </div>
                    <div class="collapsible-content">
                        <div class="stories-grid">
                            <div class="story-item animated-text">
                                <div class="story-content">
                                    <p class="story-text enhanced-paragraph">"一日情侣体验非常棒！我们一起看电影、逛公园，度过了浪漫的一天。感谢平台让我们相遇！"</p>
                                    <div class="story-author gradient-text">— 张先生，上海</div>
                                </div>
                            </div>
                            <div class="story-item animated-text" style="animation-delay: 0.2s;">
                                <div class="story-content">
                                    <p class="story-text enhanced-paragraph">"24小时的情侣体验很特别，我们一起完成了很多有趣的任务，现在还保持着联系！"</p>
                                    <div class="story-author gradient-text">— 李女士，北京</div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- 用户评价 (可折叠) -->
                <div class="collapsible-section user-reviews">
                    <div class="collapsible-header" onclick="toggleCollapse(this)">
                        <div class="review-stats">
                            <div class="rating">
                                <span class="stars">★★★★★</span>
                                <span class="rating-number">4.9/5</span>
                            </div>
                            <div class="review-count">基于1200+真实用户评价</div>
                        </div>
                        <i class="fas fa-chevron-down collapse-icon"></i>
                    </div>
                </div>
                
                <!-- 支付方式选择 -->
                <div class="matchmaker-payment-methods">
                    <div class="matchmaker-payment-method active" data-method="alipay">
                        <i class="fab fa-alipay"></i>
                        <div>支付宝</div>
                    </div>
                    <div class="matchmaker-payment-method" data-method="wxpay">
                        <i class="fab fa-weixin"></i>
                        <div>微信支付</div>
                    </div>
                </div>
                
                <!-- 支付宝支付表单 -->
                <div class="matchmaker-payment-form active" id="matchmakerAlipayForm">
                    <button class="btn btn-primary" id="matchmakerAlipayBtn">
                        <span class="loading hidden"></span>
                        <span id="matchmakerAlipayBtnText">支付宝支付 ¥199.99</span>
                    </button>
                </div>
                
                <!-- 微信支付表单 -->
                <div class="matchmaker-payment-form" id="matchmakerWxpayForm">
                    <button class="btn btn-primary" id="matchmakerWxpayBtn">
                        <span class="loading hidden"></span>
                        <span id="matchmakerWxpayBtnText">微信支付 ¥199.99</span>
                    </button>
                </div>
                
                <!-- 声明和免责声明 -->
                <div class="agreement-section">
                    <div class="agreement-title">
                        <i class="fas fa-exclamation-circle"></i> 法律声明与免责声明
                    </div>
                    
                    <div class="agreement-content hidden" id="matchmakerPaymentAgreementContent">
                        <div class="agreement-summary">
                            <p><strong>重要提示：</strong>在使用本平台服务前，请仔细阅读以下声明内容。双击"我已阅读同意上述法律声明和免责声明"复选框即可查看完整内容。</p>
                            <p class="agreement-preview">本平台严格遵守国家法律法规，提供婚恋交友信息服务。用户需对自身行为承担法律责任，平台仅提供信息交流服务...</p>
                        </div>
                        
                        <div class="agreement-details">
                            <p><strong>法律声明：</strong></p>
                            <ul>
                                <li>本平台严格遵守《中华人民共和国网络安全法》、《个人信息保护法》、《民法典》等相关法律法规</li>
                                <li>用户需保证所提供信息的真实性和合法性，不得冒用他人身份或提供虚假信息</li>
                                <li>禁止发布涉及色情、暴力、赌博、诈骗、传销等违法信息及不当言论</li>
                                <li>用户需对自身行为承担全部法律责任，包括但不限于民事、行政、刑事责任</li>
                                <li>平台有权对违规内容进行删除，对违规用户进行警告、限制功能或封禁处理</li>
                                <li>用户应妥善保管账号信息，不得转让、出租或出借账号给他人使用</li>
                                <li>禁止利用平台进行商业推广、广告宣传等未经授权的商业活动</li>
                                <li>用户应遵守平台社区规范，维护良好的交流环境</li>
                            </ul>
                            
                            <p><strong>免责声明：</strong></p>
                            <ul>
                                <li>本平台仅提供信息交流服务，不承担用户间纠纷责任，用户应自行协商解决</li>
                                <li>用户需自行判断信息真实性，平台不保证用户发布信息的准确性、完整性和时效性</li>
                                <li>因用户行为造成的任何损失，包括但不限于财产损失、人身伤害等，平台概不负责</li>
                                <li>平台有权根据法律法规变化或业务需要调整服务内容，恕不另行通知</li>
                                <li>因不可抗力、网络故障、黑客攻击等导致的服务中断，平台不承担责任</li>
                                <li>用户应遵守社会公德，文明交流，不得进行骚扰、诽谤等不当行为</li>
                                <li>平台不保证服务的连续性、及时性、安全性，用户需自行承担使用风险</li>
                                <li>用户应自行备份重要信息，平台不承担数据丢失责任</li>
                            </ul>
                            
                            <p><strong>隐私保护：</strong></p>
                            <ul>
                                <li>平台将依法保护用户个人信息，未经用户同意不得向第三方泄露</li>
                                <li>用户应保护个人隐私，不要轻易透露身份证号、银行卡号等敏感信息</li>
                                <li>平台有权依法向司法机关提供用户信息以配合调查</li>
                                <li>用户有权查询、更正、删除个人信息的权利</li>
                                <li>平台将采取合理措施保护用户信息安全，但无法保证绝对安全</li>
                            </ul>
                            
                            <p><strong>安全提示：</strong></p>
                            <ul>
                                <li>建议用户在线下见面时选择公共场所，注意人身和财产安全</li>
                                <li>如遇不当内容或行为，请及时通过举报功能反馈，平台将及时处理</li>
                                <li>如发现违法犯罪行为，请立即向公安机关举报</li>
                                <li>用户应理性对待情感关系，谨慎处理个人隐私</li>
                                <li>禁止进行金钱交易，谨防网络诈骗</li>
                            </ul>
                            
                            <p><strong>服务条款：</strong></p>
                            <ul>
                                <li>用户注册即表示同意本平台的服务条款和隐私政策</li>
                                <li>平台有权收集和使用用户信息以提供更好的服务，具体详见隐私政策</li>
                                <li>VIP服务购买后不支持退款，请谨慎选择</li>
                                <li>平台保留最终解释权和修改权</li>
                                <li>用户应遵守平台使用规则，不得恶意攻击系统或干扰正常运营</li>
                            </ul>
                        </div>
                    </div>
                    
                    <div class="agreement-checkbox required">
                        <input type="checkbox" id="matchmakerPaymentAgreementCheckbox">
                        <label for="matchmakerPaymentAgreementCheckbox">我已阅读同意上述法律声明和免责声明</label>
                    </div>
                    
                    <div class="agreement-error" id="matchmakerPaymentAgreementError">
                        <i class="fas fa-exclamation-triangle"></i> 请先阅读并同意法律声明和免责声明
                    </div>
                </div>
            </div>
            
            <!-- 城市选择区域 - 优化折叠面板 -->
            <div class="matchmaker-city-selector panel-collapse" id="matchmakerCitySelector">
                <div class="matchmaker-city-selector-title panel-header">
                    <span>选择你所在的城市区域</span>
                    <div class="panel-toggle">
                        <i class="fas fa-chevron-down toggle-icon"></i>
                    </div>
                </div>
                <div class="matchmaker-city-grid panel-content" id="matchmakerCityGrid">
                    <!-- 城市区域将通过JS动态生成 -->
                </div>
            </div>


            
            <div class="matchmaker-section" id="matchmakerContent">
                <!-- 红娘牵线内容将通过JS动态生成 -->
            </div>
        </div>
        
        <!-- 用户详情区域（默认隐藏） -->
        <div class="card hidden" id="userDetailSection">
            <div class="user-detail-section" id="userDetailContent">
                <!-- 用户详情内容将通过JS动态生成 -->
            </div>
            <button class="btn btn-secondary" id="userDetailBackBtn">返回</button>
        </div>
    </div>
    
    <!-- 支付过渡页面 -->
    <div class="modal hidden" id="paymentRedirectModal">
        <div class="modal-content">
            <div class="payment-redirect">
                <div class="payment-icon"><i class="fas fa-credit-card"></i></div>
                <h2>正在处理支付请求</h2>
                <div class="payment-details">
                    <div class="detail-item">
                        <span class="detail-label">订单号：</span>
                        <span class="detail-value" id="redirectOrderNumber">WXGROUP20241234567890</span>
                    </div>
                    <div class="detail-item alert-message">
                        <i class="fas fa-exclamation-circle"></i>
                        <span>提示：如果支付成功后未开通对应的VIP功能，请及时联系客服</span>
                    </div>
                </div>
                <div class="countdown-area">
                    <p>正在跳转支付，请耐心等待 <span id="redirectCountdown">3</span> 秒</p>
                    <div class="progress-bar">
                        <div class="progress-fill" id="redirectProgress"></div>
                    </div>
                </div>
                <div class="modal-buttons">
                    <button class="btn btn-primary" id="continuePaymentBtn">继续支付</button>
                    <button class="btn btn-secondary" id="cancelPaymentBtn">返回</button>
                </div>
            </div>
        </div>
    </div>

    <!-- 牵线服务通知模态框 -->
    <div class="modal hidden" id="matchmakerNotificationModal">
        <div class="modal-content premium-style">
            <div class="matchmaker-notification modern-notification">
                <!-- 顶部装饰元素 -->
                <div class="notification-decoration">
                    <div class="heart-decoration heart-1"></div>
                    <div class="heart-decoration heart-2"></div>
                    <div class="heart-decoration heart-3"></div>
                </div>
                
                <!-- 标题区域 -->
                <div class="notification-header modern-header">
                    <h2><i class="fas fa-crown gold-icon"></i> <span class="seductive-text gradient-text">专属</span> 一对一体验</h2>
                    <p class="header-subtitle">为您精心打造的私密约会服务</p>
                </div>
                
                <!-- 主要内容区域 -->
                <div class="notification-content modern-content">
                    <!-- 视觉元素 -->
                    <div class="notification-visual">
                        <div class="visual-container">
                            <i class="fas fa-heart red-heart pulse-animation"></i>
                            <i class="fas fa-heart pink-heart pulse-animation-delay"></i>
                            <i class="fas fa-heart blue-heart pulse-animation-delay-2"></i>
                        </div>
                    </div>
                    
                    <!-- 文字内容 -->
                    <div class="notification-message">
                        <p class="message-text romantic-text">
                            <span class="greeting">亲爱的用户，</span>
                            <br>
                            欢迎体验我们<span class="highlight">浪漫定制</span>的一日情侣牵线服务
                        </p>
                        
                        <div class="service-highlights">
                            <div class="highlight-item">
                                <i class="fas fa-user-check"></i>
                                <span>精准匹配合适伴侣</span>
                            </div>
                            <div class="highlight-item">
                                <i class="fas fa-clock"></i>
                                <span>24小时甜蜜体验</span>
                            </div>
                            <div class="highlight-item">
                                <i class="fas fa-gift"></i>
                                <span>专属情侣任务</span>
                            </div>
                        </div>
                        
                        <p class="message-text seductive-text italic-text">
                            <i class="fas fa-fire flame-icon"></i>
                            <span class="special-text">在双方<span class="underline">自愿同意</span>的前提下，您可以享受24小时专属情侣体验，共同完成浪漫任务...</span>
                            <i class="fas fa-kiss-wink-heart love-icon"></i>
                        </p>
                        
                        <p class="notification-disclaimer">
                            <small><strong>重要提示：本服务仅面向18岁以上成年用户提供，未满18岁用户禁止使用本服务。</strong></small><br>
                            <small>所有互动均建立在双方自愿和尊重的基础上，平台建议用户注意个人安全与隐私保护。</small>
                        </p>
                    </div>
                </div>
                
                <!-- 底部按钮区域 -->
                <div class="notification-actions modern-actions">
                    <button class="btn premium-button" id="confirmNotificationBtn">
                        <span>开启浪漫之旅</span>
                        <i class="fas fa-arrow-right"></i>
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- 支付处理中模态框 -->
    <div class="modal hidden" id="processingModal">
        <div class="modal-content">
            <div class="payment-processing">
                <div class="loading"></div>
                <div class="payment-status">支付处理中...</div>
                <p>请稍候，正在连接支付平台</p>
            </div>
        </div>
    </div>
    
    <!-- 支付失败模态框 -->
    <div class="modal hidden" id="failedModal">
        <div class="modal-content">
            <div class="success-icon" style="color: #ff3b30;"><i class="fas fa-times-circle"></i></div>
            <h2>支付失败</h2>
            <div class="payment-details">
                <div class="detail-item">
                    <span class="detail-label">订单号：</span>
                    <span class="detail-value" id="failedOrderNumber">20241234567890</span>
                </div>
                <div class="detail-item">
                    <span class="detail-label">支付金额：</span>
                    <span class="detail-value" id="failedAmount">¥99.00</span>
                </div>
                <div class="detail-item">
                    <span class="detail-label">失败原因：</span>
                    <span class="detail-value" id="failedReason">支付超时或网络异常</span>
                </div>
            </div>
            <p id="failedMessage">支付未能完成，请检查您的支付方式或重试</p>
            <div class="modal-buttons">
                <button class="btn btn-primary" id="retryPayBtn">重新支付</button>
                <button class="btn btn-secondary" id="contactCustomerBtn2">联系客服</button>
                <button class="btn btn-secondary" id="closeFailedModalBtn">关闭</button>
            </div>
        </div>
    </div>
    
    <!-- 支付成功模态框 -->
    <div class="modal hidden" id="successModal">
        <div class="modal-content">
            <div class="success-icon"><i class="fas fa-check-circle"></i></div>
            <h2>支付成功！</h2>
            <div class="payment-details">
                <div class="detail-item">
                    <span class="detail-label">订单号：</span>
                    <span class="detail-value" id="successOrderNumber">20241234567890</span>
                </div>
                <div class="detail-item">
                    <span class="detail-label">支付金额：</span>
                    <span class="detail-value" id="successAmount">¥99.00</span>
                </div>
                <div class="detail-item">
                    <span class="detail-label">支付时间：</span>
                    <span class="detail-value" id="successTime">2024-01-01 12:00:00</span>
                </div>
            </div>
            <div class="refund-notice">
                <p>如需退款，请在7天内联系客服处理</p>
            </div>
            <div class="modal-buttons">
                <button class="btn btn-secondary" id="contactCustomerBtn">联系客服</button>
                <button class="btn btn-primary" id="closeSuccessModalBtn">确定</button>
            </div>
        </div>
    </div>
    
    <!-- 功能提示模态框 -->
    <div class="modal hidden" id="featureInfoModal">
        <div class="modal-content">
            <div class="success-icon"><i class="fas fa-info-circle"></i></div>
            <h2>功能提示</h2>
            <p>请先完善您的个人资料以使用此功能</p>
            <div class="modal-buttons">
                <button class="btn btn-primary" id="closeFeatureInfoModalBtn">我知道了</button>
            </div>
        </div>
    </div>
    

    

    
    <div class="bottom-nav">
        <div class="nav-item active" data-target="main">
            <i class="fas fa-home"></i>
            <span>首页</span>
        </div>
        <div class="nav-item" data-target="orderSection">
            <i class="fas fa-list-alt"></i>
            <span>订单</span>
        </div>
        <div class="nav-item" data-target="feedbackSection">
            <i class="fas fa-comments"></i>
            <span>反馈中心</span>
        </div>
        <div class="nav-item" data-target="matchmakerSection">
            <i class="fas fa-heart"></i>
            <span>红娘牵线</span>
        </div>
        <div class="nav-item" data-target="profileSection">
            <i class="fas fa-user"></i>
            <span>我的</span>
        </div>
    </div>

    <!-- 客服系统 -->
    <div class="customer-service-container">
        <!-- 客服浮动按钮 -->
        <div class="customer-service-btn" id="customerServiceBtn">
            <i class="fas fa-comments"></i>
            <span>联系客服</span>
        </div>
        
        <!-- 客服聊天窗口 -->
        <div class="customer-service-chat hidden" id="customerServiceChat">
            <div class="chat-header">
                <div class="chat-title">
                    <i class="fas fa-headset"></i>
                    <span>在线客服</span>
                </div>
                <button class="chat-close" id="closeCustomerService">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div class="chat-messages" id="customerServiceMessages">
                <!-- 默认客服消息 -->
                <div class="message customer-message">
                    <div class="message-content">
                        <div class="message-text">您好！我是客服小助手，有什么可以帮助您的吗？</div>
                        <div class="message-time">刚刚</div>
                    </div>
                </div>
                <div class="message customer-message">
                    <div class="message-content">
                        <div class="message-text">如果长时间没有恢复消息请添加客服QQ1158980053</div>
                        <div class="message-time">刚刚</div>
                    </div>
                </div>
            </div>
            
            <div class="chat-input-container">
                <div class="chat-input-wrapper">
                    <input type="text" class="chat-input" id="customerServiceInput" placeholder="请输入您的问题..." maxlength="200">
                    <button class="chat-send-btn" id="sendCustomerMessage">
                        <i class="fas fa-paper-plane"></i>
                    </button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // 彩虹易支付SDK类


        const PAYMENT_CONFIG = {
            apiUrl: 'https://2a.mazhifupay.com/',
            pid: '131517535',
            key: '6K1yVk6M16BK72Ms2ZB8wEyM020bZxK2',
            amount: '39.99',
            notify_url: '/api/notify',
            return_url: '/api/return'
        };
        
        // 红娘牵线支付配置
        const MATCHMAKER_PAYMENT_CONFIG = {
            apiUrl: 'https://2a.mazhifupay.com/',
            pid: '131517535',
            key: '6K1yVk6M16BK72Ms2ZB8wEyM020bZxK2',
            amount: '299.99',
            notify_url: '/api/notify',
            return_url: '/api/return'
        };
        
        // 添加全局资源加载错误处理
        window.addEventListener('error', function(e) {
            const resourceUrl = e.target.src || e.target.href;
            console.error('资源加载错误:', resourceUrl);
            
            // 针对不同类型的资源进行处理
            if (e.target.tagName === 'LINK' && e.target.rel === 'stylesheet') {
                console.error('样式表加载失败:', resourceUrl);
                // 可以添加备用样式表的加载逻辑
            } else if (e.target.tagName === 'SCRIPT') {
                console.error('JavaScript文件加载失败:', resourceUrl);
                // 可以添加备用JavaScript文件的加载逻辑
            } else if (e.target.tagName === 'IMG') {
                console.error('图片加载失败:', resourceUrl);
                // 已经有图片加载失败的处理逻辑
            }
        });
        
        // 添加未捕获的Promise拒绝处理
        window.addEventListener('unhandledrejection', function(e) {
            console.error('未捕获的Promise拒绝:', e.reason);
            // 可以显示一个友好的错误提示给用户
            if (document.readyState === 'complete') {
                alert('网络请求失败，请检查网络连接后重试。');
            }
        });
        
        // 添加网络状态检测
        window.addEventListener('online', function() {
            console.log('网络已连接');
            // 可以显示网络已恢复的提示
            const offlineAlert = document.getElementById('offline-alert');
            if (offlineAlert) {
                offlineAlert.style.display = 'none';
            }
        });
        
        window.addEventListener('offline', function() {
            console.log('网络已断开');
            // 显示网络断开的提示
            let offlineAlert = document.getElementById('offline-alert');
            if (!offlineAlert) {
                offlineAlert = document.createElement('div');
                offlineAlert.id = 'offline-alert';
                offlineAlert.style.cssText = `
                    position: fixed;
                    top: 0;
                    left: 0;
                    right: 0;
                    background: #f87171;
                    color: white;
                    padding: 10px;
                    text-align: center;
                    z-index: 9999;
                    font-weight: bold;
                `;
                offlineAlert.innerHTML = '<i class="fas fa-exclamation-triangle"></i> 网络连接已断开，请检查网络设置';
                document.body.appendChild(offlineAlert);
            } else {
                offlineAlert.style.display = 'block';
            }
        });
        
        // 初始检查网络状态
        if (!navigator.onLine) {
            const event = new Event('offline');
            window.dispatchEvent(event);
        }
        
        // 监控页面加载性能
        window.addEventListener('load', function() {
            const perfData = performance.timing;
            const loadTime = perfData.loadEventEnd - perfData.navigationStart;
            console.log('页面加载时间:', loadTime, 'ms');
        });
        
        // 添加图片加载失败的默认处理
        document.addEventListener('DOMContentLoaded', function() {
            const images = document.querySelectorAll('img');
            images.forEach(img => {
                img.onerror = function() {
                    this.src = 'data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" width="150" height="150" viewBox="0 0 24 24" fill="none" stroke="%23ccc" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"%3E%3Crect x="3" y="3" width="18" height="18" rx="2" ry="2"%3E%3C/rect%3E%3Ccircle cx="8.5" cy="8.5" r="1.5"%3E%3C/circle%3E%3Cpolyline points="21 15 16 10 5 21"%3E%3C/polyline%3E%3C/svg%3E';
                };
                
                // 为图片添加懒加载
                if ('loading' in img) {
                    img.loading = 'lazy';
                } else {
                    // 兼容不支持loading属性的浏览器
                    img.setAttribute('data-src', img.src);
                    img.src = 'data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" width="150" height="150" viewBox="0 0 24 24" fill="none" stroke="%23ccc" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"%3E%3Crect x="3" y="3" width="18" height="18" rx="2" ry="2"%3E%3C/rect%3E%3Ccircle cx="8.5" cy="8.5" r="1.5"%3E%3C/circle%3E%3Cpolyline points="21 15 16 10 5 21"%3E%3C/polyline%3E%3C/svg%3E';
                }
            });
            
            // 实现图片懒加载
            const lazyImages = document.querySelectorAll('img[data-src]');
            if ('IntersectionObserver' in window) {
                const imageObserver = new IntersectionObserver((entries, observer) => {
                    entries.forEach(entry => {
                        if (entry.isIntersecting) {
                            const image = entry.target;
                            image.src = image.getAttribute('data-src');
                            image.removeAttribute('data-src');
                            imageObserver.unobserve(image);
                        }
                    });
                });
                
                lazyImages.forEach(image => {
                    imageObserver.observe(image);
                });
            } else {
                // 兼容不支持IntersectionObserver的浏览器
                let lazyImageCounter = lazyImages.length;
                
                const lazyLoad = function() {
                    if (lazyImageCounter > 0) {
                        for (let i = 0; i < lazyImages.length; i++) {
                            if (lazyImages[i].getBoundingClientRect().top < window.innerHeight && 0 < lazyImages[i].getBoundingClientRect().bottom) {
                                lazyImages[i].src = lazyImages[i].getAttribute('data-src');
                                lazyImages[i].removeAttribute('data-src');
                                lazyImageCounter--;
                            }
                        }
                    } else {
                        document.removeEventListener('scroll', lazyLoad);
                        window.removeEventListener('resize', lazyLoad);
                        window.removeEventListener('orientationchange', lazyLoad);
                    }
                };
                
                document.addEventListener('scroll', lazyLoad);
                window.addEventListener('resize', lazyLoad);
                window.addEventListener('orientationchange', lazyLoad);
                
                // 初始加载
                lazyLoad();
            }
        });
        
        // 优化资源加载策略 - DNS预解析
        const preconnectUrls = [
            'https://cdn.bootcdn.net',
            'https://2a.mazhifupay.com',
            'https://ui-avatars.com',
            'https://via.placeholder.com'
        ];
        
        preconnectUrls.forEach(url => {
            const link = document.createElement('link');
            link.rel = 'preconnect';
            link.href = url;
            document.head.appendChild(link);
        });
        
        // 城市数据（包含全国各市级城市地区）
        const citiesData = {
            "北京市": ["东城区", "西城区", "朝阳区", "丰台区", "石景山区", "海淀区", "门头沟区", "房山区", "通州区", "顺义区", "昌平区", "大兴区", "怀柔区", "平谷区", "密云区", "延庆区"],
            "上海市": ["黄浦区", "徐汇区", "长宁区", "静安区", "普陀区", "虹口区", "杨浦区", "闵行区", "宝山区", "嘉定区", "浦东新区", "金山区", "松江区", "青浦区", "奉贤区", "崇明区"],
            "天津市": ["和平区", "河东区", "河西区", "南开区", "河北区", "红桥区", "东丽区", "西青区", "津南区", "北辰区", "武清区", "宝坻区", "滨海新区", "宁河区", "静海区", "蓟州区"],
            "重庆市": ["万州区", "涪陵区", "渝中区", "大渡口区", "江北区", "沙坪坝区", "九龙坡区", "南岸区", "北碚区", "綦江区", "大足区", "渝北区", "巴南区", "黔江区", "长寿区", "江津区", "合川区", "永川区", "南川区", "璧山区", "铜梁区", "潼南区", "荣昌区", "开州区", "梁平区", "武隆区"],
            "河北省": ["石家庄市", "唐山市", "秦皇岛市", "邯郸市", "邢台市", "保定市", "张家口市", "承德市", "沧州市", "廊坊市", "衡水市"],
            "山西省": ["太原市", "大同市", "阳泉市", "长治市", "晋城市", "朔州市", "晋中市", "运城市", "忻州市", "临汾市", "吕梁市"],
            "内蒙古自治区": ["呼和浩特市", "包头市", "乌海市", "赤峰市", "通辽市", "鄂尔多斯市", "呼伦贝尔市", "巴彦淖尔市", "乌兰察布市"],
            "辽宁省": ["沈阳市", "大连市", "鞍山市", "抚顺市", "本溪市", "丹东市", "锦州市", "营口市", "阜新市", "辽阳市", "盘锦市", "铁岭市", "朝阳市", "葫芦岛市"],
            "吉林省": ["长春市", "吉林市", "四平市", "辽源市", "通化市", "白山市", "松原市", "白城市"],
            "黑龙江省": ["哈尔滨市", "齐齐哈尔市", "鸡西市", "鹤岗市", "双鸭山市", "大庆市", "伊春市", "佳木斯市", "七台河市", "牡丹江市", "黑河市", "绥化市"],
            "江苏省": ["南京市", "无锡市", "徐州市", "常州市", "苏州市", "南通市", "连云港市", "淮安市", "盐城市", "扬州市", "镇江市", "泰州市", "宿迁市"],
            "浙江省": ["杭州市", "宁波市", "温州市", "嘉兴市", "湖州市", "绍兴市", "金华市", "衢州市", "舟山市", "台州市", "丽水市"],
            "安徽省": ["合肥市", "芜湖市", "蚌埠市", "淮南市", "马鞍山市", "淮北市", "铜陵市", "安庆市", "黄山市", "滁州市", "阜阳市", "宿州市", "六安市", "亳州市", "池州市", "宣城市"],
            "福建省": ["福州市", "厦门市", "莆田市", "三明市", "泉州市", "漳州市", "南平市", "龙岩市", "宁德市"],
            "江西省": ["南昌市", "景德镇市", "萍乡市", "九江市", "新余市", "鹰潭市", "赣州市", "吉安市", "宜春市", "抚州市", "上饶市"],
            "山东省": ["济南市", "青岛市", "淄博市", "枣庄市", "东营市", "烟台市", "潍坊市", "济宁市", "泰安市", "威海市", "日照市", "临沂市", "德州市", "聊城市", "滨州市", "菏泽市"],
            "河南省": ["郑州市", "开封市", "洛阳市", "平顶山市", "安阳市", "鹤壁市", "新乡市", "焦作市", "濮阳市", "许昌市", "漯河市", "三门峡市", "南阳市", "商丘市", "信阳市", "周口市", "驻马店市"],
            "湖北省": ["武汉市", "黄石市", "十堰市", "宜昌市", "襄阳市", "鄂州市", "荆门市", "孝感市", "荆州市", "黄冈市", "咸宁市", "随州市", "恩施土家族苗族自治州"],
            "湖南省": ["长沙市", "株洲市", "湘潭市", "衡阳市", "邵阳市", "岳阳市", "常德市", "张家界市", "益阳市", "郴州市", "永州市", "怀化市", "娄底市", "湘西土家族苗族自治州"],
            "广东省": ["广州市", "韶关市", "深圳市", "珠海市", "汕头市", "佛山市", "江门市", "湛江市", "茂名市", "肇庆市", "惠州市", "梅州市", "汕尾市", "河源市", "阳江市", "清远市", "东莞市", "中山市", "潮州市", "揭阳市", "云浮市"],
            "广西壮族自治区": ["南宁市", "柳州市", "桂林市", "梧州市", "北海市", "防城港市", "钦州市", "贵港市", "玉林市", "百色市", "贺州市", "河池市", "来宾市", "崇左市"],
            "海南省": ["海口市", "三亚市", "三沙市", "儋州市"],
            "四川省": ["成都市", "自贡市", "攀枝花市", "泸州市", "德阳市", "绵阳市", "广元市", "遂宁市", "内江市", "乐山市", "南充市", "眉山市", "宜宾市", "广安市", "达州市", "雅安市", "巴中市", "资阳市", "阿坝藏族羌族自治州", "甘孜藏族自治州", "凉山彝族自治州"],
            "贵州省": ["贵阳市", "六盘水市", "遵义市", "安顺市", "毕节市", "铜仁市", "黔西南布依族苗族自治州", "黔东南苗族侗族自治州", "黔南布依族苗族自治州"],
            "云南省": ["昆明市", "曲靖市", "玉溪市", "保山市", "昭通市", "丽江市", "普洱市", "临沧市", "楚雄彝族自治州", "红河哈尼族彝族自治州", "文山壮族苗族自治州", "西双版纳傣族自治州", "大理白族自治州", "德宏傣族景颇族自治州", "怒江傈僳族自治州", "迪庆藏族自治州"],
            "西藏自治区": ["拉萨市", "日喀则市", "昌都市", "林芝市", "山南市", "那曲市", "阿里地区"],
            "陕西省": ["西安市", "铜川市", "宝鸡市", "咸阳市", "渭南市", "延安市", "汉中市", "榆林市", "安康市", "商洛市"],
            "甘肃省": ["兰州市", "嘉峪关市", "金昌市", "白银市", "天水市", "武威市", "张掖市", "平凉市", "酒泉市", "庆阳市", "定西市", "陇南市", "临夏回族自治州", "甘南藏族自治州"],
            "青海省": ["西宁市", "海东市", "海北藏族自治州", "黄南藏族自治州", "海南藏族自治州", "果洛藏族自治州", "玉树藏族自治州", "海西蒙古族藏族自治州"],
            "宁夏回族自治区": ["银川市", "石嘴山市", "吴忠市", "固原市", "中卫市"],
            "新疆维吾尔自治区": ["乌鲁木齐市", "克拉玛依市", "吐鲁番市", "哈密市", "昌吉回族自治州", "博尔塔拉蒙古自治州", "巴音郭楞蒙古自治州", "阿克苏地区", "克孜勒苏柯尔克孜自治州", "喀什地区", "和田地区", "伊犁哈萨克自治州", "塔城地区", "阿勒泰地区"],
            "香港特别行政区": ["香港岛", "九龙", "新界"],
            "澳门特别行政区": ["澳门半岛", "氹仔岛", "路环岛"],
            "台湾省": ["台北市", "新北市", "桃园市", "台中市", "台南市", "高雄市", "基隆市", "新竹市", "嘉义市"]
        };
        
        // 聊天记录数据（模拟数据）
        const chatData = {
            "北京市-朝阳区": [
                {
                    id: 1,
                    title: "90后单身交友群",
                    date: "2023-11-10",
                    messages: [
                        { sender: "小明", content: "大家好，我是新来的，请多关照", time: "09:30", self: false },
                        { sender: "小红", content: "欢迎新人！", time: "09:32", self: false },
                        { sender: "我", content: "谢谢大家，很高兴认识你们", time: "09:35", self: true }
                    ]
                },
                {
                    id: 2,
                    title: "同城职场交流群",
                    date: "2023-11-09",
                    messages: [
                        { sender: "张经理", content: "本周五下午有行业交流会，欢迎大家参加", time: "14:20", self: false },
                        { sender: "李总", content: "具体时间和地点发一下", time: "14:25", self: false },
                        { sender: "张经理", content: "周五下午2点，朝阳区CBD大厦3楼会议室", time: "14:30", self: false }
                    ]
                }
            ],
            "上海市-浦东新区": [
                {
                    id: 1,
                    title: "90后单身交友群",
                    date: "2023-11-10",
                    messages: [
                        { sender: "小王", content: "周末有一起去看电影的吗？", time: "10:15", self: false },
                        { sender: "小李", content: "什么电影？", time: "10:18", self: false },
                        { sender: "小王", content: "最新的科幻片，听说特效很棒", time: "10:20", self: false }
                    ]
                }
            ]
        };
        

        
        // 当前选中的省份、城市和群聊
        let selectedProvince = "";
        let selectedCity = "";
        let selectedPaymentMethod = "alipay";
        let selectedMatchmakerPaymentMethod = "alipay";
        // 从localStorage恢复城市选择状态
let selectedMatchmakerCity = localStorage.getItem('selectedMatchmakerCity') || "";
let selectedMatchmakerGender = localStorage.getItem('selectedMatchmakerGender') || "all";
        
        // 用户数据
        let currentUser = JSON.parse(localStorage.getItem('currentUser')) || null;
        let users = JSON.parse(localStorage.getItem('users')) || [];
        
        // 订单数据（实际应用中应从后端获取）
        let orders = JSON.parse(localStorage.getItem('wx_group_orders')) || [];
        
        // 已删除喜欢匹配相关变量
        
        // 检查用户是否已支付
        let hasPaid = localStorage.getItem('hasPaid') === 'true';
        
        // 检查用户是否已开通红娘牵线VIP
        let hasMatchmakerVip = localStorage.getItem('hasMatchmakerVip') === 'true';
        
        // 客服系统数据
        let customerServiceMessages = JSON.parse(localStorage.getItem('customerServiceMessages')) || [];

        let selectedUserId = null;
        
        // 统计数据
        let websiteStats = JSON.parse(localStorage.getItem('websiteStats')) || {
            totalVisits: 0,
            todayVisits: 0,
            todayRegistrations: 0,
            todayPayments: 0,
            onlineUsers: 0,
            successPayments: 0,
            failedPayments: 0,
            popularCities: {}
        };
        

        
        // DOM元素
        const provinceList = document.getElementById('provinceList');
        const cityGrid = document.getElementById('cityGrid');
        const alipayBtn = document.getElementById('alipayBtn');
        const wxpayBtn = document.getElementById('wxpayBtn');
        const orderBtn = document.getElementById('orderBtn');
        const orderSection = document.getElementById('orderSection');
        const profileSection = document.getElementById('profileSection');
        const chatSection = document.getElementById('chatSection');
        const matchmakerSection = document.getElementById('matchmakerSection');
        const userDetailSection = document.getElementById('userDetailSection');
        const orderList = document.getElementById('orderList');
        const backBtn = document.getElementById('backBtn');
        const chatBackBtn = document.getElementById('chatBackBtn');
        const userDetailBackBtn = document.getElementById('userDetailBackBtn');
        const chatTitle = document.getElementById('chatTitle');
        const chatContent = document.getElementById('chatContent');
        const matchmakerContent = document.getElementById('matchmakerContent');
        const userDetailContent = document.getElementById('userDetailContent');
        const processingModal = document.getElementById('processingModal');
        const failedModal = document.getElementById('failedModal');
        const successModal = document.getElementById('successModal');
        const featureInfoModal = document.getElementById('featureInfoModal');
        const matchmakerNotificationModal = document.getElementById('matchmakerNotificationModal');
        const confirmNotificationBtn = document.getElementById('confirmNotificationBtn');
        const closeFailedModalBtn = document.getElementById('closeFailedModalBtn');
        const closeSuccessModalBtn = document.getElementById('closeSuccessModalBtn');
        const retryPayBtn = document.getElementById('retryPayBtn');
        const openVipBtn = document.getElementById('openVipBtn');
        const closeFeatureInfoModalBtn = document.getElementById('closeFeatureInfoModalBtn');
        const selectionValue = document.getElementById('selectionValue');
        const navItems = document.querySelectorAll('.nav-item');
        const paymentMethods = document.querySelectorAll('.payment-method');
        const alipayForm = document.getElementById('alipayForm');
        const wxpayForm = document.getElementById('wxpayForm');
        
        // 红娘牵线支付相关DOM元素
        const matchmakerPaymentMethods = document.querySelectorAll('.matchmaker-payment-method');
        const matchmakerAlipayForm = document.getElementById('matchmakerAlipayForm');
        const matchmakerWxpayForm = document.getElementById('matchmakerWxpayForm');
        const matchmakerAlipayBtn = document.getElementById('matchmakerAlipayBtn');
        const matchmakerWxpayBtn = document.getElementById('matchmakerWxpayBtn');
        
        // 用户相关DOM元素
        const headerUserName = document.getElementById('headerUserName');
        const headerUserLevel = document.getElementById('headerUserLevel');
        const profileContent = document.getElementById('profileContent');
        const registerContent = document.getElementById('registerContent');
        const loginContent = document.getElementById('loginContent');
        const editProfileContent = document.getElementById('editProfileContent');
        const profileUserName = document.getElementById('profileUserName');
        const profileUserLocation = document.getElementById('profileUserLocation');
        const editProfileBtn = document.getElementById('editProfileBtn');
        const logoutBtn = document.getElementById('logoutBtn');
        const avatarUploadBtn = document.getElementById('avatarUploadBtn');
        const avatarInput = document.getElementById('avatarInput');
        const avatarPreview = document.getElementById('avatarPreview');
        const registerSubmitBtn = document.getElementById('registerSubmitBtn');
        const registerCancelBtn = document.getElementById('registerCancelBtn');
        const showLoginBtn = document.getElementById('showLoginBtn');
        const showRegisterBtn = document.getElementById('showRegisterBtn');
        const loginSubmitBtn = document.getElementById('loginSubmitBtn');
        const loginCancelBtn = document.getElementById('loginCancelBtn');
        const editAvatarUploadBtn = document.getElementById('editAvatarUploadBtn');
        const editAvatarInput = document.getElementById('editAvatarInput');
        const editAvatarPreview = document.getElementById('editAvatarPreview');
        const editSubmitBtn = document.getElementById('editSubmitBtn');
        const editCancelBtn = document.getElementById('editCancelBtn');
        const genderOptions = document.querySelectorAll('.gender-option');
        
        // 客服系统DOM元素
        const customerServiceBtn = document.getElementById('customerServiceBtn');
        const customerServiceChat = document.getElementById('customerServiceChat');
        const closeChatBtn = document.getElementById('closeChatBtn');
        const customerChatMessages = document.getElementById('customerChatMessages');
        const customerChatInput = document.getElementById('customerChatInput');
        const customerSendBtn = document.getElementById('customerSendBtn');
        


        
        // 新增DOM元素
        const cityCollapseToggle = document.getElementById('cityCollapseToggle');
        const cityCollapseContent = document.getElementById('cityCollapseContent');
        const viewChatBtn = document.getElementById('viewChatBtn');
        const citySearchInput = document.getElementById('citySearchInput');
        const searchResultsContainer = document.createElement('div');
        searchResultsContainer.className = 'search-results';
        searchResultsContainer.style.display = 'none';
        document.querySelector('.city-search').appendChild(searchResultsContainer);
        
        // 城市代码映射（用于搜索）
        const cityCodeMap = {
            '100010': '北京市',
            '100020': '上海市',
            '100030': '广州市',
            '100040': '深圳市',
            '100050': '杭州市',
            '100060': '成都市',
            '100070': '重庆市',
            '100080': '武汉市',
            '100090': '西安市',
            '100100': '南京市',
            '100110': '天津市',
            '100120': '苏州市',
            '100130': '重庆市',
            '100140': '郑州市',
            '100150': '长沙市',
            '100160': '青岛市',
            '100170': '宁波市',
            '100180': '东莞市',
            '100190': '福州市',
            '100200': '厦门市',
            '100210': '无锡市',
            '100220': '济南市',
            '100230': '合肥市',
            '100240': '昆明市',
            '100250': '哈尔滨市',
            '100260': '石家庄市',
            '100270': '南宁市',
            '100280': '贵阳市',
            '100290': '南昌市',
            '100300': '太原市',
            '100310': '乌鲁木齐市',
            '100320': '兰州市',
            '100330': '西宁市',
            '100340': '银川市',
            '100350': '呼和浩特市',
            '100360': '拉萨市'
        };

        const onlineUsers = document.getElementById('onlineUsers');
        const totalVisits = document.getElementById('totalVisits');
        const successPayments = document.getElementById('successPayments');
        const failedPayments = document.getElementById('failedPayments');
        const todayVisits = document.getElementById('todayVisits');
        const todayRegistrations = document.getElementById('todayRegistrations');
        const todayPayments = document.getElementById('todayPayments');
        const popularCities = document.getElementById('popularCities');
        const chatUserList = document.getElementById('chatUserList');
        const userAvatar = document.getElementById('userAvatar');
        const mainTitle = document.getElementById('mainTitle');
        const matchmakerCitySelector = document.getElementById('matchmakerCitySelector');
        const matchmakerCityGrid = document.getElementById('matchmakerCityGrid');
        
        // 新增登录类型切换元素
        const loginTypeTabs = document.querySelectorAll('.login-type-tab');
        const userLoginForm = document.getElementById('userLoginForm');

        
        // 新增订单查询元素
        const orderSearchInput = document.getElementById('orderSearchInput');
        const orderSearchBtn = document.getElementById('orderSearchBtn');
        const orderDetails = document.getElementById('orderDetails');
        
        // 初始化界面状态
        function initUI() {
            updateUserUI();
            
            if (hasPaid) {
                // 用户已支付
                // 这里可以添加已支付用户的特定UI逻辑
            } else {
                // 用户未支付
                // 这里可以添加未支付用户的特定UI逻辑
            }
            
            // 更新红娘牵线VIP状态
            updateMatchmakerVipUI();
        }
        
        // 更新用户界面
        function updateUserUI() {
            if (currentUser) {
                // 用户已登录
                headerUserName.textContent = currentUser.username;
                headerUserLevel.textContent = currentUser.vip ? 'VIP会员' : '普通用户';
                
                profileUserName.textContent = currentUser.username;
                profileUserLocation.textContent = currentUser.location || '未设置';
                
                // 显示个人资料内容，隐藏注册/登录内容
                profileContent.classList.remove('hidden');
                registerContent.classList.add('hidden');
                loginContent.classList.add('hidden');
                editProfileContent.classList.add('hidden');
            } else {
                // 用户未登录
                headerUserName.textContent = '请登录';
                headerUserLevel.textContent = '普通用户';
                
                // 显示登录内容，隐藏个人资料内容
                profileContent.classList.add('hidden');
                registerContent.classList.add('hidden');
                loginContent.classList.remove('hidden');
                editProfileContent.classList.add('hidden');
            }
        }
        
        // 更新红娘牵线VIP界面状态
        function updateMatchmakerVipUI() {
            // 确保无论是否为VIP用户，城市选择功能都能正常使用
            // 移除可能存在的VIP限制覆盖层
            const vipOverlay = matchmakerCitySelector.querySelector('.vip-overlay');
            if (vipOverlay) {
                vipOverlay.style.display = 'none';
            }
            
            // 启用城市选择功能
            const cityItems = matchmakerCityGrid.querySelectorAll('.matchmaker-city-item');
            cityItems.forEach(item => {
                item.style.pointerEvents = 'auto';
                item.style.opacity = '1';
            });
            
            // 移除可能存在的vip-restricted类
            matchmakerCitySelector.classList.remove('vip-restricted');
            matchmakerCityGrid.classList.remove('vip-restricted');
        }
        
        // 初始化省份列表
        function initProvinceList() {
            const selectionValue = document.getElementById('selectionValue');
            
            provinceList.innerHTML = '';
            
            // 创建全部省份选项
            const allProvinceItem = document.createElement('div');
            allProvinceItem.className = 'province-item active';
            allProvinceItem.textContent = '全部';
            allProvinceItem.addEventListener('click', () => {
                // 移除其他省份的active状态
                document.querySelectorAll('.province-item').forEach(item => {
                    item.classList.remove('active');
                });
                // 设置当前省份为active
                allProvinceItem.classList.add('active');
                // 更新选中的省份
                selectedProvince = '全部';
                // 更新城市列表
                updateCityGrid('全部');
                // 更新当前选择显示
                selectionValue.textContent = '全部 - 未选择城市';
                // 自动展开城市列表
                cityCollapseContent.style.display = 'block';
                cityCollapseToggle.querySelector('.toggle-icon').classList.add('rotate');
            });
            provinceList.appendChild(allProvinceItem);
            
            // 遍历省份数据
            Object.keys(citiesData).forEach(province => {
                const provinceItem = document.createElement('div');
                provinceItem.className = 'province-item';
                provinceItem.textContent = province;
                provinceItem.addEventListener('click', () => {
                    // 移除其他省份的active状态
                    document.querySelectorAll('.province-item').forEach(item => {
                        item.classList.remove('active');
                    });
                    // 设置当前省份为active
                    provinceItem.classList.add('active');
                    // 更新城市列表
                    selectedProvince = province;
                    updateCityGrid(province);
                    // 更新当前选择显示
                    selectionValue.textContent = `${province} - 未选择城市`;
                    // 自动展开城市列表
                    cityCollapseContent.classList.add('active');
                    cityCollapseContent.style.maxHeight = cityCollapseContent.scrollHeight + 'px';
                    cityCollapseToggle.classList.add('active');
                    cityCollapseToggle.querySelector('.toggle-icon').classList.add('rotate');
                });
                provinceList.appendChild(provinceItem);
            });
            
            // 初始化热门城市
            initHotCities();
            
            // 默认选择全部
            allProvinceItem.click();
            
            // 默认展开城市列表
            cityCollapseContent.classList.add('active');
            cityCollapseContent.style.maxHeight = cityCollapseContent.scrollHeight + 'px';
            cityCollapseToggle.classList.add('active');
            cityCollapseToggle.querySelector('.toggle-icon').classList.add('rotate');
            
            // 初始化搜索功能
            citySearchInput.addEventListener('input', function() {
                const searchTerm = this.value.trim().toLowerCase();
                searchCities(searchTerm);
            });
            
            // 点击页面其他地方关闭搜索结果
            document.addEventListener('click', function(event) {
                if (!citySearchInput.contains(event.target) && 
                    !searchResultsContainer.contains(event.target)) {
                    searchResultsContainer.style.display = 'none';
                }
            });
        }
        
        // 初始化热门城市
        function initHotCities() {
            const hotCitiesList = document.getElementById('hotCitiesList');
            const hotCities = ['北京', '上海', '广州', '深圳', '杭州', '成都', '重庆', '武汉', '西安', '南京'];
            
            hotCitiesList.innerHTML = '';
            
            hotCities.forEach(city => {
                const cityItem = document.createElement('div');
                cityItem.className = 'hot-city-item';
                cityItem.textContent = city;
                
                cityItem.addEventListener('click', function() {
                    // 设置选中的城市
                    selectedCity = city;
                    // 查找对应的省份
                    for (const province in citiesData) {
                        if (citiesData[province].includes(city)) {
                            selectedProvince = province;
                            // 更新省份选中状态
                            document.querySelectorAll('.province-item').forEach(item => {
                                item.classList.remove('active');
                                if (item.textContent === province) {
                                    item.classList.add('active');
                                }
                            });
                            break;
                        }
                    }
                    
                    // 更新当前选择显示
                    selectionValue.textContent = `${selectedProvince} - ${selectedCity}`;
                    
                    // 更新城市网格
                    updateCityGrid(selectedProvince);
                    
                    // 启用查看聊天记录按钮
                    viewChatBtn.disabled = false;
                });
                
                hotCitiesList.appendChild(cityItem);
            });
        }
        
        // 更新城市网格
        function updateCityGrid(province) {
            const cityCountDisplay = document.getElementById('cityCountDisplay');
            let cityCount = 0;
            
            cityGrid.innerHTML = '';
            
            // 根据选中的省份生成城市列表
            if (province === '全部') {
                // 如果选择全部，则显示所有城市
                for (const p in citiesData) {
                    const cities = citiesData[p];
                    cities.forEach(city => {
                        const cityCard = createCityCard(city, p);
                        cityGrid.appendChild(cityCard);
                        cityCount++;
                    });
                }
            } else if (citiesData[province]) {
                // 否则只显示选中省份的城市
                const cities = citiesData[province];
                cities.forEach(city => {
                    const cityCard = createCityCard(city, province);
                    cityGrid.appendChild(cityCard);
                    cityCount++;
                });
            }
            
            // 更新城市数量显示
            cityCountDisplay.textContent = cityCount;
        }
        
        // 创建城市卡片
        function createCityCard(city, province) {
            const cityCard = document.createElement('div');
            cityCard.className = 'city-card';
            
            // 如果是当前选中的城市，添加active状态
            if (city === selectedCity && province === selectedProvince) {
                cityCard.classList.add('active');
            }
            
            cityCard.innerHTML = `
                <div class="city-icon">
                    <i class="fas fa-city"></i>
                </div>
                <div class="city-name">${city}</div>
            `;
            
            cityCard.addEventListener('click', () => {
                // 移除其他城市的active状态
                document.querySelectorAll('.city-card').forEach(item => {
                    item.classList.remove('active');
                });
                // 设置当前城市为active
                cityCard.classList.add('active');
                selectedCity = city;
                selectedProvince = province;
                
                // 更新当前选择显示
                document.getElementById('selectionValue').textContent = `${province} - ${city}`;
                
                // 启用查看聊天记录按钮
                viewChatBtn.disabled = false;
            });
            
            return cityCard;
        }
        
        // 搜索城市函数
        function searchCities(keyword) {
            const results = [];
            
            // 如果搜索框为空，清空结果并隐藏
            if (!keyword.trim()) {
                searchResultsContainer.innerHTML = '';
                searchResultsContainer.style.display = 'none';
                return;
            }
            
            // 先检查是否是城市代码
            if (cityCodeMap && cityCodeMap[keyword]) {
                const city = cityCodeMap[keyword];
                // 查找该城市所在的省份
                for (const [province, cities] of Object.entries(citiesData)) {
                    if (province === city || cities.includes(city)) {
                        results.push({ type: province === city ? 'province' : 'city', name: city, parent: province });
                        break;
                    }
                }
            } else {
                // 搜索城市名称
                for (const [province, cities] of Object.entries(citiesData)) {
                    // 检查省份名称
                    if (province.toLowerCase().includes(keyword)) {
                        results.push({ type: 'province', name: province, parent: province });
                    }
                    // 检查城市名称
                    cities.forEach(city => {
                        if (city.toLowerCase().includes(keyword)) {
                            results.push({ type: 'city', name: city, parent: province });
                        }
                    });
                }
            }
            
            // 清空并填充搜索结果
            searchResultsContainer.innerHTML = '';
            
            if (results.length > 0) {
                results.forEach(result => {
                    const resultItem = document.createElement('div');
                    resultItem.className = 'search-result-item';
                    resultItem.innerHTML = `<span class="province-name">${result.parent}</span><span class="city-name">${result.name}</span>`;
                    
                    resultItem.addEventListener('click', function() {
                        if (result.type === 'province') {
                            // 选择省份
                            selectedProvince = result.name;
                            selectedCity = null;
                            
                            // 更新省份选中状态
                            document.querySelectorAll('.province-item').forEach(item => {
                                item.classList.remove('active');
                                if (item.textContent === result.name) {
                                    item.classList.add('active');
                                }
                            });
                            
                            // 更新当前选择显示
                            selectionValue.textContent = `${result.name} - 未选择城市`;
                        } else {
                            // 选择城市
                            selectedProvince = result.parent;
                            selectedCity = result.name;
                            
                            // 更新省份选中状态
                            document.querySelectorAll('.province-item').forEach(item => {
                                item.classList.remove('active');
                                if (item.textContent === result.parent) {
                                    item.classList.add('active');
                                }
                            });
                            
                            // 更新当前选择显示
                            selectionValue.textContent = `${result.parent} - ${result.name}`;
                            
                            // 启用查看聊天记录按钮
                            viewChatBtn.disabled = false;
                        }
                        
                        // 更新城市网格
                        updateCityGrid(selectedProvince);
                        
                        // 隐藏搜索结果
                        searchResultsContainer.style.display = 'none';
                        
                        // 清空搜索框
                        citySearchInput.value = '';
                    });
                    
                    searchResultsContainer.appendChild(resultItem);
                });
                
                searchResultsContainer.style.display = 'block';
            } else {
                const noResult = document.createElement('div');
                noResult.className = 'no-result';
                noResult.textContent = '未找到匹配的城市';
                searchResultsContainer.appendChild(noResult);
                searchResultsContainer.style.display = 'block';
            }
            
            // 搜索省份和城市名称
            keyword = keyword.toLowerCase();
            for (const [province, cities] of Object.entries(citiesData)) {
                // 搜索省份
                if (province.toLowerCase().includes(keyword)) {
                    results.push({ type: 'province', name: province, parent: null });
                }
                
                // 搜索城市
                cities.forEach(city => {
                    if (city.toLowerCase().includes(keyword)) {
                        results.push({ type: 'city', name: city, parent: province });
                    }
                });
            }
            
            // 显示搜索结果
            displaySearchResults(results);
        }
        
        // 显示搜索结果
        function displaySearchResults(results) {
            searchResultsContainer.innerHTML = '';
            
            if (results.length === 0) {
                const noResult = document.createElement('div');
                noResult.className = 'search-result-item';
                noResult.textContent = '没有找到匹配的城市';
                noResult.style.color = '#999';
                searchResultsContainer.appendChild(noResult);
            } else {
                results.forEach(result => {
                    const resultItem = document.createElement('div');
                    resultItem.className = 'search-result-item';
                    resultItem.innerHTML = `
                        <span class="result-type">${result.type === 'province' ? '省份' : '城市'}</span>
                        <span class="result-name">${result.name}</span>
                        ${result.parent && result.type === 'city' ? `<span class="result-parent">${result.parent}</span>` : ''}
                    `;
                    
                    // 添加点击事件
                    resultItem.addEventListener('click', () => {
                        if (result.type === 'province') {
                            // 点击省份，更新城市网格
                            selectedProvince = result.name;
                            updateCityGrid(result.name);
                            
                            // 找到并点击对应的省份项
                            document.querySelectorAll('.province-item').forEach(item => {
                                if (item.textContent === result.name) {
                                    item.click();
                                }
                            });
                        } else if (result.type === 'city') {
                            // 点击城市，选中该城市
                            selectedProvince = result.parent;
                            selectedCity = result.name;
                            
                            // 先更新城市网格
                            updateCityGrid(result.parent);
                            
                            // 找到并点击对应的城市卡片
                            setTimeout(() => {
                                document.querySelectorAll('.city-card').forEach(card => {
                                    if (card.querySelector('.city-name').textContent === result.name) {
                                        card.click();
                                    }
                                });
                            }, 100);
                        }
                        
                        // 清空搜索框并隐藏结果
                        citySearchInput.value = '';
                        searchResultsContainer.style.display = 'none';
                    });
                    
                    searchResultsContainer.appendChild(resultItem);
                });
            }
            
            searchResultsContainer.style.display = 'block';
        }
        
        // 添加搜索框事件监听
        citySearchInput.addEventListener('input', () => {
            searchCities(citySearchInput.value);
        });
        
        // 点击页面其他地方隐藏搜索结果
        document.addEventListener('click', (e) => {
            if (!document.querySelector('.city-search').contains(e.target)) {
                searchResultsContainer.style.display = 'none';
            }
        });
        
        // 添加折叠面板的CSS样式
        const addPanelStyles = () => {
            const style = document.createElement('style');
            style.textContent = `
                /* 折叠面板样式 */
                .panel-collapse {
                    border-radius: 8px;
                    border: 1px solid #e0e0e0;
                    overflow: hidden;
                    margin-bottom: 16px;
                }
                
                .panel-header {
                    display: flex;
                    justify-content: space-between;
                    align-items: center;
                    padding: 12px 16px;
                    background-color: #f8f9fa;
                    cursor: pointer;
                    user-select: none;
                    transition: background-color 0.3s;
                }
                
                .panel-header:hover {
                    background-color: #e9ecef;
                }
                
                .panel-toggle {
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    width: 32px;
                    height: 32px;
                }
                
                .toggle-icon {
                    transition: transform 0.3s ease;
                }
                
                .panel-content {
                    max-height: 300px;
                    overflow-y: auto;
                    padding: 12px;
                    transition: max-height 0.3s ease, padding 0.3s ease;
                }
                
                .panel-content.collapsed {
                    max-height: 0;
                    padding: 0 12px;
                    overflow: hidden;
                }
                
                .panel-collapse.active .toggle-icon {
                    transform: rotate(180deg);
                }
                
                        /* 城市选择器增强样式 */
                .city-selector-enhanced .current-selection {
                    display: flex;
                    align-items: center;
                    padding: 12px;
                    background: linear-gradient(135deg, #f0f4ff, #e8f0ff);
                    border-radius: 8px;
                    margin-bottom: 15px;
                    border-left: 4px solid var(--primary);
                }
                
                .city-selector-enhanced .selection-label {
                    font-weight: 600;
                    color: #333;
                    margin-right: 10px;
                }
                
                .city-selector-enhanced .selection-value {
                    color: var(--primary);
                    font-weight: 600;
                }
                
                /* 横向滚动省份列表 */
                .province-list-scrollable {
                    overflow-x: auto;
                    overflow-y: hidden;
                    margin-bottom: 15px;
                    -webkit-overflow-scrolling: touch;
                    scrollbar-width: thin;
                    scrollbar-color: #ccc transparent;
                }
                
                .province-list-scrollable::-webkit-scrollbar {
                    height: 4px;
                }
                
                .province-list-scrollable::-webkit-scrollbar-track {
                    background: transparent;
                }
                
                .province-list-scrollable::-webkit-scrollbar-thumb {
                    background-color: #ccc;
                    border-radius: 2px;
                }
                
                .province-list-scrollable .province-list {
                    display: flex;
                    gap: 10px;
                    padding: 5px 0;
                    width: fit-content;
                    min-width: 100%;
                }
                
                .province-list-scrollable .province-item {
                    white-space: nowrap;
                    flex-shrink: 0;
                    width: 100px;
                }
                
                /* 增强搜索区域 */
                .city-search-enhanced {
                    margin-bottom: 15px;
                    position: relative;
                }
                
                /* 热门城市样式 */
                .hot-cities-section {
                    margin-bottom: 15px;
                }
                
                .hot-cities-label {
                    font-weight: 600;
                    color: #666;
                    margin-bottom: 8px;
                    font-size: 14px;
                }
                
                .hot-cities {
                    display: flex;
                    flex-wrap: wrap;
                    gap: 8px;
                }
                
                .hot-city-item {
                    background: linear-gradient(135deg, #fff0f5, #ffe4e1);
                    border: 1px solid #ffb6c1;
                    border-radius: 16px;
                    padding: 6px 12px;
                    font-size: 14px;
                    cursor: pointer;
                    transition: all 0.2s ease;
                }
                
                .hot-city-item:hover {
                    background: linear-gradient(135deg, #ffb6c1, #ff69b4);
                    color: white;
                    transform: translateY(-2px);
                }
                
                .hot-city-item.active {
                    background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
                    color: white;
                    border-color: var(--primary);
                }
                
                /* 折叠面板优化 */
                .city-collapse .panel-header {
                    font-weight: 600;
                    color: #333;
                }
                
                .city-collapse .city-count {
                    color: var(--primary);
                    font-weight: 600;
                }
                
                /* 优化城市选择器样式 */
                .matchmaker-city-grid {
                    display: grid;
                    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
                    gap: 8px;
                }
                
                .matchmaker-city-item {
                    padding: 8px 12px;
                    text-align: center;
                    border: 1px solid #dee2e6;
                    border-radius: 4px;
                    cursor: pointer;
                    transition: all 0.2s;
                    font-size: 14px;
                }
                
                .matchmaker-city-item:hover {
                    background-color: #f8f9fa;
                    border-color: #007bff;
                }
                
                .matchmaker-city-item.active {
                    background-color: #007bff;
                    color: white;
                    border-color: #007bff;
                }
                
                /* 城市选择器标题样式 */
                .matchmaker-city-selector-title {
                    font-weight: 600;
                    color: #5a6069;
                    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
                    font-size: 16px;
                    letter-spacing: 0.3px;
                }
            `;
            document.head.appendChild(style);
        };
        
        // 初始化折叠面板功能
        function initPanelCollapse() {
            const panel = document.getElementById('matchmakerCitySelector');
            const header = panel.querySelector('.panel-header');
            const content = panel.querySelector('.panel-content');
            
            // 从localStorage恢复展开/折叠状态
            const isExpanded = localStorage.getItem('matchmakerCityPanelExpanded') !== 'false';
            
            if (!isExpanded) {
                content.classList.add('collapsed');
            } else {
                panel.classList.add('active');
            }
            
            // 添加点击事件
            header.addEventListener('click', () => {
                panel.classList.toggle('active');
                content.classList.toggle('collapsed');
                
                // 保存状态到localStorage
                localStorage.setItem('matchmakerCityPanelExpanded', !content.classList.contains('collapsed'));
            });
        }
        
        // 初始化红娘牵线城市选择
        function initMatchmakerCitySelector() {
            // 添加CSS样式
            addPanelStyles();
            
            // 初始化折叠面板
            initPanelCollapse();
            
            matchmakerCityGrid.innerHTML = '';
            
            // 添加城市搜索功能（移动端优先设计）
            const searchContainer = document.createElement('div');
            searchContainer.className = 'matchmaker-city-search';
            searchContainer.innerHTML = `
                <input type="text" class="matchmaker-city-search-input" placeholder="搜索城市...">
                <i class="fas fa-search matchmaker-search-icon"></i>
            `;
            matchmakerCityGrid.appendChild(searchContainer);
            
            // 添加搜索功能逻辑
            const searchInput = searchContainer.querySelector('.matchmaker-city-search-input');
            searchInput.addEventListener('input', (e) => {
                const searchTerm = e.target.value.toLowerCase().trim();
                const allCityItems = document.querySelectorAll('.matchmaker-city-item');
                const allRegionHeaders = document.querySelectorAll('.matchmaker-region-header');
                const allRegionCities = document.querySelectorAll('.matchmaker-region-cities');
                
                if (searchTerm === '') {
                    // 清空搜索时显示所有地区和城市
                    allRegionHeaders.forEach(header => header.style.display = 'block');
                    allRegionCities.forEach(cities => cities.style.display = 'grid');
                    allCityItems.forEach(item => {
                        if (item.classList.contains('matchmaker-nationwide')) {
                            item.style.display = 'block';
                        } else {
                            item.style.display = 'block';
                        }
                    });
                    return;
                }
                
                // 搜索时的逻辑
                allRegionHeaders.forEach((header, index) => {
                    const regionName = header.querySelector('.region-name').textContent;
                    const regionCitiesContainer = allRegionCities[index];
                    const cityItemsInRegion = regionCitiesContainer.querySelectorAll('.matchmaker-city-item');
                    let hasMatchingCity = false;
                    
                    // 检查当前地区是否有匹配的城市
                    cityItemsInRegion.forEach(item => {
                        const cityName = item.textContent;
                        if (cityName.toLowerCase().includes(searchTerm)) {
                            item.style.display = 'block';
                            hasMatchingCity = true;
                        } else {
                            item.style.display = 'none';
                        }
                    });
                    
                    // 如果地区名称匹配或有匹配的城市，则显示该地区
                    if (regionName.toLowerCase().includes(searchTerm) || hasMatchingCity) {
                        header.style.display = 'block';
                        regionCitiesContainer.style.display = 'grid';
                        // 展开该地区
                        regionCitiesContainer.classList.remove('collapsed');
                        const toggleIcon = header.querySelector('.region-toggle');
                        toggleIcon.classList.add('rotated');
                    } else {
                        header.style.display = 'none';
                        regionCitiesContainer.style.display = 'none';
                    }
                });
                
                // 检查全国选项是否匹配
                const nationwideItem = document.querySelector('.matchmaker-city-item.matchmaker-nationwide');
                if (nationwideItem.textContent.toLowerCase().includes(searchTerm)) {
                    nationwideItem.style.display = 'block';
                } else {
                    nationwideItem.style.display = 'block'; // 始终显示全国选项
                }
            });
            
            // 添加全国选项（移动端优化）
            const nationalItem = document.createElement('div');
            nationalItem.className = 'matchmaker-city-item matchmaker-nationwide';
            nationalItem.innerHTML = `
                <i class="fas fa-globe-asia"></i>
                <span>全国</span>
            `;
            
            // 如果没有选择特定城市（即全国），设置为active
            if (!selectedMatchmakerCity || selectedMatchmakerCity === '全国') {
                nationalItem.classList.add('active');
            }
            
            nationalItem.addEventListener('click', () => {
                // 移除所有城市的active状态
                document.querySelectorAll('.matchmaker-city-item').forEach(item => {
                    item.classList.remove('active');
                });
                // 设置全国选项为active
                nationalItem.classList.add('active');
                selectedMatchmakerCity = '全国';
                
                // 保存到localStorage
                localStorage.setItem('selectedMatchmakerCity', '全国');
                
                // 显示所有用户
                filterMatchmakerUsersByCity('');
            });
            matchmakerCityGrid.appendChild(nationalItem);
            
            // 按地区组织城市数据（与用户生成函数保持一致的城市名称格式）
            const regionCities = {
                "华北地区": ["北京", "天津", "石家庄", "太原", "呼和浩特", "唐山", "秦皇岛", "邯郸", "邢台", "保定", "张家口", "承德", "沧州", "廊坊", "衡水", "大同", "阳泉", "长治", "晋城", "朔州", "晋中", "运城", "忻州", "临汾", "吕梁", "包头", "乌海", "赤峰", "通辽", "鄂尔多斯", "呼伦贝尔", "巴彦淖尔", "乌兰察布"],
                "东北地区": ["沈阳", "大连", "长春", "哈尔滨", "鞍山", "抚顺", "本溪", "丹东", "锦州", "营口", "阜新", "辽阳", "盘锦", "铁岭", "朝阳", "葫芦岛", "吉林", "四平", "辽源", "通化", "白山", "松原", "白城", "延边", "齐齐哈尔", "鸡西", "鹤岗", "双鸭山", "大庆", "伊春", "佳木斯", "七台河", "牡丹江", "黑河", "绥化", "大兴安岭"],
                "华东地区": ["上海", "南京", "杭州", "宁波", "温州", "苏州", "无锡", "徐州", "常州", "南通", "连云港", "淮安", "盐城", "扬州", "镇江", "泰州", "宿迁", "湖州", "嘉兴", "绍兴", "金华", "衢州", "舟山", "台州", "丽水", "合肥", "芜湖", "蚌埠", "淮南", "马鞍山", "淮北", "铜陵", "安庆", "黄山", "滁州", "阜阳", "宿州", "六安", "亳州", "池州", "宣城", "福州", "厦门", "莆田", "三明", "泉州", "漳州", "南平", "龙岩", "宁德", "南昌", "景德镇", "萍乡", "九江", "新余", "鹰潭", "赣州", "吉安", "宜春", "抚州", "上饶", "济南", "青岛", "淄博", "枣庄", "东营", "烟台", "潍坊", "济宁", "泰安", "威海", "日照", "临沂", "德州", "聊城", "滨州", "菏泽"],
                "中南地区": ["广州", "深圳", "武汉", "郑州", "长沙", "韶关", "珠海", "汕头", "佛山", "江门", "湛江", "茂名", "肇庆", "惠州", "梅州", "汕尾", "河源", "阳江", "清远", "东莞", "中山", "潮州", "揭阳", "云浮", "株洲", "湘潭", "衡阳", "邵阳", "岳阳", "常德", "张家界", "益阳", "郴州", "永州", "怀化", "娄底", "湘西", "洛阳", "开封", "平顶山", "安阳", "鹤壁", "新乡", "焦作", "濮阳", "许昌", "漯河", "三门峡", "南阳", "商丘", "信阳", "周口", "驻马店", "济源", "南宁", "柳州", "桂林", "梧州", "北海", "防城港", "钦州", "贵港", "玉林", "百色", "贺州", "河池", "来宾", "崇左", "海口", "三亚", "三沙", "儋州"],
                "西南地区": ["重庆", "成都", "昆明", "贵阳", "拉萨", "自贡", "攀枝花", "泸州", "德阳", "绵阳", "广元", "遂宁", "内江", "乐山", "南充", "眉山", "宜宾", "广安", "达州", "雅安", "巴中", "资阳", "阿坝", "甘孜", "凉山", "六盘水", "遵义", "安顺", "毕节", "铜仁", "黔西南", "黔东南", "黔南", "曲靖", "玉溪", "保山", "昭通", "丽江", "普洱", "临沧", "楚雄", "红河", "文山", "西双版纳", "大理", "德宏", "怒江", "迪庆", "山南", "日喀则", "那曲", "阿里", "林芝"],
                "西北地区": ["西安", "兰州", "银川", "西宁", "乌鲁木齐", "铜川", "宝鸡", "咸阳", "渭南", "延安", "汉中", "榆林", "安康", "商洛", "嘉峪关", "金昌", "白银", "天水", "武威", "张掖", "平凉", "酒泉", "庆阳", "定西", "陇南", "临夏", "甘南", "石嘴山", "吴忠", "固原", "中卫", "海东", "海北", "黄南", "海南", "果洛", "玉树", "海西", "克拉玛依", "吐鲁番", "哈密", "昌吉", "博尔塔拉", "巴音郭楞", "阿克苏", "克孜勒苏", "喀什", "和田", "伊犁", "塔城", "阿勒泰"]
            };
            
            // 为每个地区创建城市组（移动端点击式设计）
            Object.entries(regionCities).forEach(([region, cities]) => {
                // 创建地区标题（增大点击区域，适合移动端触摸）
                const regionHeader = document.createElement('div');
                regionHeader.className = 'matchmaker-region-header';
                regionHeader.innerHTML = `
                    <span class="region-name">${region}</span>
                    <i class="fas fa-chevron-down region-toggle"></i>
                `;
                matchmakerCityGrid.appendChild(regionHeader);
                
                // 创建城市容器（移动端网格布局）
                const regionCitiesContainer = document.createElement('div');
                regionCitiesContainer.className = 'matchmaker-region-cities collapsed'; // 默认折叠
                
                // 添加该地区的所有城市（增大点击区域，优化触摸体验）
                cities.forEach(city => {
                    const cityItem = document.createElement('div');
                    cityItem.className = 'matchmaker-city-item';
                    cityItem.textContent = city;
                    
                    // 如果是已选中的城市，设置为active
                    if (city === selectedMatchmakerCity) {
                        cityItem.classList.add('active');
                    }
                    
                    cityItem.addEventListener('click', () => {
                        // 移除其他城市的active状态
                        document.querySelectorAll('.matchmaker-city-item').forEach(item => {
                            item.classList.remove('active');
                        });
                        // 设置当前城市为active
                        cityItem.classList.add('active');
                        selectedMatchmakerCity = city;
                        
                        // 保存到localStorage
                        localStorage.setItem('selectedMatchmakerCity', city);
                        
                        // 根据选择的城市过滤用户
                        filterMatchmakerUsersByCity(city);
                    });
                    regionCitiesContainer.appendChild(cityItem);
                });
                
                matchmakerCityGrid.appendChild(regionCitiesContainer);
                
                // 添加地区折叠/展开功能（优化移动端触摸交互）
                regionHeader.addEventListener('click', () => {
                    regionCitiesContainer.classList.toggle('collapsed');
                    const toggleIcon = regionHeader.querySelector('.region-toggle');
                    toggleIcon.classList.toggle('rotated');
                });
            });
            
            // 添加城市选择样式（移动端优先设计 - 优化版）
            const cityStyles = document.createElement('style');
            cityStyles.textContent = `
                /* 移动端优先的城市选择样式 */
                .matchmaker-city-grid {
                    padding: 12px;
                    background: #fefefe;
                    border-radius: 16px;
                    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.06);
                    width: 100%;
                    box-sizing: border-box;
                    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
                }
                
                /* 全国选项样式 */
                .matchmaker-nationwide {
                    background: linear-gradient(135deg, #748ffc 0%, #9775fa 100%);
                    color: white;
                    border: none;
                    font-weight: 600;
                    margin-bottom: 18px;
                    padding: 18px 24px;
                    border-radius: 14px;
                    transition: all 0.3s ease;
                    font-size: 17px;
                    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    cursor: pointer;
                    -webkit-tap-highlight-color: transparent;
                    letter-spacing: 0.5px;
                }
                
                .matchmaker-nationwide:hover,
                .matchmaker-nationwide:active {
                    transform: translateY(-2px);
                    box-shadow: 0 6px 20px rgba(116, 143, 252, 0.4);
                }
                
                /* 地区标题样式 */
                .matchmaker-region-header {
                    display: flex;
                    justify-content: space-between;
                    align-items: center;
                    padding: 16px 20px;
                    background: #f7f8fa;
                    border-radius: 12px;
                    cursor: pointer;
                    margin-bottom: 10px;
                    transition: all 0.3s ease;
                    font-size: 16px;
                    font-weight: 600;
                    color: #5a6069;
                    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
                    -webkit-tap-highlight-color: transparent;
                    letter-spacing: 0.3px;
                }
                
                .matchmaker-region-header:hover,
                .matchmaker-region-header:active {
                    background: #f0f2f5;
                    transform: translateY(-1px);
                }
                
                .region-name {
                    font-weight: 600;
                }
                
                .region-toggle {
                    transition: transform 0.3s ease;
                    color: #868e96;
                    font-size: 15px;
                }
                
                .region-toggle.rotated {
                    transform: rotate(180deg);
                }
                
                /* 城市容器样式 */
                .matchmaker-region-cities {
                    padding: 14px;
                    background: white;
                    border-radius: 12px;
                    display: grid;
                    grid-template-columns: repeat(3, 1fr);
                    gap: 12px;
                    transition: all 0.3s ease;
                    margin-bottom: 14px;
                    max-height: 400px;
                    overflow-y: auto;
                }
                
                /* 城市项样式（优化触摸体验） */
                .matchmaker-city-item {
                    padding: 16px 14px;
                    background: #f9fafb;
                    border: 1px solid #f0f2f5;
                    border-radius: 12px;
                    cursor: pointer;
                    text-align: center;
                    font-size: 15px;
                    transition: all 0.25s ease;
                    color: #5a6069;
                    font-weight: 500;
                    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
                    -webkit-tap-highlight-color: transparent;
                    min-height: 54px;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    word-wrap: break-word;
                    letter-spacing: 0.2px;
                    line-height: 1.4;
                }
                
                .matchmaker-city-item:hover,
                .matchmaker-city-item:active {
                    background: #e7f5ff;
                    border-color: #90caf9;
                    color: #1976d2;
                    transform: translateY(-2px);
                    box-shadow: 0 5px 16px rgba(144, 202, 249, 0.3);
                }
                
                /* 城市项选中状态 */
                .matchmaker-city-item.active {
                    background: #bbdefb;
                    border-color: #64b5f6;
                    color: #1565c0;
                    font-weight: 600;
                }
                
                /* 优化滚动条样式 */
                .matchmaker-region-cities::-webkit-scrollbar {
                    width: 6px;
                }
                
                .matchmaker-region-cities::-webkit-scrollbar-track {
                    background: #f1f3f4;
                    border-radius: 3px;
                }
                
                .matchmaker-region-cities::-webkit-scrollbar-thumb {
                    background: #c1c8cd;
                    border-radius: 3px;
                }
                
                .matchmaker-region-cities::-webkit-scrollbar-thumb:hover {
                    background: #a8b2b9;
                }
                
                .matchmaker-city-item.active {
                    background: linear-gradient(135deg, #4CAF50 0%, #45a049 100%);
                    color: white;
                    border-color: #4CAF50;
                    font-weight: 600;
                    box-shadow: 0 4px 12px rgba(76, 175, 80, 0.4);
                }
                
                /* 搜索功能样式 */
                .matchmaker-city-search {
                    position: relative;
                    margin-bottom: 20px;
                }
                
                .matchmaker-city-search-input {
                    width: 100%;
                    padding: 16px 20px 16px 50px;
                    border: 2px solid #e9ecef;
                    border-radius: 28px;
                    font-size: 15px;
                    transition: all 0.3s ease;
                    box-sizing: border-box;
                    background: #f8f9fa;
                    -webkit-appearance: none;
                }
                
                .matchmaker-city-search-input:focus {
                    outline: none;
                    border-color: #667eea;
                    background: white;
                    box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
                }
                
                .matchmaker-search-icon {
                    position: absolute;
                    left: 18px;
                    top: 50%;
                    transform: translateY(-50%);
                    color: #6c757d;
                    font-size: 18px;
                }
                
                /* 移动端优化 */
                @media (max-width: 768px) {
                    .matchmaker-city-grid {
                        padding: 12px;
                        margin: 0 -15px;
                        border-radius: 0;
                    }
                    
                    .matchmaker-region-cities {
                        grid-template-columns: repeat(3, 1fr);
                        gap: 10px;
                        padding: 16px;
                    }
                    
                    .matchmaker-region-cities.collapsed {
                        display: none;
                    }
                    
                    .matchmaker-city-item {
                        padding: 16px 12px;
                        font-size: 14px;
                        min-height: 55px;
                    }
                    
                    .matchmaker-city-search-input {
                        padding: 16px 20px 16px 50px;
                        font-size: 15px;
                    }
                    
                    .matchmaker-region-header {
                        padding: 16px 20px;
                        font-size: 15px;
                    }
                }
                
                /* 超小屏幕优化 */
                @media (max-width: 480px) {
                    .matchmaker-region-cities {
                        grid-template-columns: repeat(2, 1fr);
                        gap: 10px;
                    }
                    
                    .matchmaker-city-item {
                        padding: 14px 8px;
                        font-size: 13px;
                    }
                }
                
                /* 全国选项的图标样式 */
                .matchmaker-nationwide i {
                    margin-right: 10px;
                    font-size: 18px;
                }
                
                .matchmaker-nationwide span {
                    vertical-align: middle;
                }
                    cursor: pointer;
                    transition: all 0.2s ease;
                }
                
                .matchmaker-city-item:hover {
                    background-color: #f0f0f0;
                    border-color: #999;
                }
                
                .matchmaker-city-item.active {
                    background-color: #2196F3;
                    color: white;
                    border-color: #2196F3;
                }
            `;
            document.head.appendChild(cityStyles);
        }
        
        // 根据城市过滤红娘牵线用户
        function filterMatchmakerUsersByCity(city) {
            // 设置选中的城市
            selectedMatchmakerCity = city;
            // 保存到localStorage
            localStorage.setItem('selectedMatchmakerCity', city);
            // 调用displayMatchmakerUserList显示筛选后的用户信息
            displayMatchmakerUserList();
            
            // 更新用户界面，显示已选择的城市
            console.log(`已选择城市: ${city || '全国'}，正在显示该区域的所有用户`);
        }
        
        // 显示聊天记录
        function showChatRecords(province, city) {
            const key = `${province}-${city}`;
            const chatRecords = chatData[key] || [];
            
            // 检查用户是否为VIP
            const isVip = currentUser && currentUser.vip && currentUser.vip.group === true;
            
            // 设置聊天标题
            chatTitle.textContent = `${province}${city} - 群聊记录`;
            
            // 清空聊天内容
            chatContent.innerHTML = '';
            
            if (chatRecords.length === 0) {
                // 没有聊天记录
                const noData = document.createElement('div');
                noData.className = 'no-chat-data';
                noData.innerHTML = `
                    <i class="fas fa-comment-slash"></i>
                    <p>暂无群聊记录</p>
                    <p style="font-size: 0.9rem; margin-top: 10px;">支付后即可查看当地群聊记录</p>
                `;
                chatContent.appendChild(noData);
            } else {
                // 创建折叠面板
                const collapseContainer = document.createElement('div');
                collapseContainer.className = 'chat-collapse';
                
                chatRecords.forEach(record => {
                    const collapseItem = document.createElement('div');
                    collapseItem.className = 'collapse-item';
                    
                    const collapseHeader = document.createElement('div');
                    collapseHeader.className = 'collapse-header';
                    collapseHeader.innerHTML = `
                        <h3><i class="fas fa-users"></i> ${record.title}</h3>
                        <div class="collapse-arrow">
                            <i class="fas fa-chevron-down"></i>
                        </div>
                    `;
                    
                    const collapseContent = document.createElement('div');
                    collapseContent.className = 'collapse-content';
                    
                    const chatMessages = document.createElement('div');
                    chatMessages.className = 'chat-messages';
                    
                    if (isVip) {
                        // VIP用户显示完整消息
                        record.messages.forEach(message => {
                            const messageDiv = document.createElement('div');
                            messageDiv.className = `chat-message ${message.self ? 'self' : ''}`;
                            messageDiv.innerHTML = `
                                <div class="chat-avatar">
                                    <i class="fas fa-user"></i>
                                </div>
                                <div class="message-content">
                                    <div class="message-sender">${message.sender}</div>
                                    <div class="message-text">${message.content}</div>
                                    <div class="message-time">${message.time}</div>
                                </div>
                            `;
                            chatMessages.appendChild(messageDiv);
                        });
                    } else {
                        // 非VIP用户只显示消息预览和VIP提示
                        const previewMessage = record.messages[0];
                        const messageDiv = document.createElement('div');
                        messageDiv.className = `chat-message ${previewMessage.self ? 'self' : ''}`;
                        messageDiv.innerHTML = `
                            <div class="chat-avatar">
                                <i class="fas fa-user"></i>
                            </div>
                            <div class="message-content">
                                <div class="message-sender">${previewMessage.sender}</div>
                                <div class="message-text">${previewMessage.content.substring(0, 50)}... <span style="color: #ff6b6b; font-weight: bold;">[查看完整内容需开通VIP]</span></div>
                                <div class="message-time">${previewMessage.time}</div>
                            </div>
                        `;
                        chatMessages.appendChild(messageDiv);
                        
                        // 添加VIP提示
                        const vipNotice = document.createElement('div');
                        vipNotice.className = 'vip-notice';
                        vipNotice.style.cssText = `
                            background: linear-gradient(135deg, #ff6b6b, #ffa07a);
                            color: white;
                            padding: 12px;
                            margin: 10px 0;
                            border-radius: 8px;
                            text-align: center;
                            font-size: 0.9rem;
                        `;
                        vipNotice.innerHTML = `
                            <i class="fas fa-crown"></i> 开通VIP即可查看完整群聊记录
                            <button onclick="openPaymentModal('group')" style="
                                background: white;
                                color: #ff6b6b;
                                border: none;
                                padding: 6px 12px;
                                border-radius: 4px;
                                margin-left: 10px;
                                cursor: pointer;
                                font-weight: bold;
                            ">立即开通</button>
                        `;
                        chatMessages.appendChild(vipNotice);
                    }
                    
                    collapseContent.appendChild(chatMessages);
                    collapseItem.appendChild(collapseHeader);
                    collapseItem.appendChild(collapseContent);
                    collapseContainer.appendChild(collapseItem);
                    
                    // 添加折叠功能
                    collapseHeader.addEventListener('click', () => {
                        collapseHeader.classList.toggle('active');
                        collapseContent.classList.toggle('active');
                        
                        if (collapseContent.classList.contains('active')) {
                            collapseContent.style.maxHeight = collapseContent.scrollHeight + 'px';
                        } else {
                            collapseContent.style.maxHeight = null;
                        }
                    });
                });
                
                chatContent.appendChild(collapseContainer);
            }
            
            // 显示聊天区域
            switchSection('chatSection');
        }
        
        // 已删除用户详情预览功能
        
        // 记录联系请求
        function recordContactRequest(user) {
            // 创建联系请求记录
            const contactRequest = {
                id: Date.now(),
                userId: currentUser ? currentUser.id : 'anonymous',
                userName: currentUser ? currentUser.username : '匿名用户',
                targetUserId: user.id,
                targetUserName: user.name,
                time: new Date().toLocaleString(),
                status: 'pending'
            };
            
            // 保存到本地存储（实际应用中应发送到服务器）
            let contactRequests = JSON.parse(localStorage.getItem('contactRequests')) || [];
            contactRequests.push(contactRequest);
            localStorage.setItem('contactRequests', JSON.stringify(contactRequests));
            
            // 这里可以添加发送到系统的逻辑
            console.log('联系请求已记录:', contactRequest);
        }
        
        // 初始化订单列表
        function initOrderList() {
            orderList.innerHTML = '';
            
            if (orders.length === 0) {
                orderList.innerHTML = '<p style="text-align: center; padding: 20px; color: #999;">暂无订单</p>';
                return;
            }
            
            orders.forEach((order, index) => {
                const orderItem = document.createElement('div');
                orderItem.className = 'order-item';
                
                const orderInfo = document.createElement('div');
                orderInfo.className = 'order-info';
                
                const orderTitle = document.createElement('h3');
                orderTitle.textContent = `${order.province} - ${order.city} 交友群`;
                
                const orderTime = document.createElement('p');
                orderTime.textContent = `订单时间: ${order.time}`;
                
                orderInfo.appendChild(orderTitle);
                orderInfo.appendChild(orderTime);
                
                const orderActions = document.createElement('div');
                orderActions.className = 'order-actions';
                
                const orderStatus = document.createElement('span');
                orderStatus.className = `order-status ${order.status === 'paid' ? 'status-paid' : 'status-refunded'}`;
                orderStatus.textContent = order.status === 'paid' ? '已支付' : '已退款';
                
                orderActions.appendChild(orderStatus);
                
                // 只有已支付的订单可以退款
                if (order.status === 'paid') {
                    const refundBtn = document.createElement('button');
                    refundBtn.className = 'refund-btn';
                    refundBtn.textContent = '申请退款';
                    refundBtn.addEventListener('click', () => {
                        refundOrder(index);
                    });
                    orderActions.appendChild(refundBtn);
                }
                
                orderItem.appendChild(orderInfo);
                orderItem.appendChild(orderActions);
                orderList.appendChild(orderItem);
            });
        }
        
        // 初始化彩虹易支付SDK
        // EpayCore类定义
        class EpayCore {
            constructor(config) {
                this.pid = config.pid;
                this.key = config.key;
                this.submitUrl = config.apiUrl + 'submit.php';
                this.mapiUrl = config.apiUrl + 'mapi.php';
                this.apiUrl = config.apiUrl + 'api.php';
                this.signType = 'MD5';
                
                // 调试信息
                console.log('EpayCore配置:', {
                    pid: this.pid,
                    key: this.key,
                    submitUrl: this.submitUrl,
                    mapiUrl: this.mapiUrl,
                    apiUrl: this.apiUrl
                });
            }

            // 发起支付（页面跳转）
            pagePay(param, button = '正在跳转') {
                const params = this.buildRequestParam(param);
                
                let html = '<form id="dopay" action="' + this.submitUrl + '" method="post">';
                for (const key in params) {
                    if (params.hasOwnProperty(key)) {
                        html += '<input type="hidden" name="' + key + '" value="' + params[key] + '"/>';
                    }
                }
                html += '<input type="submit" value="' + button + '"><\/form><script>document.getElementById("dopay").submit();<\/script>';
                
                return html;
            }

            // 发起支付（获取链接）
            getPayLink(param) {
                const params = this.buildRequestParam(param);
                // 使用传统的URL参数构建方式，与PHP后端保持一致
                const queryString = Object.keys(params)
                    .map(key => encodeURIComponent(key) + '=' + encodeURIComponent(params[key]))
                    .join('&');
                const url = this.submitUrl + '?' + queryString;
                return url;
            }

            // 发起支付（页面跳转）
            submitPayment(param) {
                // 创建隐藏的form表单进行支付跳转，确保支付平台正确识别支付方式
                const params = this.buildRequestParam(param);
                const form = document.createElement('form');
                form.method = 'POST';
                form.action = this.submitUrl;
                form.style.display = 'none';
                
                // 添加所有参数到表单
                for (const key in params) {
                    if (params.hasOwnProperty(key)) {
                        const input = document.createElement('input');
                        input.type = 'hidden';
                        input.name = key;
                        input.value = params[key];
                        form.appendChild(input);
                    }
                }
                
                // 将表单添加到页面并自动提交
                document.body.appendChild(form);
                form.submit();
            }

            // 异步回调验证
            verifyNotify(getParams) {
                if (!getParams || Object.keys(getParams).length === 0) return false;
                
                const sign = this.getSign(getParams);
                return sign === getParams.sign;
            }

            // 同步回调验证
            verifyReturn(getParams) {
                if (!getParams || Object.keys(getParams).length === 0) return false;
                
                const sign = this.getSign(getParams);
                return sign === getParams.sign;
            }

            // 查询订单支付状态
            async orderStatus(tradeNo) {
                const result = await this.queryOrder(tradeNo);
                return result.status === 1;
            }

            // 查询订单
            async queryOrder(tradeNo) {
                const url = this.apiUrl + '?act=order&pid=' + this.pid + '&key=' + this.key + '&trade_no=' + tradeNo;
                const response = await this.getHttpResponse(url);
                return JSON.parse(response);
            }

            // 订单退款
            async refund(tradeNo, money) {
                const url = this.apiUrl + '?act=refund';
                const postData = 'pid=' + this.pid + '&key=' + this.key + '&trade_no=' + tradeNo + '&money=' + money;
                const response = await this.getHttpResponse(url, postData);
                return JSON.parse(response);
            }

            // 私有方法
            buildRequestParam(param) {
                // 确保pid参数被添加到支付请求中
                if (!param.pid) {
                    param.pid = this.pid;
                }
                const mysign = this.getSign(param);
                param.sign = mysign;
                param.sign_type = this.signType;
                return param;
            }

            // 计算签名
            getSign(param) {
                const sortedParams = Object.keys(param)
                    .sort()
                    .reduce((result, key) => {
                        if (key !== "sign" && key !== "sign_type" && param[key] !== '') {
                            result[key] = param[key];
                        }
                        return result;
                    }, {});
                
                let signStr = '';
                for (const key in sortedParams) {
                    signStr += key + '=' + sortedParams[key] + '&';
                }
                signStr = signStr.slice(0, -1); // 去掉最后一个&
                signStr += this.key;
                
                // 确保在MD5之前进行UTF-8编码
                signStr = this.Utf8Encode(signStr);
                
                return this.md5(signStr);
            }

            // MD5加密函数
            md5(string) {
                function rotateLeft(lValue, iShiftBits) {
                    return (lValue << iShiftBits) | (lValue >>> (32 - iShiftBits));
                }

                function addUnsigned(lX, lY) {
                    let lX4, lY4, lX8, lY8, lResult;
                    lX8 = (lX & 0x80000000);
                    lY8 = (lY & 0x80000000);
                    lX4 = (lX & 0x40000000);
                    lY4 = (lY & 0x40000000);
                    lResult = (lX & 0x3FFFFFFF) + (lY & 0x3FFFFFFF);
                    if (lX4 & lY4) {
                        return (lResult ^ 0x80000000 ^ lX8 ^ lY8);
                    }
                    if (lX4 | lY4) {
                        if (lResult & 0x40000000) {
                            return (lResult ^ 0xC0000000 ^ lX8 ^ lY8);
                        } else {
                            return (lResult ^ 0x40000000 ^ lX8 ^ lY8);
                        }
                    } else {
                        return (lResult ^ lX8 ^ lY8);
                    }
                }

                function F(x, y, z) { return (x & y) | ((~x) & z); }
                function G(x, y, z) { return (x & z) | (y & (~z)); }
                function H(x, y, z) { return (x ^ y ^ z); }
                function I(x, y, z) { return (y ^ (x | (~z))); }

                function FF(a, b, c, d, x, s, ac) {
                    a = addUnsigned(a, addUnsigned(addUnsigned(F(b, c, d), x), ac));
                    return addUnsigned(rotateLeft(a, s), b);
                }

                function GG(a, b, c, d, x, s, ac) {
                    a = addUnsigned(a, addUnsigned(addUnsigned(G(b, c, d), x), ac));
                    return addUnsigned(rotateLeft(a, s), b);
                }

                function HH(a, b, c, d, x, s, ac) {
                    a = addUnsigned(a, addUnsigned(addUnsigned(H(b, c, d), x), ac));
                    return addUnsigned(rotateLeft(a, s), b);
                }

                function II(a, b, c, d, x, s, ac) {
                    a = addUnsigned(a, addUnsigned(addUnsigned(I(b, c, d), x), ac));
                    return addUnsigned(rotateLeft(a, s), b);
                }

                function convertToWordArray(string) {
                    let lWordCount;
                    const lMessageLength = string.length;
                    const lNumberOfWordsTemp1 = lMessageLength + 8;
                    const lNumberOfWordsTemp2 = (lNumberOfWordsTemp1 - (lNumberOfWordsTemp1 % 64)) / 64;
                    const lNumberOfWords = (lNumberOfWordsTemp2 + 1) * 16;
                    const lWordArray = Array(lNumberOfWords - 1);
                    let lBytePosition = 0;
                    let lByteCount = 0;
                    while (lByteCount < lMessageLength) {
                        lWordCount = (lByteCount - (lByteCount % 4)) / 4;
                        lBytePosition = (lByteCount % 4) * 8;
                        lWordArray[lWordCount] = (lWordArray[lWordCount] | (string.charCodeAt(lByteCount) << lBytePosition));
                        lByteCount++;
                    }
                    lWordCount = (lByteCount - (lByteCount % 4)) / 4;
                    lBytePosition = (lByteCount % 4) * 8;
                    lWordArray[lWordCount] = lWordArray[lWordCount] | (0x80 << lBytePosition);
                    lWordArray[lNumberOfWords - 2] = lMessageLength << 3;
                    lWordArray[lNumberOfWords - 1] = lMessageLength >>> 29;
                    return lWordArray;
                }

                function wordToHex(lValue) {
                    let WordToHexValue = "", WordToHexValueTemp = "", lByte, lCount;
                    for (lCount = 0; lCount <= 3; lCount++) {
                        lByte = (lValue >>> (lCount * 8)) & 255;
                        WordToHexValueTemp = "0" + lByte.toString(16);
                        WordToHexValue = WordToHexValue + WordToHexValueTemp.substr(WordToHexValueTemp.length - 2, 2);
                    }
                    return WordToHexValue;
                }

                let x = [];
                let k, AA, BB, CC, DD, a, b, c, d;
                const S11 = 7, S12 = 12, S13 = 17, S14 = 22;
                const S21 = 5, S22 = 9, S23 = 14, S24 = 20;
                const S31 = 4, S32 = 11, S33 = 16, S34 = 23;
                const S41 = 6, S42 = 10, S43 = 15, S44 = 21;

                // UTF-8编码函数
                function Utf8Encode(string) {
                    string = string.replace(/\r\n/g, "\n");
                    let utftext = "";
                    
                    for (let n = 0; n < string.length; n++) {
                        const c = string.charCodeAt(n);
                        
                        if (c < 128) {
                            utftext += String.fromCharCode(c);
                        } else if ((c > 127) && (c < 2048)) {
                            utftext += String.fromCharCode((c >> 6) | 192);
                            utftext += String.fromCharCode((c & 63) | 128);
                        } else {
                            utftext += String.fromCharCode((c >> 12) | 224);
                            utftext += String.fromCharCode(((c >> 6) & 63) | 128);
                            utftext += String.fromCharCode((c & 63) | 128);
                        }
                    }
                    
                    return utftext;
                }
                
                x = convertToWordArray(string);

                a = 0x67452301; b = 0xEFCDAB89; c = 0x98BADCFE; d = 0x10325476;

                for (k = 0; k < x.length; k += 16) {
                    AA = a; BB = b; CC = c; DD = d;
                    a = FF(a, b, c, d, x[k + 0], S11, 0xD76AA478);
                    d = FF(d, a, b, c, x[k + 1], S12, 0xE8C7B756);
                    c = FF(c, d, a, b, x[k + 2], S13, 0x242070DB);
                    b = FF(b, c, d, a, x[k + 3], S14, 0xC1BDCEEE);
                    a = FF(a, b, c, d, x[k + 4], S11, 0xF57C0FAF);
                    d = FF(d, a, b, c, x[k + 5], S12, 0x4787C62A);
                    c = FF(c, d, a, b, x[k + 6], S13, 0xA8304613);
                    b = FF(b, c, d, a, x[k + 7], S14, 0xFD469501);
                    a = FF(a, b, c, d, x[k + 8], S11, 0x698098D8);
                    d = FF(d, a, b, c, x[k + 9], S12, 0x8B44F7AF);
                    c = FF(c, d, a, b, x[k + 10], S13, 0xFFFF5BB1);
                    b = FF(b, c, d, a, x[k + 11], S14, 0x895CD7BE);
                    a = FF(a, b, c, d, x[k + 12], S11, 0x6B901122);
                    d = FF(d, a, b, c, x[k + 13], S12, 0xFD987193);
                    c = FF(c, d, a, b, x[k + 14], S13, 0xA679438E);
                    b = FF(b, c, d, a, x[k + 15], S14, 0x49B40821);
                    a = GG(a, b, c, d, x[k + 1], S21, 0xF61E2562);
                    d = GG(d, a, b, c, x[k + 6], S22, 0xC040B340);
                    c = GG(c, d, a, b, x[k + 11], S23, 0x265E5A51);
                    b = GG(b, c, d, a, x[k + 0], S24, 0xE9B6C7AA);
                    a = GG(a, b, c, d, x[k + 5], S21, 0xD62F105D);
                    d = GG(d, a, b, c, x[k + 10], S22, 0x2441453);
                    c = GG(c, d, a, b, x[k + 15], S23, 0xD8A1E681);
                    b = GG(b, c, d, a, x[k + 4], S24, 0xE7D3FBC8);
                    a = GG(a, b, c, d, x[k + 9], S21, 0x21E1CDE6);
                    d = GG(d, a, b, c, x[k + 14], S22, 0xC33707D6);
                    c = GG(c, d, a, b, x[k + 3], S23, 0xF4D50D87);
                    b = GG(b, c, d, a, x[k + 8], S24, 0x455A14ED);
                    a = GG(a, b, c, d, x[k + 13], S21, 0xA9E3E905);
                    d = GG(d, a, b, c, x[k + 2], S22, 0xFCEFA3F8);
                    c = GG(c, d, a, b, x[k + 7], S23, 0x676F02D9);
                    b = GG(b, c, d, a, x[k + 12], S24, 0x8D2A4C8A);
                    a = HH(a, b, c, d, x[k + 5], S31, 0xFFFA3942);
                    d = HH(d, a, b, c, x[k + 8], S32, 0x8771F681);
                    c = HH(c, d, a, b, x[k + 11], S33, 0x6D9D6122);
                    b = HH(b, c, d, a, x[k + 14], S34, 0xFDE5380C);
                    a = HH(a, b, c, d, x[k + 1], S31, 0xA4BEEA44);
                    d = HH(d, a, b, c, x[k + 4], S32, 0x4BDECFA9);
                    c = HH(c, d, a, b, x[k + 7], S33, 0xF6BB4B60);
                    b = HH(b, c, d, a, x[k + 10], S34, 0xBEBFBC70);
                    a = HH(a, b, c, d, x[k + 13], S31, 0x289B7EC6);
                    d = HH(d, a, b, c, x[k + 0], S32, 0xEAA127FA);
                    c = HH(c, d, a, b, x[k + 3], S33, 0xD4EF3085);
                    b = HH(b, c, d, a, x[k + 6], S34, 0x4881D05);
                    a = HH(a, b, c, d, x[k + 9], S31, 0xD9D4D039);
                    d = HH(d, a, b, c, x[k + 12], S32, 0xE6DB99E5);
                    c = HH(c, d, a, b, x[k + 15], S33, 0x1FA27CF8);
                    b = HH(b, c, d, a, x[k + 2], S34, 0xC4AC5665);
                    a = II(a, b, c, d, x[k + 0], S41, 0xF4292244);
                    d = II(d, a, b, c, x[k + 7], S42, 0x432AFF97);
                    c = II(c, d, a, b, x[k + 14], S43, 0xAB9423A7);
                    b = II(b, c, d, a, x[k + 5], S44, 0xFC93A039);
                    a = II(a, b, c, d, x[k + 12], S41, 0x655B59C3);
                    d = II(d, a, b, c, x[k + 3], S42, 0x8F0CCC92);
                    c = II(c, d, a, b, x[k + 10], S43, 0xFFEFF47D);
                    b = II(b, c, d, a, x[k + 1], S44, 0x85845DD1);
                    a = II(a, b, c, d, x[k + 8], S41, 0x6FA87E4F);
                    d = II(d, a, b, c, x[k + 15], S42, 0xFE2CE6E0);
                    c = II(c, d, a, b, x[k + 6], S43, 0xA3014314);
                    b = II(b, c, d, a, x[k + 13], S44, 0x4E0811A1);
                    a = II(a, b, c, d, x[k + 4], S41, 0xF7537E82);
                    d = II(d, a, b, c, x[k + 11], S42, 0xBD3AF235);
                    c = II(c, d, a, b, x[k + 2], S43, 0x2AD7D2BB);
                    b = II(b, c, d, a, x[k + 9], S44, 0xEB86D391);
                    a = addUnsigned(a, AA);
                    b = addUnsigned(b, BB);
                    c = addUnsigned(c, CC);
                    d = addUnsigned(d, DD);
                }
                const temp = wordToHex(a) + wordToHex(b) + wordToHex(c) + wordToHex(d);
                return temp.toLowerCase();
            }

            // UTF-8编码
            Utf8Encode(string) {
                string = string.replace(/\r\n/g, "\n");
                let utftext = "";
                for (let n = 0; n < string.length; n++) {
                    const c = string.charCodeAt(n);
                    if (c < 128) {
                        utftext += String.fromCharCode(c);
                    } else if ((c > 127) && (c < 2048)) {
                        utftext += String.fromCharCode((c >> 6) | 192);
                        utftext += String.fromCharCode((c & 63) | 128);
                    } else {
                        utftext += String.fromCharCode((c >> 12) | 224);
                        utftext += String.fromCharCode(((c >> 6) & 63) | 128);
                        utftext += String.fromCharCode((c & 63) | 128);
                    }
                }
                return utftext;
            }

            // HTTP请求 - 优化版本：支持重试和超时
            async getHttpResponse(url, postData = false, timeout = 10000, retryCount = 2) {
                let attempt = 0;
                
                while (attempt <= retryCount) {
                    try {
                        const controller = new AbortController();
                        const timeoutId = setTimeout(() => controller.abort(), timeout);
                        
                        const options = {
                            method: postData ? 'POST' : 'GET',
                            headers: {
                                'Accept': '*/*',
                                'Accept-Language': 'zh-CN,zh;q=0.8',
                                'Connection': 'close'
                            },
                            signal: controller.signal
                        };
                        
                        if (postData) {
                            options.headers['Content-Type'] = 'application/x-www-form-urlencoded';
                            options.body = postData;
                        }
                        
                        const response = await fetch(url, options);
                        clearTimeout(timeoutId);
                        
                        if (!response.ok) {
                            throw new Error(`HTTP error! status: ${response.status}`);
                        }
                        
                        return await response.text();
                    } catch (error) {
                        console.error(`HTTP请求尝试 ${attempt + 1} 失败:`, error);
                        attempt++;
                        
                        // 如果还有重试机会，等待一段时间后重试（指数退避）
                        if (attempt <= retryCount) {
                            const delay = 1000 * Math.pow(2, attempt - 1);
                            console.log(`等待 ${delay}ms 后重试...`);
                            await new Promise(resolve => setTimeout(resolve, delay));
                        } else {
                            // 所有尝试都失败了
                            console.error('HTTP请求所有尝试都失败了');
                            throw error;
                        }
                    }
                }
            }
        }

        // 创建支付核心实例（统一使用一个实例）
        const epayCore = new EpayCore(PAYMENT_CONFIG);
        
        // 为EpayCore类添加重试机制和备用地址支持
        EpayCore.prototype.submitPaymentWithRetry = async function(param, retryCount = 2) {
            let attempt = 0;
            const paymentUrls = [
                this.submitUrl, // 默认地址
                'https://2a.mazhifupay.com/submit.php' // 备用地址
            ];
            
            while (attempt <= retryCount) {
                try {
                    // 尝试使用不同的支付地址
                    const currentUrl = paymentUrls[attempt % paymentUrls.length];
                    
                    // 创建隐藏的form表单进行支付跳转，确保支付平台正确识别支付方式
                    const params = this.buildRequestParam(param);
                    const form = document.createElement('form');
                    form.method = 'POST';
                    form.action = currentUrl;
                    form.style.display = 'none';
                    
                    // 添加所有参数到表单
                    for (const key in params) {
                        if (params.hasOwnProperty(key)) {
                            const input = document.createElement('input');
                            input.type = 'hidden';
                            input.name = key;
                            input.value = params[key];
                            form.appendChild(input);
                        }
                    }
                    
                    // 将表单添加到页面并自动提交
                    document.body.appendChild(form);
                    form.submit();
                    
                    // 提交成功后退出循环
                    break;
                } catch (error) {
                    console.error(`支付尝试 ${attempt + 1} 失败:`, error);
                    attempt++;
                    
                    // 如果还有重试机会，等待一段时间后重试
                    if (attempt <= retryCount) {
                        await new Promise(resolve => setTimeout(resolve, 1000 * attempt));
                    } else {
                        // 所有尝试都失败了，显示错误信息
                        alert('支付失败，请稍后重试或联系客服。');
                        throw error;
                    }
                }
            }
        };
        
        // 重写redirectToPayment函数，使用带重试机制的支付提交方法
        // 如果 redirectToPayment 已存在，先保存原始引用（避免重复声明）
        const originalRedirectToPayment = typeof redirectToPayment !== 'undefined' ? redirectToPayment : undefined;
        redirectToPayment = function() {
            if (redirectPaymentParams) {
                // 隐藏支付过渡页面
                document.getElementById('paymentRedirectModal').classList.add('hidden');
                
                // 使用带重试机制的支付提交方法
                epayCore.submitPaymentWithRetry(redirectPaymentParams)
                    .catch(error => {
                        console.error('支付重定向失败:', error);
                        // 显示支付失败页面
                        showPaymentFailed(redirectPaymentParams.out_trade_no, redirectPaymentParams.money, '支付请求发送失败，请检查网络连接');
                    });
                
                // 清空保存的支付参数
                redirectPaymentParams = null;
            }
        };
        
        let redirectTimer = null;
        let redirectPaymentParams = null;
        
        // 显示支付过渡页面
        function showPaymentRedirect(orderNo, paymentParams) {
            // 保存支付参数以便稍后使用
            redirectPaymentParams = paymentParams;
            
            // 更新订单号
            document.getElementById('redirectOrderNumber').textContent = orderNo;
            
            // 重置倒计时
            const countdownEl = document.getElementById('redirectCountdown');
            const progressEl = document.getElementById('redirectProgress');
            let seconds = 3;
            countdownEl.textContent = seconds;
            progressEl.style.width = '100%';
            
            // 显示过渡页面
            document.getElementById('paymentRedirectModal').classList.remove('hidden');
            
            // 清除之前的定时器
            if (redirectTimer) {
                clearInterval(redirectTimer);
            }
            
            // 开始倒计时
            redirectTimer = setInterval(() => {
                seconds--;
                countdownEl.textContent = seconds;
                
                // 更新进度条
                const progressPercentage = (seconds / 3) * 100;
                progressEl.style.width = progressPercentage + '%';
                
                // 倒计时结束，自动跳转到支付
                if (seconds <= 0) {
                    clearInterval(redirectTimer);
                    redirectToPayment();
                }
            }, 1000);
        }
        
        // 跳转到支付页面
        function redirectToPayment() {
            if (redirectPaymentParams) {
                // 隐藏过渡页面
                document.getElementById('paymentRedirectModal').classList.add('hidden');
                
                // 使用SDK的支付跳转方法
                console.log('自动跳转到支付页面...');
                epayCore.submitPayment(redirectPaymentParams);
                
                // 清除支付参数
                redirectPaymentParams = null;
            }
        }
        
        // 取消支付
        function cancelPayment() {
            // 清除定时器
            if (redirectTimer) {
                clearInterval(redirectTimer);
                redirectTimer = null;
            }
            
            // 隐藏过渡页面
            document.getElementById('paymentRedirectModal').classList.add('hidden');
            
            // 提示支付失败并建议重新支付
            alert('支付失败，请重新支付');
            
            // 清除支付参数
            redirectPaymentParams = null;
        }
        
        // 绑定支付过渡页面按钮事件
        document.addEventListener('DOMContentLoaded', function() {
            // 继续支付按钮
            document.getElementById('continuePaymentBtn').addEventListener('click', function() {
                if (redirectTimer) {
                    clearInterval(redirectTimer);
                }
                redirectToPayment();
            });
            
            // 返回按钮
            document.getElementById('cancelPaymentBtn').addEventListener('click', cancelPayment);
        });
        
        // 提交支付请求（使用彩虹易支付SDK）
        function submitPayment() {
            // 检查是否已选择城市
            if (!selectedProvince || !selectedCity) {
                // 显示更友好的提示，并自动滚动到城市选择区域
                alert('请先选择您所在的城市，然后才能进行支付');
                
                // 自动滚动到城市选择区域
                const citySection = document.querySelector('.city-section');
                if (citySection) {
                    citySection.scrollIntoView({ behavior: 'smooth' });
                }
                
                // 高亮显示城市选择区域
                const provinceList = document.getElementById('provinceList');
                if (provinceList) {
                    provinceList.style.border = '2px solid #ff6b6b';
                    provinceList.style.boxShadow = '0 0 10px rgba(255, 107, 107, 0.5)';
                    
                    // 3秒后移除高亮效果
                    setTimeout(() => {
                        provinceList.style.border = '';
                        provinceList.style.boxShadow = '';
                    }, 3000);
                }
                
                return;
            }
            
            // 检查是否同意声明
            const agreementCheckbox = document.getElementById('paymentAgreementCheckbox');
            const agreementError = document.getElementById('paymentAgreementError');
            
            if (!agreementCheckbox.checked) {
                // 显示错误提示
                agreementError.classList.remove('hidden');
                
                // 高亮显示声明区域
                const agreementSection = document.querySelector('.agreement-section');
                if (agreementSection) {
                    agreementSection.scrollIntoView({ behavior: 'smooth' });
                    
                    // 添加高亮效果
                    agreementSection.style.border = '2px solid #ff6b6b';
                    agreementSection.style.boxShadow = '0 0 10px rgba(255, 107, 107, 0.5)';
                    
                    // 3秒后移除高亮效果
                    setTimeout(() => {
                        agreementSection.style.border = '';
                        agreementSection.style.boxShadow = '';
                    }, 3000);
                }
                
                return;
            } else {
                // 隐藏错误提示（如果之前显示的话）
                agreementError.classList.add('hidden');
            }
            
            console.log('开始生成支付请求...');
            
            // 构建支付参数 - 根据用户选择的支付方式
            const paymentParams = {
                type: selectedPaymentMethod === 'alipay' ? 'alipay' : 'wxpay', // 根据选择切换支付方式
                notify_url: PAYMENT_CONFIG.notify_url,
                return_url: PAYMENT_CONFIG.return_url,
                out_trade_no: 'WXGROUP' + Date.now(),
                name: '微信群聊VIP服务',
                money: parseFloat(PAYMENT_CONFIG.amount).toFixed(2) // 确保金额为两位小数格式
            };
            
            console.log('支付参数生成成功:', paymentParams);
            console.log('选择的支付方式:', selectedPaymentMethod);
            
            // 显示支付过渡页面，而不是直接跳转
            console.log('显示支付过渡页面...');
            showPaymentRedirect(paymentParams.out_trade_no, paymentParams);
        }
        
        // 提交红娘牵线支付请求（使用彩虹易支付SDK）
        function submitMatchmakerPayment() {
            // 检查用户是否已登录
            if (!currentUser) {
                alert('请先登录才能开通红娘牵线VIP服务');
                switchSection('profileSection');
                return;
            }
            
            // 检查是否同意声明
            const agreementCheckbox = document.getElementById('matchmakerPaymentAgreementCheckbox');
            const agreementError = document.getElementById('matchmakerPaymentAgreementError');
            
            if (!agreementCheckbox.checked) {
                // 显示错误提示
                agreementError.classList.remove('hidden');
                
                // 高亮显示声明区域
                const agreementSection = document.querySelector('.agreement-section');
                if (agreementSection) {
                    agreementSection.scrollIntoView({ behavior: 'smooth' });
                    
                    // 添加高亮效果
                    agreementSection.style.border = '2px solid #ff6b6b';
                    agreementSection.style.boxShadow = '0 0 10px rgba(255, 107, 107, 0.5)';
                    
                    // 3秒后移除高亮效果
                    setTimeout(() => {
                        agreementSection.style.border = '';
                        agreementSection.style.boxShadow = '';
                    }, 3000);
                }
                
                return;
            } else {
                // 隐藏错误提示（如果之前显示的话）
                agreementError.classList.add('hidden');
            }
            
            // 构建红娘牵线支付参数 - 使用MATCHMAKER_PAYMENT_CONFIG中的配置
            const paymentParams = {
                type: selectedMatchmakerPaymentMethod === 'alipay' ? 'alipay' : 'wxpay', // 根据选择切换支付方式
                notify_url: MATCHMAKER_PAYMENT_CONFIG.notify_url,
                return_url: MATCHMAKER_PAYMENT_CONFIG.return_url,
                out_trade_no: 'MATCHMAKER' + Date.now(),
                name: '红娘牵线VIP服务',
                money: parseFloat(MATCHMAKER_PAYMENT_CONFIG.amount).toFixed(2) // 确保金额为两位小数格式
            };
            
            console.log('红娘牵线支付参数生成成功:', paymentParams);
            console.log('选择的支付方式:', selectedMatchmakerPaymentMethod);
            
            // 显示支付过渡页面，而不是直接跳转
            console.log('显示支付过渡页面...');
            showPaymentRedirect(paymentParams.out_trade_no, paymentParams);
        }
        
        // 退款功能
        function refundOrder(orderIndex) {
            if (confirm('确定要申请退款吗？退款将在1-3个工作日内处理。')) {
                orders[orderIndex].status = 'refunded';
                localStorage.setItem('wx_group_orders', JSON.stringify(orders));
                initOrderList();
                alert('退款申请已提交，请等待处理');
            }
        }
        
        // 检查URL参数，处理支付结果（使用彩虹易支付SDK验证）
        function checkPaymentResult() {
            const urlParams = new URLSearchParams(window.location.search);
            const status = urlParams.get('status');
            const tradeNo = urlParams.get('out_trade_no');
            const payStatus = urlParams.get('pay_status');
            const tradeStatus = urlParams.get('trade_status');
            const totalAmount = urlParams.get('total_amount');
            
            // 只有在有支付参数时才处理支付结果
            if (!status && !tradeNo && !payStatus && !tradeStatus) {
                return;
            }
            
            console.log('检测到支付回调参数:', {
                status, tradeNo, payStatus, tradeStatus, totalAmount
            });
            
            // 支持多种支付结果参数格式
            const isSuccess = status === 'success' || 
                            payStatus === '1' || 
                            tradeStatus === 'TRADE_SUCCESS' ||
                            tradeStatus === 'success';
            
            if (isSuccess && tradeNo) {
                // 支付成功
                hasPaid = true;
                localStorage.setItem('hasPaid', 'true');
                
                // 生成订单
                const orderTime = new Date().toLocaleString();
                const orderAmount = totalAmount ? parseFloat(totalAmount) : 39.99;
                const newOrder = {
                    id: tradeNo,
                    province: selectedProvince,
                    city: selectedCity,
                    amount: orderAmount,
                    time: orderTime,
                    status: 'paid'
                };
                
                orders.unshift(newOrder);
                localStorage.setItem('wx_group_orders', JSON.stringify(orders));
                
                // 更新UI状态
                initUI();
                
                // 显示详细的支付成功页面
                showPaymentSuccess(tradeNo, orderAmount, orderTime, '微信群聊VIP服务');
                
                // 清除URL参数
                window.history.replaceState({}, document.title, window.location.pathname);
                
                console.log('支付成功处理完成，订单号:', tradeNo);
            } else if (status === 'failed' || payStatus === '0' || tradeStatus === 'TRADE_CLOSED') {
                // 支付失败
                const failedOrderNo = tradeNo || '未知订单号';
                const failedAmount = totalAmount ? parseFloat(totalAmount) : 39.99;
                showPaymentFailed(failedOrderNo, failedAmount, '支付超时或网络异常');
                
                // 清除URL参数
                window.history.replaceState({}, document.title, window.location.pathname);
                
                console.log('支付失败处理完成，订单号:', failedOrderNo);
            }
        }
        
        // 显示支付成功页面
        function showPaymentSuccess(orderNumber, amount, time, productName) {
            // 更新支付成功页面信息
            document.getElementById('successOrderNumber').textContent = orderNumber;
            document.getElementById('successAmount').textContent = '¥' + amount.toFixed(2);
            document.getElementById('successTime').textContent = time;
            
            // 显示支付成功模态框
            successModal.classList.remove('hidden');
            
            // 自动跳转到订单页面（5秒后）
            setTimeout(() => {
                successModal.classList.add('hidden');
                switchSection('orderSection');
            }, 5000);
        }
        
        // 显示支付失败页面
        function showPaymentFailed(orderNumber, amount, reason) {
            // 更新支付失败页面信息
            document.getElementById('failedOrderNumber').textContent = orderNumber;
            document.getElementById('failedAmount').textContent = '¥' + amount.toFixed(2);
            document.getElementById('failedReason').textContent = reason;
            
            // 显示支付失败模态框
            failedModal.classList.remove('hidden');
        }
        
        // 检查红娘牵线支付结果（使用彩虹易支付SDK验证）
        function checkMatchmakerPaymentResult() {
            const urlParams = new URLSearchParams(window.location.search);
            const status = urlParams.get('status');
            const tradeNo = urlParams.get('out_trade_no');
            const payStatus = urlParams.get('pay_status');
            const tradeStatus = urlParams.get('trade_status');
            const totalAmount = urlParams.get('total_amount');
            const product = urlParams.get('name');
            
            // 只有在有支付参数时才处理支付结果
            if (!status && !tradeNo && !payStatus && !tradeStatus) {
                return;
            }
            
            console.log('检测到红娘牵线支付回调参数:', {
                status, tradeNo, payStatus, tradeStatus, totalAmount, product
            });
            
            // 支持多种支付结果参数格式
            const isSuccess = status === 'success' || 
                            payStatus === '1' || 
                            tradeStatus === 'TRADE_SUCCESS' ||
                            tradeStatus === 'success';
            
            if (isSuccess && tradeNo) {
                // 红娘牵线VIP支付成功
                hasMatchmakerVip = true;
                localStorage.setItem('hasMatchmakerVip', 'true');
                
                // 更新UI状态
                updateMatchmakerVipUI();
                
                // 显示详细的支付成功页面
                const orderTime = new Date().toLocaleString();
                const orderAmount = totalAmount ? parseFloat(totalAmount) : 99.99;
                showPaymentSuccess(tradeNo, orderAmount, orderTime, '红娘牵线VIP服务');
                
                // 清除URL参数
                window.history.replaceState({}, document.title, window.location.pathname);
                
                console.log('红娘牵线支付成功处理完成，订单号:', tradeNo);
            } else if (status === 'failed' || payStatus === '0' || tradeStatus === 'TRADE_CLOSED') {
                // 支付失败
                const failedOrderNo = tradeNo || '未知订单号';
                const failedAmount = totalAmount ? parseFloat(totalAmount) : 99.99;
                showPaymentFailed(failedOrderNo, failedAmount, '支付超时或网络异常');
                
                // 清除URL参数
                window.history.replaceState({}, document.title, window.location.pathname);
                
                console.log('红娘牵线支付失败处理完成，订单号:', failedOrderNo);
            }
        }
        
        // 生成红娘牵线支付请求URL（使用彩虹易支付SDK）
        function generateMatchmakerPaymentRequest() {
            // 生成订单号
            const outTradeNo = 'MM' + Date.now() + Math.floor(Math.random() * 1000);
            
            // 商品名称
            const productName = '红娘牵线VIP服务';
            
            // 构建支付参数（仅包含彩虹易支付标准参数）
            const params = {
                pid: MATCHMAKER_PAYMENT_CONFIG.pid,
                type: selectedMatchmakerPaymentMethod === 'alipay' ? 'alipay' : 'wxpay',
                out_trade_no: outTradeNo,
                notify_url: MATCHMAKER_PAYMENT_CONFIG.notify_url,
                return_url: MATCHMAKER_PAYMENT_CONFIG.return_url,
                name: productName,
                money: MATCHMAKER_PAYMENT_CONFIG.amount // 使用配置文件中的金额
            };
            
            // 使用红娘牵线专用的EpayCore实例生成支付链接
            return matchmakerEpayCore.getPayLink(params);
        }
        
        // 页面加载完成后自动运行完整的彩虹易支付签名测试
        window.addEventListener('load', function() {
            testRainbowPaySignature();
        });
        
        // 全局UTF-8编码函数已删除，统一使用EpayCore类的Utf8Encode方法

        // 移除了重复的MD5实现，使用类内部定义的md5方法，确保签名生成的一致性
        
        // 添加一个更精确的测试函数，完全模拟彩虹易支付官方签名验证过程
        function testRainbowPaySignature() {
            console.log('=== 开始彩虹易支付官方签名规则测试 ===');
            
            // 实际支付配置
            const config = {
                apiUrl: 'https://2a.mazhifupay.com/',
                pid: '131517535',
                key: '6K1yVk6M16BK72Ms2ZB8wEyM020bZxK2',
                signType: 'MD5'
            };
            
            // 模拟实际支付参数（与真实支付请求完全一致）
            const testParams = {
                pid: config.pid,
                type: 'alipay',
                out_trade_no: 'TEST' + Date.now(),
                notify_url: window.location.protocol + '//' + window.location.host + '/api/notify',
                return_url: window.location.protocol + '//' + window.location.host + '/api/return',
                name: '微信群聊VIP服务',
                money: '39.99' // 彩虹易支付要求金额必须为两位小数
            };
            
            console.log('\n=== 测试参数信息 ===');
            console.log('支付方式:', testParams.type);
            console.log('订单号:', testParams.out_trade_no);
            console.log('商品名称:', testParams.name);
            console.log('金额:', testParams.money);
            console.log('回调URL:', testParams.notify_url);
            console.log('返回URL:', testParams.return_url);
            console.log('商户ID:', testParams.pid);
            
            // 创建EpayCore实例
            const epayCore = new EpayCore(config);
            
            // 生成客户端签名
            const clientSign = epayCore.getSign(testParams);
            
            // 完全按照彩虹易支付官方文档的签名规则实现服务器端验证
            function officialServerSideVerification(params, key) {
                console.log('\n=== 官方服务器端签名验证过程 ===');
                
                // 1. 复制参数，保留原始值，不做任何修改
                const paramCopy = JSON.parse(JSON.stringify(params));
                
                // 2. 移除sign和sign_type参数
                delete paramCopy.sign;
                delete paramCopy.sign_type;
                
                // 3. 按照参数名的ASCII码从小到大排序
                const sortedKeys = Object.keys(paramCopy).sort(function(a, b) {
                    // 严格按照ASCII码顺序排序
                    for (let i = 0; i < Math.min(a.length, b.length); i++) {
                        if (a.charCodeAt(i) !== b.charCodeAt(i)) {
                            return a.charCodeAt(i) - b.charCodeAt(i);
                        }
                    }
                    return a.length - b.length;
                });
                
                console.log('官方排序后的参数键:', sortedKeys);
                
                // 4. 构建签名字符串
                // 规则：参数名1=参数值1&参数名2=参数值2&...&参数名n=参数值n&key=商户密钥
                // 注意：
                // - 参数值不进行URL编码
                // - 保留原始格式（包括小数点格式）
                // - 不要添加任何额外的空格或转义字符
                const signStr = sortedKeys.map(key => {
                    return key + '=' + paramCopy[key];
                }).join('&') + '&key=' + key;
                
                console.log('\n官方签名字符串:', signStr);
                console.log('官方使用的密钥:', key);
                
                // 5. 使用标准MD5算法计算签名（注意：必须与PHP的md5()函数结果一致）
                // PHP的md5()函数会自动对字符串进行UTF-8编码（如果PHP配置正确）
                // 彩虹易支付要求签名必须是大写
                const serverSign = epayCore.md5(signStr).toUpperCase();
                
                console.log('\n官方服务器端生成的签名:', serverSign);
                
                return serverSign;
            }
            
            // 使用官方规则验证签名
            const serverSign = officialServerSideVerification(testParams, config.key);
            
            // 对比签名结果
            console.log('\n=== 签名对比结果 ===');
            console.log('客户端生成的签名:', clientSign);
            console.log('官方服务器端签名:', serverSign);
            console.log('签名是否一致:', clientSign === serverSign);
            
            // 构建支付链接并检查
            const fullParams = epayCore.buildRequestParam(testParams);
            const paymentUrl = epayCore.getPayLink(testParams);
            
            console.log('\n=== 支付请求详细信息 ===');
            console.log('完整支付参数:', fullParams);
            console.log('生成的支付链接:', paymentUrl);
            
            // 验证支付链接中的签名
            const urlParams = new URLSearchParams(paymentUrl.split('?')[1]);
            const urlSign = urlParams.get('sign');
            console.log('\n=== 支付链接签名验证 ===');
            console.log('URL中的签名:', urlSign);
            console.log('URL签名与客户端签名是否一致:', urlSign === clientSign);
            
            console.log('\n=== 签名测试结束 ===');
            
            return {
                params: testParams,
                clientSign: clientSign,
                serverSign: serverSign,
                signatureMatch: clientSign === serverSign,
                paymentUrl: paymentUrl,
                urlSign: urlSign,
                urlSignMatch: urlSign === clientSign
            };
        }
        
        // 添加一个直接测试URL参数的函数
        function testUrlParamsSignature() {
            console.log('=== 开始URL参数签名测试 ===');
            
            // 从URL中获取参数
            const urlParams = new URLSearchParams(window.location.search);
            const paramsObj = {};
            
            for (const [key, value] of urlParams.entries()) {
                paramsObj[key] = value;
            }
            
            if (Object.keys(paramsObj).length === 0) {
                console.log('URL中没有参数，跳过测试');
                return null;
            }
            
            console.log('URL中的参数:', paramsObj);
            
            // 使用实际配置进行验证
            const epayCore = new EpayCore({
                key: '6K1yVk6M16BK72Ms2ZB8wEyM020bZxK2'
            });
            
            // 验证签名
            const isValid = epayCore.getSign(paramsObj) === paramsObj.sign;
            console.log('签名验证结果:', isValid);
            console.log('=== URL参数签名测试结束 ===');
            
            return {
                params: paramsObj,
                isValid: isValid
            };
        }
        

        

        

        

        

        

        
        // 退款功能

        
        // 导航切换
        function switchSection(targetId) {
            // 切换页面时滚动到顶部，提升用户体验
            window.scrollTo(0, 0);
            // 隐藏所有部分，包括反馈中心的所有子页面
            document.querySelectorAll('.card, #feedbackSection > div[id$="Page"]').forEach(element => {
                element.classList.add('hidden');
            });
            
            // 显示目标部分
            if (targetId === 'main') {
                // 切换到首页时，确保隐藏并清理反馈中心的所有内容
                const feedbackSection = document.getElementById('feedbackSection');
                if (feedbackSection) {
                    feedbackSection.classList.add('hidden');
                    // 重置反馈中心内部可能动态生成的内容
                    const feedbackContent = document.getElementById('feedbackContent');
                    const groupFeedbackList = document.getElementById('groupFeedbackList');
                    const matchmakerFeedbackList = document.getElementById('matchmakerFeedbackList');
                    
                    if (groupFeedbackList) groupFeedbackList.innerHTML = '';
                    if (matchmakerFeedbackList) matchmakerFeedbackList.innerHTML = '';
                }
                
                // 显示首页内容
                document.querySelectorAll('.card:not(#orderSection):not(#profileSection):not(#chatSection):not(#matchmakerSection):not(#userDetailSection):not(#feedbackSection)').forEach(card => {
                    card.classList.remove('hidden');
                });
            } else {
                const targetElement = document.getElementById(targetId);
                if (targetElement) {
                    targetElement.classList.remove('hidden');
                }
                
                // 牵线服务特殊处理：检查用户是否已登录且未查看过通知
                if (targetId === 'matchmakerSection') {
                    const currentUser = JSON.parse(localStorage.getItem('currentUser')) || null;
                    console.log('当前用户状态:', currentUser);
                    console.log('是否已看过通知:', hasUserSeenNotification());
                    
                    // 只有当用户未看过通知时才显示
                    if (!hasUserSeenNotification()) {
                        setTimeout(() => {
                            console.log('触发显示通知');
                            showMatchmakerNotification();
                        }, 300);
                    }
                    
                    // 检查用户登录状态
                    if (!currentUser) {
                        console.log('用户未登录');
                        // 不自动模拟登录，改为提示用户
                        alert('请先登录才能使用牵线服务功能');
                        // 切换到登录页面
                        switchSection('profileSection');
                        return;
                    }
                    
                    // 重新初始化牵线服务
                    setTimeout(() => {
                        initMatchmaker();
                    }, 500);
                }
            }
            
            // 更新导航状态
            navItems.forEach(item => {
                if (item.getAttribute('data-target') === targetId) {
                    item.classList.add('active');
                } else {
                    item.classList.remove('active');
                }
            });
        }
        
        // 检查URL参数，处理支付结果（使用彩虹易支付SDK验证）

        

        
        // 获取未读消息数量
        function getUnreadMessages() {
            if (!currentUser) return 0;
            
            // 从localStorage获取消息数据
            const messages = JSON.parse(localStorage.getItem('customerMessages') || '[]');
            
            // 过滤当前用户的未读消息
            const unreadMessages = messages.filter(msg => 
                msg.userId === currentUser.id && !msg.read
            );
            
            return unreadMessages.length;
        }
        
        // 显示消息通知
        function showMessageNotification(message) {
            // 创建通知元素
            const notification = document.createElement('div');
            notification.className = 'message-notification';
            notification.innerHTML = `
                <div class="notification-content">
                    <i class="fas fa-bell"></i>
                    <span>${message}</span>
                    <button class="notification-close">×</button>
                </div>
            `;
            
            // 添加到页面
            document.body.appendChild(notification);
            
            // 自动消失
            setTimeout(() => {
                if (notification.parentNode) {
                    notification.parentNode.removeChild(notification);
                }
            }, 5000);
            
            // 关闭按钮事件
            const closeBtn = notification.querySelector('.notification-close');
            closeBtn.addEventListener('click', () => {
                if (notification.parentNode) {
                    notification.parentNode.removeChild(notification);
                }
            });
        }
        
        // 初始化反馈中心
        function initFeedbackCenter() {
            // 检查用户登录状态
            updateFeedbackCenterUI();
            
            // 监听用户登录状态变化
            window.addEventListener('userLogin', updateFeedbackCenterUI);
            window.addEventListener('userLogout', updateFeedbackCenterUI);
            
            // 初始化反馈页面导航点击事件
            const feedbackTabs = document.querySelectorAll('.feedback-page-tab');
            feedbackTabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    // 移除所有标签的active类
                    feedbackTabs.forEach(t => t.classList.remove('active'));
                    
                    // 为当前点击的标签添加active类
                    tab.classList.add('active');
                    
                    // 获取当前点击的页面类型
                    const pageType = tab.dataset.page;
                    
                    // 隐藏所有反馈内容
                    const feedbackContents = document.querySelectorAll('.feedback-mode-content');
                    feedbackContents.forEach(content => content.classList.remove('active'));
                    
                    // 显示对应的反馈内容
                    if (pageType === 'groupFeedbackPage') {
                        document.getElementById('groupFeedbackContent').classList.add('active');
                    } else if (pageType === 'matchmakerFeedbackPage') {
                        document.getElementById('matchmakerFeedbackContent').classList.add('active');
                    }
                });
            });
        }
        
        // 更新反馈中心UI显示
        function updateFeedbackCenterUI() {
            const currentUser = JSON.parse(localStorage.getItem('currentUser') || 'null');
            
            // 删除登录限制，未登录用户也可以查看反馈中心
            document.getElementById('feedbackLoginPrompt').classList.add('hidden');
            document.getElementById('feedbackContent').classList.remove('hidden');
            
            // 如果已登录，加载反馈数据
            if (currentUser) {
                loadFeedbackData();
            }
        }
        
        // 加载反馈数据
        function loadFeedbackData() {
            // 从localStorage加载反馈数据
            const feedbackData = JSON.parse(localStorage.getItem('feedbackData') || '[]');
            
            // 分离微信群聊和红娘牵线反馈
            const groupFeedback = feedbackData.filter(fb => fb.mode === 'group');
            const matchmakerFeedback = feedbackData.filter(fb => fb.mode === 'matchmaker');
            
            // 更新免费观看次数
            updateViewCounts(groupFeedback, matchmakerFeedback);
            
            // 渲染反馈列表
            renderFeedbackList('group', groupFeedback);
            renderFeedbackList('matchmaker', matchmakerFeedback);
        }
        
        // 更新观看次数
        function updateViewCounts(groupFeedback, matchmakerFeedback) {
            // 移除VIP观看次数限制，所有用户都可以查看所有反馈
            // 不再显示观看次数统计，直接显示所有反馈内容
            
            // 显示所有反馈内容，不限制观看
            document.getElementById('groupFeedbackList').innerHTML = '';
            document.getElementById('matchmakerFeedbackList').innerHTML = '';
            
            // 渲染所有反馈内容
            renderFeedbackList('group', groupFeedback);
            renderFeedbackList('matchmaker', matchmakerFeedback);
        }
        
        // 渲染反馈列表
        function renderFeedbackList(mode, feedbackList) {
            const container = document.getElementById(mode + 'FeedbackList');
            container.innerHTML = '';
            
            feedbackList.forEach((feedback, index) => {
                const feedbackItem = document.createElement('div');
                feedbackItem.className = 'feedback-item';
                
                feedbackItem.innerHTML = `
                    <div class="feedback-item-header">
                        <div class="feedback-item-title">${feedback.title}</div>
                        <div class="feedback-item-date">${feedback.date}</div>
                    </div>
                    <div class="feedback-item-content">${feedback.content}</div>
                    ${feedback.photos && feedback.photos.length > 0 ? `
                        <div class="feedback-item-photos">
                            ${feedback.photos.map(photo => `<img src="${photo}" class="feedback-photo" alt="反馈照片">`).join('')}
                        </div>
                    ` : ''}
                `;
                
                container.appendChild(feedbackItem);
            });
        }
        
        // 提交反馈
        function submitFeedback() {
            if (!currentUser) {
                alert('请先登录');
                return;
            }
            
            const title = document.getElementById('feedbackTitle').value;
            const content = document.getElementById('feedbackContent').value;
            
            // 获取当前选中的反馈模式
            const activeTab = document.querySelector('.feedback-page-tab.active');
            const mode = activeTab ? activeTab.dataset.page === 'groupFeedbackPage' ? 'group' : 'matchmaker' : 'group';
            
            if (!title || !content) {
                alert('请填写反馈标题和内容');
                return;
            }
            
            // 检查VIP状态 - 需要开通VIP才能上传反馈
            if (!currentUser.vip) {
                if (confirm('提交反馈需要开通VIP会员。是否立即开通？')) {
                    // 跳转到首页底部导航的VIP页面
                    switchSection('homeSection');
                    return;
                }
                return;
            }
            
            // 创建反馈对象
            const newFeedback = {
                id: Date.now(),
                title,
                content,
                mode,
                photos: uploadedPhotos,
                date: new Date().toLocaleString(),
                userId: currentUser.id
            };
            
            // 保存到localStorage
            const feedbackData = JSON.parse(localStorage.getItem('feedbackData') || '[]');
            feedbackData.push(newFeedback);
            localStorage.setItem('feedbackData', JSON.stringify(feedbackData));
            
            // 清空表单
            document.getElementById('feedbackTitle').value = '';
            document.getElementById('feedbackContent').value = '';
            uploadedPhotos = [];
            updatePhotoPreview();
            
            // 重新加载反馈数据
            loadFeedbackData();
            
            alert('反馈提交成功！');
        }
        
        // 照片上传相关变量
        let uploadedPhotos = [];
        
        // 更新照片预览
        function updatePhotoPreview() {
            const photoList = document.getElementById('photoList');
            photoList.innerHTML = '';
            
            uploadedPhotos.forEach((photo, index) => {
                const photoItem = document.createElement('div');
                photoItem.className = 'photo-item';
                photoItem.innerHTML = `
                    <img src="${photo}" alt="上传的照片">
                    <div class="photo-remove" onclick="removePhoto(${index})">×</div>
                `;
                photoList.appendChild(photoItem);
            });
        }
        
        // 移除照片
        function removePhoto(index) {
            uploadedPhotos.splice(index, 1);
            updatePhotoPreview();
        }
        
        // 处理照片上传
        function handlePhotoUpload(event) {
            const files = event.target.files;
            if (files.length === 0) return;
            
            Array.from(files).forEach(file => {
                if (!file.type.startsWith('image/')) {
                    alert('请上传图片文件');
                    return;
                }
                
                const reader = new FileReader();
                reader.onload = function(e) {
                    uploadedPhotos.push(e.target.result);
                    updatePhotoPreview();
                };
                reader.readAsDataURL(file);
            });
            
            // 清空文件输入
            event.target.value = '';
        }
        
        // 切换反馈页面函数已删除 - 不再支持群聊和牵线反馈跳转功能
        
        // 切换反馈模式
        function switchFeedbackMode(mode) {
            // 更新模式选择器
            document.querySelectorAll('.feedback-mode-option').forEach(option => {
                option.classList.remove('active');
            });
            document.getElementById(mode + 'Mode').classList.add('active');
            
            // 更新表单模式
            document.getElementById('feedbackMode').value = mode;
            
            // 显示/隐藏相应的反馈列表
            document.getElementById('groupFeedbackSection').classList.toggle('hidden', mode !== 'group');
            document.getElementById('matchmakerFeedbackSection').classList.toggle('hidden', mode !== 'matchmaker');
        }
        
        // 检查红娘牵线支付结果（使用彩虹易支付SDK验证）

        
        // 用户注册
        function registerUser() {
            const username = document.getElementById('registerUsername').value;
            const password = document.getElementById('registerPassword').value;
            const confirmPassword = document.getElementById('registerConfirmPassword').value;
            const phone = document.getElementById('registerPhone').value;
            const age = document.getElementById('registerAge').value;
            const location = document.getElementById('registerLocation').value;
            const bio = document.getElementById('registerBio').value;
            const agreementCheckbox = document.getElementById('registerAgreementCheckbox');
            const agreementError = document.getElementById('registerAgreementError');
            const registerSubmitBtn = document.getElementById('registerSubmitBtn');
            
            // 获取选中的性别
            let gender = '';
            document.querySelectorAll('.gender-option').forEach(option => {
                if (option.classList.contains('active')) {
                    gender = option.getAttribute('data-gender');
                }
            });
            
            // 简单验证
            if (!username.trim()) {
                alert('请输入用户名');
                document.getElementById('registerUsername').focus();
                return;
            }
            
            if (!password) {
                alert('请输入密码');
                document.getElementById('registerPassword').focus();
                return;
            }
            
            if (!confirmPassword) {
                alert('请确认密码');
                document.getElementById('registerConfirmPassword').focus();
                return;
            }
            
            if (password !== confirmPassword) {
                alert('两次输入的密码不一致');
                document.getElementById('registerConfirmPassword').focus();
                return;
            }
            
            // 密码验证 - 必须满足6位数
            if (password.length !== 6) {
                alert('密码必须为6位数');
                document.getElementById('registerPassword').focus();
                return;
            }
            
            // 手机号验证 - 必须输入手机号才能注册（放在其他验证之后，允许用户先填写其他字段）
            if (!phone) {
                alert('必须输入手机号才能注册');
                document.getElementById('registerPhone').focus();
                return;
            }
            
            // 手机号-密码关联验证：检查密码是否与手机号相关
            const phoneRegex = /^1[3-9]\d{9}$/;
            
            // 只有当手机号输入完整时才进行格式验证
            if (phone.length === 11) {
                if (phoneRegex.test(phone)) {
                    // 检查密码是否与手机号相关
                    const lastSixDigits = phone.slice(-6);
                    const firstSixDigits = phone.slice(0, 6);
                    
                    // 密码不能是手机号的前6位或后6位
                    if (password === lastSixDigits || password === firstSixDigits) {
                        alert('密码不能与手机号的前6位或后6位相同');
                        document.getElementById('registerPassword').focus();
                        return;
                    }
                    
                    // 密码不能是连续的6个相同数字
                    if (/^(\d)\1{5}$/.test(password)) {
                        alert('密码不能是连续的6个相同数字');
                        document.getElementById('registerPassword').focus();
                        return;
                    }
                    
                    // 密码不能是简单的递增或递减序列
                    const isSequential = (str) => {
                        const digits = str.split('').map(Number);
                        const diff = digits[1] - digits[0];
                        for (let i = 1; i < digits.length - 1; i++) {
                            if (digits[i + 1] - digits[i] !== diff) {
                                return false;
                            }
                        }
                        return Math.abs(diff) === 1;
                    };
                    
                    if (isSequential(password)) {
                        alert('密码不能是简单的递增或递减序列');
                        document.getElementById('registerPassword').focus();
                        return;
                    }
                } else {
                    // 手机号格式不正确
                    alert('请输入有效的中国大陆手机号码（11位数字，以1开头）');
                    document.getElementById('registerPhone').focus();
                    return;
                }
            } else {
                // 手机号长度不足11位
                alert('手机号必须为11位数字');
                document.getElementById('registerPhone').focus();
                return;
            }
            
            // 检查手机号是否已被注册
            if (users.find(user => user.phone === phone)) {
                alert('该手机号已被注册');
                document.getElementById('registerPhone').focus();
                return;
            }
            
            // 检查声明勾选框 - 需要点击勾选后才能注册
            if (!agreementCheckbox.checked) {
                agreementError.style.display = 'block';
                agreementCheckbox.focus();
                return;
            } else {
                agreementError.style.display = 'none';
            }
            
            // 检查用户名是否已存在
            if (users.find(user => user.username === username)) {
                alert('用户名已存在');
                document.getElementById('registerUsername').focus();
                return;
            }
            
            // 设置加载状态
            registerSubmitBtn.disabled = true;
            registerSubmitBtn.textContent = '注册中...';
            
            try {
                // 创建新用户
                const newUser = {
                    id: Date.now(),
                    username,
                    password,
                    phone,
                    gender,
                    age: parseInt(age),
                    location,
                    bio,
                    vip: false,
                    avatar: null,
                    registerTime: new Date().toLocaleString()
                };
                
                // 保存用户
                users.push(newUser);
                localStorage.setItem('users', JSON.stringify(users));
                
                // 自动登录
                currentUser = newUser;
                localStorage.setItem('currentUser', JSON.stringify(currentUser));
                
                // 更新UI
                updateUserUI();
                
                // 触发登录事件
                const loginEvent = new CustomEvent('userLogin');
                window.dispatchEvent(loginEvent);
                
                alert('注册成功！欢迎使用我们的服务！');
                
                // 清空表单
                document.getElementById('registerUsername').value = '';
                document.getElementById('registerPassword').value = '';
                document.getElementById('registerConfirmPassword').value = '';
                document.getElementById('registerPhone').value = '';
                document.getElementById('registerAge').value = '';
                document.getElementById('registerLocation').value = '';
                document.getElementById('registerBio').value = '';
                agreementCheckbox.checked = false;
                document.querySelectorAll('.gender-option').forEach(option => {
                    option.classList.remove('active');
                });
            } catch (error) {
                console.error('注册失败:', error);
                alert('注册失败，请稍后重试！');
            } finally {
                // 恢复按钮状态
                registerSubmitBtn.disabled = false;
                registerSubmitBtn.textContent = '注册';
            }
        }
        
        // 用户登录
        function loginUser() {
            const username = document.getElementById('loginUsername').value;
            const password = document.getElementById('loginPassword').value;
            const agreementCheckbox = document.getElementById('loginAgreementCheckbox');
            const agreementError = document.getElementById('loginAgreementError');
            const loginSubmitBtn = document.getElementById('loginSubmitBtn');
            
            if (!username.trim()) {
                alert('请输入用户名或手机号');
                document.getElementById('loginUsername').focus();
                return;
            }
            
            if (!password) {
                alert('请输入密码');
                document.getElementById('loginPassword').focus();
                return;
            }
            
            // 密码长度验证：必须为6位数
            if (password.length !== 6) {
                alert('密码必须为6位数');
                document.getElementById('loginPassword').focus();
                return;
            }
            
            // 手机号-密码关联验证：检查密码是否与手机号相关
            const phoneRegex = /^1[3-9]\d{9}$/;
            if (phoneRegex.test(username)) {
                // 如果是手机号格式，检查密码是否与手机号相关
                const lastSixDigits = username.slice(-6);
                const firstSixDigits = username.slice(0, 6);
                
                // 密码不能是手机号的前6位或后6位
                if (password === lastSixDigits || password === firstSixDigits) {
                    alert('密码不能与手机号的前6位或后6位相同');
                    document.getElementById('loginPassword').focus();
                    return;
                }
                
                // 密码不能是连续的6个相同数字
                if (/^(\d)\1{5}$/.test(password)) {
                    alert('密码不能是连续的6个相同数字');
                    document.getElementById('loginPassword').focus();
                    return;
                }
                
                // 密码不能是简单的递增或递减序列
                const isSequential = (str) => {
                    const digits = str.split('').map(Number);
                    const diff = digits[1] - digits[0];
                    for (let i = 1; i < digits.length - 1; i++) {
                        if (digits[i + 1] - digits[i] !== diff) {
                            return false;
                        }
                    }
                    return Math.abs(diff) === 1;
                };
                
                if (isSequential(password)) {
                    alert('密码不能是简单的递增或递减序列');
                    document.getElementById('loginPassword').focus();
                    return;
                }
            }
            
            // 检查声明勾选框
            if (!agreementCheckbox.checked) {
                agreementError.style.display = 'block';
                agreementCheckbox.focus();
                return;
            } else {
                agreementError.style.display = 'none';
            }
            
            // 设置加载状态
            loginSubmitBtn.disabled = true;
            loginSubmitBtn.textContent = '登录中...';
            
            try {
                // 查找用户
                const user = users.find(u => u.username === username && u.password === password);
                
                if (user) {
                    currentUser = user;
                    localStorage.setItem('currentUser', JSON.stringify(currentUser));
                    updateUserUI();
                    
                    // 触发登录事件
                    const loginEvent = new CustomEvent('userLogin');
                    window.dispatchEvent(loginEvent);
                    
                    alert('登录成功！欢迎回来！');
                    
                    // 清空表单
                    document.getElementById('loginUsername').value = '';
                    document.getElementById('loginPassword').value = '';
                    agreementCheckbox.checked = false;
                } else {
                    alert('用户名或密码错误，请检查后重试！');
                    document.getElementById('loginPassword').focus();
                }
            } catch (error) {
                console.error('登录失败:', error);
                alert('登录失败，请稍后重试！');
            } finally {
                // 恢复按钮状态
                loginSubmitBtn.disabled = false;
                loginSubmitBtn.textContent = '登录';
            }
        }
        
        // 用户退出登录
        function logoutUser() {
            // 确认是否退出登录
            if (!confirm('确定要退出登录吗？')) {
                return;
            }
            
            try {
                currentUser = null;
                localStorage.removeItem('currentUser');
                updateUserUI();
                
                // 触发退出登录事件
                const logoutEvent = new CustomEvent('userLogout');
                window.dispatchEvent(logoutEvent);
                
                alert('已成功退出登录');
            } catch (error) {
                console.error('退出登录失败:', error);
                alert('退出登录失败，请稍后重试！');
            }
        }
        
        // 编辑用户资料
        function editUserProfile() {
            const username = document.getElementById('editUsername').value;
            const age = document.getElementById('editAge').value;
            const location = document.getElementById('editLocation').value;
            const bio = document.getElementById('editBio').value;
            
            // 获取选中的性别
            let gender = '';
            document.querySelectorAll('.gender-option').forEach(option => {
                if (option.classList.contains('active')) {
                    gender = option.getAttribute('data-gender');
                }
            });
            
            // 简单验证
            if (!username) {
                alert('请填写用户名');
                return;
            }
            
            // 更新用户信息
            currentUser.username = username;
            currentUser.gender = gender;
            currentUser.age = parseInt(age);
            currentUser.location = location;
            currentUser.bio = bio;
            
            // 保存更新
            const userIndex = users.findIndex(u => u.id === currentUser.id);
            if (userIndex !== -1) {
                users[userIndex] = currentUser;
                localStorage.setItem('users', JSON.stringify(users));
                localStorage.setItem('currentUser', JSON.stringify(currentUser));
            }
            
            // 牵线资料功能已关闭，不再同步更新牵线资料
            
            
            // 更新UI
            updateUserUI();
            
            // 返回个人资料页面
            profileContent.classList.remove('hidden');
            editProfileContent.classList.add('hidden');
            
            alert('个人资料已更新，牵线资料也已同步更新');
        }
        
        // 显示编辑个人资料表单
        function showEditProfileForm() {
            // 填充表单数据
            document.getElementById('editUsername').value = currentUser.username || '';
            document.getElementById('editAge').value = currentUser.age || '';
            document.getElementById('editLocation').value = currentUser.location || '';
            document.getElementById('editBio').value = currentUser.bio || '';
            
            // 设置性别选项
            document.querySelectorAll('.gender-option').forEach(option => {
                option.classList.remove('active');
                if (option.getAttribute('data-gender') === currentUser.gender) {
                    option.classList.add('active');
                }
            });
            
            // 显示编辑表单
            profileContent.classList.add('hidden');
            editProfileContent.classList.remove('hidden');
        }
        
        // 初始化红娘牵线功能
        // 牵线服务通知相关函数
// 移除重复的函数定义，保留下面的简化版本

// 牵线服务通知相关功能
function showMatchmakerNotification() {
    matchmakerNotificationModal.classList.remove('hidden');
}

function hideMatchmakerNotification() {
    matchmakerNotificationModal.classList.add('hidden');
}

// 检查用户是否已经看过通知
function hasUserSeenNotification() {
    return localStorage.getItem('matchmakerNotificationSeen') === 'true';
}

// 标记通知为已查看
function markNotificationAsSeen() {
    localStorage.setItem('matchmakerNotificationSeen', 'true');
}

// 确认按钮点击事件
confirmNotificationBtn.addEventListener('click', function() {
    markNotificationAsSeen();
    hideMatchmakerNotification();
});

// 点击模态框外部关闭通知
matchmakerNotificationModal.addEventListener('click', function(e) {
    if (e.target === matchmakerNotificationModal) {
        // 点击外部不标记为已查看，只有点击确认按钮才标记
        hideMatchmakerNotification();
    }
});

// 测试函数：允许用户在控制台手动触发通知显示（方便测试）
window.testMatchmakerNotification = function() {
    // 清除已查看标记，确保通知会显示
    localStorage.removeItem('matchmakerNotificationSeen');
    // 显示通知
    showMatchmakerNotification();
    console.log('牵线服务通知已显示，可通过 localStorage.removeItem("matchmakerNotificationSeen") 重置通知状态');
};

function initMatchmaker() {
            matchmakerContent.innerHTML = '';
            
            if (!currentUser) {
                // 用户未登录，显示登录提示
                const loginPrompt = document.createElement('div');
                loginPrompt.className = 'matchmaker-login-prompt';
                loginPrompt.innerHTML = `
                    <i class="fas fa-heart"></i>
                    <h3>请先登录</h3>
                    <p>登录后即可开始寻找志同道合的朋友，拓展您的社交圈</p>
                    <button class="btn btn-primary" id="matchmakerLoginBtn">立即登录</button>
                `;
                matchmakerContent.appendChild(loginPrompt);
                
                // 添加登录按钮事件
                document.getElementById('matchmakerLoginBtn').addEventListener('click', () => {
                    switchSection('profileSection');
                });
                
                return;
            }
            
            // 创建牵线功能头部
            const matchmakerHeader = document.createElement('div');
            matchmakerHeader.className = 'matchmaker-header';
            matchmakerHeader.innerHTML = `
                <h2>牵线用户数据</h2>
                <p>浏览和查看牵线用户信息</p>
                <div class="trust-guarantees">
                    <div class="guarantee-item">
                        <i class="fas fa-shield-alt"></i>
                        <span>绝对真实可靠</span>
                    </div>
                    <div class="guarantee-item">
                        <i class="fas fa-undo-alt"></i>
                        <span>24小时不满意随时退款</span>
                    </div>
                    <div class="guarantee-item">
                        <i class="fas fa-database"></i>
                        <span>资源齐全</span>
                    </div>
                    <div class="guarantee-item">
                        <i class="fas fa-robot"></i>
                        <span>自动退款系统</span>
                    </div>
                </div>
            `;
            matchmakerContent.appendChild(matchmakerHeader);
            
            // 创建牵线资料操作区域
            const profileActionSection = document.createElement('div');
            profileActionSection.className = 'matchmaker-profile-action';
            profileActionSection.innerHTML = `
                <div class="profile-action-card">
                    <div class="card-icon">
                    </div>
                    <div class="card-content">
                        <h4>牵线服务</h4>
                        <p>浏览和选择您感兴趣的用户，查看详细资料</p>
                    </div>
                </div>
            `;
            matchmakerContent.appendChild(profileActionSection);
            
            // 添加牵线资料提示样式
            const style = document.createElement('style');
            style.textContent = `
                .matchmaker-header {
                    text-align: center;
                    margin-bottom: 20px;
                    padding: 20px;
                    background-color: #f8f9fa;
                    border-radius: 8px;
                }
                .matchmaker-header h2 {
                    margin: 0 0 10px 0;
                    color: #333;
                }
                .matchmaker-header p {
                    margin: 0;
                    color: #666;
                }
                .trust-guarantees {
                    display: flex;
                    justify-content: center;
                    flex-wrap: wrap;
                    gap: 20px;
                    margin-top: 15px;
                    padding-top: 15px;
                    border-top: 1px solid #e9ecef;
                }
                .guarantee-item {
                    display: flex;
                    align-items: center;
                    gap: 5px;
                    padding: 10px 15px;
                    background-color: rgba(103, 58, 183, 0.1);
                    border-radius: 20px;
                    color: #673ab7;
                    font-weight: 500;
                    font-size: 14px;
                }
                .guarantee-item i {
                    font-size: 16px;
                }
                .matchmaker-profile-info {
                    margin: 20px 0;
                    padding: 20px;
                    background-color: #f8f9fa;
                    border-radius: 8px;
                    text-align: center;
                }
                .profile-info-card {
                    display: flex;
                    flex-direction: column;
                    align-items: center;
                    padding: 20px;
                    background-color: white;
                    border-radius: 8px;
                    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
                }
                .card-icon {
                    font-size: 48px;
                    color: #4CAF50;
                    margin-bottom: 15px;
                }
                .card-content h4 {
                    margin: 10px 0;
                    color: #333;
                }
                .card-content p {
                    color: #666;
                    margin: 0;
                }
                

                .btn-secondary {
                    background: #6c757d;
                    color: white;
                    border: none;
                    padding: 8px 16px;
                    border-radius: 4px;
                    cursor: pointer;
                    margin-right: 10px;
                }
                .form-actions {
                    margin-top: 30px;
                    text-align: right;
                }
                .form-check {
                    display: flex;
                    align-items: center;
                    margin-bottom: 10px;
                }
                .form-check input {
                    margin-right: 8px;
                }
                .tags-input {
                    display: flex;
                    flex-wrap: wrap;
                    gap: 8px;
                    margin-top: 8px;
                }
                .tag {
                    background: #e9ecef;
                    padding: 4px 10px;
                    border-radius: 16px;
                    font-size: 12px;
                    display: flex;
                    align-items: center;
                }
                .tag .remove-tag {
                    margin-left: 6px;
                    cursor: pointer;
                    font-size: 14px;
                }
            `;
            document.head.appendChild(style);
            
            // 牵线资料上传功能已关闭
            
            
            // VIP用户且已上传资料，显示牵线匹配界面
            // 牵线资料上传和编辑功能已关闭，直接继续显示用户列表
            
            
            
            // 显示牵线匹配结果和用户列表
            const matchResult = document.createElement('div');
            matchResult.className = 'matchmaker-match-result';
            matchResult.innerHTML = `
                <div class="result-header">
                    <h4>为您推荐的匹配对象</h4>
                </div>
                <div class="match-status">
                    <div class="status-message">智能匹配已完成</div>
                    <div class="status-tip">已根据您的条件进行智能匹配</div>
                </div>
                <button class="btn btn-primary" id="refreshMatchesBtn">刷新匹配结果</button>
            `;
            matchmakerContent.appendChild(matchResult);
            
            // 刷新匹配按钮事件
            document.getElementById('refreshMatchesBtn').addEventListener('click', function() {
                alert('匹配结果已更新！');
                displayMatchmakerUserList();
            });
            
            // 初始化城市选择和用户列表
            initMatchmakerCitySelection();
            
            // 初始化性别筛选功能
            initMatchmakerGenderFilter();
            
            console.log('牵线功能初始化完成');
        }
        
        // 显示牵线资料上传表单

            
            // 生成牵线用户数据的函数 - 生成417个城市的用户数据，确保每个用户数据唯一且适合"一日情侣"主题
            function generateMatchmakerUsers() {
                // 按地区组织的固定城市数据（包含417个城市）
                const regionCities = {
                    "华北地区": ["北京", "天津", "石家庄", "太原", "呼和浩特", "唐山", "秦皇岛", "邯郸", "邢台", "保定", "张家口", "承德", "沧州", "廊坊", "衡水", "大同", "阳泉", "长治", "晋城", "朔州", "晋中", "运城", "忻州", "临汾", "吕梁", "包头", "赤峰", "通辽", "鄂尔多斯", "呼伦贝尔", "巴彦淖尔", "乌兰察布", "兴安", "锡林郭勒", "阿拉善"],
                    "东北地区": ["沈阳", "大连", "长春", "哈尔滨", "鞍山", "抚顺", "本溪", "丹东", "锦州", "营口", "阜新", "辽阳", "盘锦", "铁岭", "朝阳", "葫芦岛", "吉林", "四平", "辽源", "通化", "白山", "松原", "白城", "延边", "齐齐哈尔", "鸡西", "鹤岗", "双鸭山", "大庆", "伊春", "佳木斯", "七台河", "牡丹江", "黑河", "绥化", "大兴安岭", "铁力", "同江", "富锦", "绥芬河", "海林"],
                    "华东地区": ["上海", "南京", "杭州", "宁波", "苏州", "无锡", "合肥", "福州", "厦门", "南昌", "济南", "青岛", "徐州", "常州", "南通", "连云港", "淮安", "盐城", "扬州", "镇江", "泰州", "宿迁", "温州", "嘉兴", "湖州", "绍兴", "金华", "衢州", "舟山", "台州", "丽水", "芜湖", "蚌埠", "淮南", "马鞍山", "淮北", "铜陵", "安庆", "黄山", "滁州", "阜阳", "宿州", "六安", "亳州", "池州", "宣城", "莆田", "三明", "泉州", "漳州", "南平", "龙岩", "宁德", "景德镇", "萍乡", "九江", "新余", "鹰潭", "赣州", "吉安", "宜春", "抚州", "上饶", "淄博", "枣庄", "东营", "烟台", "潍坊", "济宁", "泰安", "威海", "日照", "临沂", "德州", "聊城", "滨州", "菏泽", "江阴", "宜兴", "常熟", "张家港", "昆山", "太仓", "如皋", "海门", "启东", "东台", "大丰", "仪征", "高邮", "江都", "丹阳", "扬中", "句容"],
                    "中南地区": ["广州", "深圳", "武汉", "郑州", "长沙", "南宁", "海口", "韶关", "珠海", "汕头", "佛山", "江门", "湛江", "茂名", "肇庆", "惠州", "梅州", "汕尾", "河源", "阳江", "清远", "东莞", "中山", "潮州", "揭阳", "云浮", "黄石", "十堰", "宜昌", "襄阳", "鄂州", "荆门", "孝感", "荆州", "黄冈", "咸宁", "随州", "恩施", "开封", "洛阳", "平顶山", "安阳", "鹤壁", "新乡", "焦作", "濮阳", "许昌", "漯河", "三门峡", "南阳", "商丘", "信阳", "周口", "驻马店", "济源", "株洲", "湘潭", "衡阳", "邵阳", "岳阳", "常德", "张家界", "益阳", "郴州", "永州", "怀化", "娄底", "柳州", "桂林", "梧州", "北海", "防城港", "钦州", "贵港", "玉林", "百色", "贺州", "河池", "来宾", "崇左", "三亚", "增城", "从化", "番禺", "花都", "龙门", "惠东", "博罗", "英德", "连州", "台山", "开平", "鹤山", "恩平", "高州", "化州", "信宜", "阳春", "雷州", "吴川", "廉江", "高要", "四会", "兴宁", "五华", "丰顺", "陆丰", "海丰", "紫金", "龙川", "连平", "和平", "罗定", "新兴", "郁南", "大冶", "阳新", "丹江口", "枝江", "宜都", "当阳"],
                    "西南地区": ["重庆", "成都", "昆明", "贵阳", "拉萨", "自贡", "攀枝花", "泸州", "德阳", "绵阳", "广元", "遂宁", "内江", "乐山", "南充", "眉山", "宜宾", "广安", "达州", "雅安", "巴中", "资阳", "阿坝", "甘孜", "凉山", "六盘水", "遵义", "安顺", "毕节", "铜仁", "黔西南", "黔东南", "黔南", "曲靖", "玉溪", "保山", "昭通", "丽江", "普洱", "临沧", "楚雄", "红河", "文山", "西双版纳", "大理", "德宏", "怒江", "迪庆", "日喀则", "昌都", "林芝", "山南", "那曲", "阿里", "合川", "永川", "南川", "江津", "长寿", "涪陵", "万州", "丰都", "垫江", "忠县", "云阳", "奉节", "巫山", "巫溪", "黔江", "石柱", "秀山", "酉阳", "彭水", "都江堰", "彭州", "邛崃", "崇州", "金堂", "双流", "郫县", "大邑", "蒲江", "新津", "广汉", "什邡", "绵竹", "中江", "罗江", "江油", "三台"],
                    "西北地区": ["西安", "兰州", "银川", "西宁", "乌鲁木齐", "铜川", "宝鸡", "咸阳", "渭南", "延安", "汉中", "榆林", "安康", "商洛", "嘉峪关", "金昌", "白银", "天水", "武威", "张掖", "平凉", "酒泉", "庆阳", "定西", "陇南", "临夏", "甘南", "石嘴山", "吴忠", "固原", "中卫", "海东", "海北", "黄南", "海南", "果洛", "玉树", "海西", "克拉玛依", "吐鲁番", "哈密", "昌吉", "博尔塔拉", "巴音郭楞", "阿克苏", "克孜勒苏", "喀什", "和田", "伊犁", "塔城", "阿勒泰", "兴平", "户县", "蓝田", "周至", "高陵", "三原", "泾阳", "乾县", "礼泉", "永寿", "彬县", "长武", "旬邑", "淳化", "武功", "韩城", "华阴", "潼关", "大荔", "合阳", "澄城", "蒲城", "白水", "富平", "宜君", "凤翔", "岐山", "扶风", "眉县", "陇县", "千阳", "麟游", "凤县", "太白", "略阳", "勉县", "留坝", "佛坪", "宁强", "南郑", "城固", "洋县", "西乡", "镇巴"]
                };
                
                // 固定的姓名库 - 中国常见姓氏和名字
                const commonFemaleFirstNames = ['雯', '婷', '莉', '娜', '艳', '娟', '秀', '敏', '静', '丽', '芳', '梅', '华', '琴', '慧', '莹', '霞', '香', '燕', '佳', '美', '雪', '红', '玉', '桂', '兰', '凤', '菊', '英', '萍'];
                const commonMaleFirstNames = ['伟', '强', '军', '勇', '杰', '涛', '磊', '超', '明', '刚', '辉', '飞', '敏', '浩', '鑫', '洋', '兵', '宇', '轩', '晨', '峰', '龙', '虎', '豹', '彪', '忠', '孝', '义', '德', '智'];
                const commonLastNames = ['王', '李', '张', '刘', '陈', '杨', '赵', '黄', '周', '吴', '徐', '孙', '胡', '朱', '高', '林', '何', '郭', '马', '罗', '梁', '宋', '郑', '谢', '韩', '唐', '冯', '于', '董', '萧'];
                
                // 偏远地区特有的少数民族姓氏和名字
                const remoteLastNames = ['扎西', '卓玛', '阿依', '库尔班', '铁木尔', '巴特尔', '呼日勒', '苏日娜', '乌兰', '其木格', '布和', '图雅', '朝鲁', '格日勒', '达瓦', '央金', '拉姆', '顿珠', '尼玛', '次仁', '强巴', '卓嘎', '巴桑', '普布', '德吉', '白玛', '措姆', '多吉', '旺堆', '索朗'];
                const remoteFemaleFirstNames = ['卓玛', '央金', '拉姆', '德吉', '白玛', '措姆', '次仁央宗', '格桑梅朵', '索朗卓玛', '达娃卓玛', '阿依古丽', '古丽仙', '帕丽达', '热依汗', '米热古丽', '迪丽娜尔', '玛依拉', '娜孜古丽', '苏日娜', '其木格', '乌兰托娅', '图雅', '格日勒', '萨日娜', '乌云其其格', '阿拉坦图雅', '诺敏', '其木格', '斯琴高娃', '塔娜'];
                const remoteMaleFirstNames = ['扎西', '顿珠', '尼玛', '次仁', '强巴', '多吉', '旺堆', '索朗', '达瓦', '格桑', '库尔班', '铁木尔', '阿不都', '依明', '买买提', '艾力', '玉山', '吐尔逊', '吾买尔', '阿不力孜', '巴特尔', '呼日勒', '朝鲁', '布和', '斯琴巴特尔', '乌云毕力格', '那顺宝音', '宝力高', '巴雅尔', '吉日嘎拉'];
                
                // 定义偏远城市列表
                const remoteCities = ['拉萨', '日喀则', '昌都', '林芝', '山南', '那曲', '阿里', '乌鲁木齐', '克拉玛依', '吐鲁番', '哈密', '昌吉', '博尔塔拉', '巴音郭楞', '阿克苏', '克孜勒苏', '喀什', '和田', '伊犁', '塔城', '阿勒泰', '西宁', '海东', '海北', '黄南', '海南', '果洛', '玉树', '海西', '呼和浩特', '包头', '乌海', '赤峰', '通辽', '鄂尔多斯', '呼伦贝尔', '巴彦淖尔', '乌兰察布', '兴安', '锡林郭勒', '阿拉善', '阿坝', '甘孜', '凉山', '西双版纳', '德宏', '怒江', '迪庆', '文山', '大理', '楚雄', '红河', '普洱', '临沧', '保山', '昭通', '丽江', '黔东南', '黔南', '黔西南', '毕节', '铜仁'];
                
                // 多样化的标签库
                const personalityTags = ['温柔善良', '活泼开朗', '成熟稳重', '幽默风趣', '认真负责', '独立自主', '善解人意', '乐观向上', '沉稳内敛', '热情大方'];
                const hobbyTags = ['爱好旅行', '喜欢运动', '热爱阅读', '音乐达人', '美食爱好者', '电影迷', '摄影爱好者', '健身达人', '瑜伽爱好者', '舞蹈爱好者'];
                const lifestyleTags = ['早睡早起', '夜猫子', '素食主义', '喜欢烹饪', '注重养生', '追求时尚', '简约生活', '喜欢社交', '享受独处', '喜欢宠物'];
                
                // 女生特有吸引人的标签
                const femaleAttractiveTags = ['身材曼妙', '气质优雅', '温柔体贴', '小鸟依人', '风情万种', '性感迷人', '曲线玲珑', '长发披肩', '甜美可爱', '优雅大方'];
                
                // 职业库
                const professions = ['医生', '教师', '工程师', '设计师', '程序员', '销售经理', '市场营销', '人力资源', '财务会计', '金融分析师', '创业者', '公务员', '律师', '科研人员', '艺术家'];
                

                
                // 收入范围
                const incomeLevels = ['5k以下', '5k-10k', '10k-20k', '20k-30k', '30k以上'];
                
                // 性格特点
                const characterTraits = ['开朗', '内向', '稳重', '幽默', '温柔', '直率', '豪爽', '细腻', '理性', '感性'];
                
                // 女生特有属性
                const appearances = ['甜美', '成熟', '可爱', '性感', '优雅'];
                
                // 生成固定数量的用户
                const users = [];
                let userId = 1;
                
                // 固定随机种子函数，确保每次生成的随机数相同
                function seededRandom(seed) {
                    const x = Math.sin(seed++) * 10000;
                    return x - Math.floor(x);
                }
                
                // 为每个区域的每个城市生成20-40个用户
                Object.values(regionCities).forEach(regionCities => {
                    regionCities.forEach(city => {
                        // 为每个城市生成10-25个用户
                        const citySeed = city.charCodeAt(0) + city.charCodeAt(city.length - 1);
                        const userCount = Math.floor(seededRandom(citySeed) * 16) + 10; // 10-25个用户
                        
                        for (let userInCity = 0; userInCity < userCount; userInCity++) {
                            const userSeed = citySeed * 100 + userInCity;
                            
                            // 控制性别比例，女多男少（约6:4）
                            const isFemale = (userId % 5 < 3); // 60%的概率生成女性
                            const gender = isFemale ? 'female' : 'male';
                            
                            // 检查是否为偏远城市，使用相应的名字库
                            const isRemoteCity = remoteCities.includes(city);
                            
                            // 选择姓氏库和名字库
                            const selectedLastNames = isRemoteCity ? remoteLastNames : commonLastNames;
                            const selectedFemaleFirstNames = isRemoteCity ? remoteFemaleFirstNames : commonFemaleFirstNames;
                            const selectedMaleFirstNames = isRemoteCity ? remoteMaleFirstNames : commonMaleFirstNames;
                            
                            // 生成固定的姓名，基于索引确保唯一性
                            const lastNameIndex = (userId % selectedLastNames.length);
                            const firstNameIndex = gender === 'female' 
                                ? (userId % selectedFemaleFirstNames.length)
                                : (userId % selectedMaleFirstNames.length);
                            
                            // 生成中国汉字名字（偏远城市使用少数民族名字，普通城市使用常见名字）
                            const name = `${selectedLastNames[lastNameIndex]}${gender === 'female' ? selectedFemaleFirstNames[firstNameIndex] : selectedMaleFirstNames[firstNameIndex]}`;
                            
                            // 生成固定的年龄，18-30岁为主，极少数其他年龄段
                            let age;
                            if (userId % 10 === 0) { // 10%的概率生成31-35岁的用户
                                age = 31 + (userId % 5); // 31-35岁
                            } else { // 90%的概率生成18-30岁的用户
                                age = 18 + (userId % 13); // 18-30岁
                            }
                            
                            // 使用当前城市作为位置
                            const location = city;
                            
                            // 选择固定的标签组合，确保每个用户的标签不同
                            const userTags = [];
                            
                            // 为女生添加特有标签
                            if (isFemale) {
                                userTags.push(femaleAttractiveTags[(userId + 3) % femaleAttractiveTags.length]);
                            }
                            
                            // 从不同类型的标签中选择固定的标签
                            userTags.push(personalityTags[(userId + 5) % personalityTags.length]);
                            userTags.push(hobbyTags[(userId + 7) % hobbyTags.length]);
                            
                            // 部分用户有更多标签
                            if (userId % 3 === 0) {
                                userTags.push(lifestyleTags[(userId + 9) % lifestyleTags.length]);
                            }
                            if (userId % 5 === 0 && !isFemale) {
                                userTags.push(personalityTags[(userId + 11) % personalityTags.length]);
                            }
                            
                            // 使用性别标识作为头像，简单区分男女
                            const photo = gender === 'female' ? 'female' : 'male';
                            
                            // 简化处理，不生成更多照片
                            const morePhotos = [];
                            
                            // 详细资料（固定且唯一）
                            const details = {
                                height: gender === 'female' 
                                    ? 155 + (userId % 20) // 155-175cm
                                    : 165 + (userId % 30), // 165-195cm
                                weight: gender === 'female' 
                                    ? 45 + (userId % 20) // 45-65kg
                                    : 60 + (userId % 30), // 60-90kg

                                occupation: professions[(userId + 4) % professions.length],
                                income: incomeLevels[(userId + 6) % incomeLevels.length],
                                character: characterTraits[(userId + 8) % characterTraits.length],
                                hobbies: userTags.slice(0, 1 + (userId % 3)), // 1-3个爱好
                                // 更多照片（仅VIP可见）
                                morePhotos
                            };
                            
                            // 为女生添加更多吸引人的属性
                            if (isFemale) {
                                details.appearance = appearances[(userId + 3) % appearances.length];
                            }
                            
                            // 生成个性化描述，符合一日情侣主题
                            let description;
                            if (isFemale) {
                                const femaleDescriptions = [
                                    `${name}，${age}岁，来自${location}。性格${details.character}，是个${details.appearance}的女生。想找个一日情侣，一起度过浪漫的一天。`,
                                    `大家好，我是${name}，在${location}工作。我${details.character}、${userTags[0]}，期待一场美好的一日约会。`,
                                    `${name}，${location}人，${age}岁。我喜欢${details.hobbies.join('、')}，性格${details.character}，想找个聊得来的人一起体验一日情侣的感觉。`
                                ];
                                description = femaleDescriptions[userId % femaleDescriptions.length];
                            } else {
                                const maleDescriptions = [
                                    `我是${name}，${age}岁，在${location}从事${details.occupation}工作。想找个一日情侣，一起探索城市的美好。`,
                                    `${location}的${name}，${age}岁，性格${details.character}，喜欢${details.hobbies.join('、')}。期待和你度过浪漫的一天。`,
                                    `大家好，我是${name}，来自${location}。我${details.character}、${userTags[0]}，想找个有趣的人体验一日情侣的约会。`
                                ];
                                description = maleDescriptions[userId % maleDescriptions.length];
                            }
                            
                            // 固定的联系方式，基于用户ID生成
                            const contact = {
                                wechat: `match_${name}${(userId + 1000).toString().substr(-4)}`,
                                phone: `1${3000000000 + (userId * 1000000)}`,
                                email: `match_${name.toLowerCase()}@example.com`
                            };
                            
                            // 创建用户对象，确保ID唯一且固定
                            users.push({
                                id: `match_user_${userId}`,
                                name: name,
                                age: age,
                                gender: gender,
                                location: location,
                                tags: userTags,
                                photo: photo,
                                description: description,
                                // 固定的验证状态
                                verified: userId % 3 !== 0, // 约2/3的用户已验证
                                // 固定的联系方式信息
                                contact: contact,
                                // 更多详细资料
                                details: details,
                                // 一日情侣个性化配对信息，每个用户都不同
                                idealPartner: {
                                    ageRange: gender === 'female' 
                                        ? [`${Math.max(20, age - 5)}`, `${Math.min(40, age + 5)}`] // 一日情侣年龄范围更灵活
                                        : [`${Math.max(20, age - 5)}`, `${Math.min(40, age + 5)}`], // 一日情侣年龄范围更灵活
                                    location: location, // 优先同城，方便见面
                                    heightRange: gender === 'female' 
                                        ? ['165', '190'] // 身高范围更宽松
                                        : ['150', '175'], // 身高范围更宽松
                                    // 一日情侣更注重兴趣和性格匹配
                                    interests: details.hobbies,
                                    personality: userTags.filter(tag => personalityTags.includes(tag))
                                }
                            });
                            
                            userId++;
                        }
                    });
                });
                
                console.log(`已生成${users.length}个适合一日情侣主题的固定牵线用户数据`);
                return users;
            }
            
            // 添加牵线用户列表功能
            function displayMatchmakerUserList() {
                // 调用generateMatchmakerUsers生成固定的用户数据
                const fixedUsers = generateMatchmakerUsers();
                
                // 从localStorage读取用户上传的资料
                const uploadedUsers = JSON.parse(localStorage.getItem('matchmakerUsers') || '[]');
                
                // 合并固定用户数据和上传的用户数据
                const allUsers = [...fixedUsers, ...uploadedUsers];
                
                console.log('牵线用户数据统计:', { 
                    fixedUsersCount: fixedUsers.length, 
                    uploadedUsersCount: uploadedUsers.length,
                    totalUsersCount: allUsers.length 
                });
                
                // 根据选择的城市和性别过滤用户
                let matchmakerUsersData = selectedMatchmakerCity && selectedMatchmakerCity !== '全国'
                    ? allUsers.filter(user => user.location === selectedMatchmakerCity)
                    : allUsers;
                
                // 按性别筛选
                if (selectedMatchmakerGender !== 'all') {
                    matchmakerUsersData = matchmakerUsersData.filter(user => user.gender === selectedMatchmakerGender);
                }
                    
                console.log('牵线用户列表已更新，当前选择城市:', selectedMatchmakerCity || '全国', 
                          '显示用户数量:', matchmakerUsersData.length);
                
                // 创建用户列表容器
                const userListContainer = document.createElement('div');
                userListContainer.className = 'matchmaker-user-list';
                
                // 添加标题和统计信息
                const listTitle = selectedMatchmakerCity 
                    ? `${selectedMatchmakerCity}的牵线用户` 
                    : '全部牵线用户';
                
                userListContainer.innerHTML = `
                    <div class="matchmaker-list-header">
                        <h4>${listTitle}</h4>
                        <span class="matchmaker-user-count">共${matchmakerUsersData.length}位用户</span>
                    </div>
                `;
                
                // 清空之前可能存在的用户列表
                const existingList = matchmakerContent.querySelector('.matchmaker-user-list');
                if (existingList) {
                    matchmakerContent.removeChild(existingList);
                }
                
                // 添加用户列表
                matchmakerContent.appendChild(userListContainer);
                
                // 添加每个用户项
                matchmakerUsersData.forEach(user => {
                    const userItem = document.createElement('div');
                    userItem.className = 'matchmaker-user-list-item';
                    userItem.dataset.userId = user.id;
                    userItem.innerHTML = `
                        <div class="matchmaker-user-list-avatar">
                            <div class="gender-avatar ${user.photo}">
                                <i class="fas fa-${user.photo === 'female' ? 'female' : 'male'}"></i>
                            </div>
                        </div>
                        <div class="matchmaker-user-list-info">
                            <div class="matchmaker-user-list-name">${user.name}</div>
                            <div class="matchmaker-user-list-basic">${user.age}岁 · ${user.gender === 'male' ? '男' : '女'} · ${user.location}</div>
                            <div class="matchmaker-user-list-tags">
                                ${user.tags.map(tag => `<div class="matchmaker-user-list-tag">${tag}</div>`).join('')}
                            </div>
                        </div>
                        <button class="btn btn-primary view-contact-btn" data-user-id="${user.id}">查看联系方式</button>
                    `;
                    
                    userListContainer.appendChild(userItem);
                    
                    // 添加查看联系方式按钮事件
                    userItem.querySelector('.view-contact-btn').addEventListener('click', function(e) {
                        e.stopPropagation();
                        const userId = this.getAttribute('data-user-id');
                        viewUserContact(userId);
                    });
                    
                    // 添加用户项点击事件，查看用户详情
                    userItem.addEventListener('click', function() {
                        const userId = this.getAttribute('data-user-id');
                        // 查找对应的用户对象
                        const userObj = allUsers.find(u => u.id === userId);
                        if (userObj) {
                            viewUserDetail(userObj);
                        }
                    });
                });
                
                // 添加列表样式和性别头像样式
                const style = document.createElement('style');
                style.textContent = `
                    .matchmaker-list-header {
                        display: flex;
                        justify-content: space-between;
                        align-items: center;
                        margin-bottom: 20px;
                        padding-bottom: 10px;
                        border-bottom: 2px solid #f0f0f0;
                    }
                    .matchmaker-user-count {
                        color: #666;
                    }
                    
                    /* 性别头像样式 */
                    .gender-avatar {
                        width: 100%;
                        height: 100%;
                        border-radius: 50%;
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        font-size: 28px;
                        font-weight: 500;
                        transition: all 0.3s ease;
                        position: relative;
                        overflow: hidden;
                    }
                    
                    .gender-avatar::before {
                        content: '';
                        position: absolute;
                        top: 0;
                        left: 0;
                        right: 0;
                        bottom: 0;
                        background: linear-gradient(135deg, rgba(255, 255, 255, 0.2) 0%, rgba(255, 255, 255, 0) 50%);
                        z-index: 1;
                    }
                    
                    .gender-avatar i {
                        position: relative;
                        z-index: 2;
                    }
                    
                    .gender-avatar.female {
                        background: linear-gradient(135deg, #ffd9e8 0%, #ffb3d1 50%, #ff99c2 100%);
                        color: #d9176d;
                    }
                    
                    .gender-avatar.male {
                        background: linear-gradient(135deg, #d9e8ff 0%, #b3d1ff 50%, #99c2ff 100%);
                        color: #175cd9;
                    }
                    
                    .gender-avatar:hover {
                        transform: translateY(-2px);
                        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
                    }
                    
                    /* 详情页面的性别头像更大 */
                    .matchmaker-user-detail-main-photo .gender-avatar {
                        width: 100%;
                        height: 100%;
                        font-size: 72px;
                        border-radius: 15px;
                        box-shadow: 0 4px 16px rgba(0, 0, 0, 0.2);
                    }
                    
                    .matchmaker-user-detail-main-photo .gender-avatar:hover {
                        transform: scale(1.02);
                    }
                        font-size: 14px;
                        font-weight: normal;
                    }
                `;
                document.head.appendChild(style);
            }
            

            
            // 初始化牵线功能的城市选择
            function initMatchmakerCitySelection() {
                // 从localStorage获取上次选择的城市，如果没有则默认选择"全国"
                const savedCity = localStorage.getItem('selectedMatchmakerCity');
                selectedMatchmakerCity = savedCity || '全国';
                console.log(`牵线功能初始化，当前选择城市: ${selectedMatchmakerCity}`);
                
                // 初始化城市选择UI并更新用户列表
                displayMatchmakerCityGrid();
                displayMatchmakerUserList();
            }
            
            // 初始化性别筛选功能
            function initMatchmakerGenderFilter() {
                // 获取性别筛选按钮和当前用户性别切换按钮
                const genderButtons = document.querySelectorAll('.gender-btn[data-gender]');
                const myGenderButtons = document.querySelectorAll('.gender-btn[data-my-gender]');
                
                // 恢复之前的选择
                if (selectedMatchmakerGender) {
                    genderButtons.forEach(btn => {
                        if (btn.dataset.gender === selectedMatchmakerGender) {
                            btn.classList.add('active');
                        } else {
                            btn.classList.remove('active');
                        }
                    });
                }
                
                // 添加性别筛选点击事件监听器
                genderButtons.forEach(btn => {
                    // 先移除可能存在的旧事件监听器
                    btn.onclick = null;
                    
                    btn.addEventListener('click', function() {
                        // 移除所有性别筛选按钮的active类
                        genderButtons.forEach(b => b.classList.remove('active'));
                        
                        // 添加当前按钮的active类
                        this.classList.add('active');
                        
                        // 更新选择的性别
                        selectedMatchmakerGender = this.dataset.gender;
                        
                        // 保存到localStorage
                        localStorage.setItem('selectedMatchmakerGender', selectedMatchmakerGender);
                        
                        console.log(`牵线功能性别筛选已更新: ${selectedMatchmakerGender}`);
                        
                        // 立即更新用户列表
                        setTimeout(() => {
                            displayMatchmakerUserList();
                        }, 100);
                    });
                });
                
                // 初始化当前用户性别
                let currentUserGender = localStorage.getItem('currentUserGender') || 'male';
                
                // 恢复当前用户性别选择
                myGenderButtons.forEach(btn => {
                    if (btn.dataset.myGender === currentUserGender) {
                        btn.classList.add('active');
                    } else {
                        btn.classList.remove('active');
                    }
                });
                
                // 添加当前用户性别切换点击事件监听器
                myGenderButtons.forEach(btn => {
                    btn.addEventListener('click', function() {
                        // 移除所有当前用户性别按钮的active类
                        myGenderButtons.forEach(b => b.classList.remove('active'));
                        
                        // 添加当前按钮的active类
                        this.classList.add('active');
                        
                        // 更新当前用户性别
                        currentUserGender = this.dataset.myGender;
                        
                        // 保存到localStorage
                        localStorage.setItem('currentUserGender', currentUserGender);
                        
                        console.log(`当前用户性别已更新: ${currentUserGender}`);
                        
                        // 根据当前用户性别自动调整推荐性别（默认推荐异性）
                        if (selectedMatchmakerGender === 'all') {
                            const recommendedGender = currentUserGender === 'male' ? 'female' : 'male';
                            
                            // 更新性别筛选按钮状态
                            genderButtons.forEach(b => {
                                b.classList.remove('active');
                                if (b.dataset.gender === recommendedGender) {
                                    b.classList.add('active');
                                }
                            });
                            
                            // 更新选择的性别
                            selectedMatchmakerGender = recommendedGender;
                            localStorage.setItem('selectedMatchmakerGender', selectedMatchmakerGender);
                            
                            console.log(`根据当前用户性别自动推荐: ${selectedMatchmakerGender}`);
                            
                            // 更新用户列表
                            displayMatchmakerUserList();
                        }
                    });
                });
            }
            
            // 查看用户详情函数
            function viewUserDetail(userObj) {
                // 接收用户对象作为参数，避免变量作用域问题
                const user = typeof userObj === 'object' ? userObj : {
                    id: userObj,
                    name: '未知用户',
                    age: 0,
                    gender: 'male',
                    location: '未知城市',
                    photo: 'https://via.placeholder.com/150',
                    tags: [],
                    description: '暂无简介',
                    idealPartner: '暂无择偶要求',
                    details: {},
                    contact: {}
                };
                console.log('查看用户详情:', user);
                if (user) {
                    // 检查用户是否为VIP
                    const hasMatchmakerVip = false; // 默认禁用联系方式查看
                    const currentUser = JSON.parse(localStorage.getItem('currentUser'));
                    const userVipStatus = currentUser && currentUser.vip && currentUser.vip.matchmaker === true;
                    const isVip = hasMatchmakerVip || userVipStatus;
                    
                    // 创建联系方式部分的HTML
                    let contactHtml;
                    if (isVip && user.contact && (user.contact.wechat || user.contact.phone || user.contact.email)) {
                        contactHtml = `
                            <div class="matchmaker-contact-info">
                                ${user.contact.wechat ? `<p><strong>微信:</strong> ${user.contact.wechat} <button class="matchmaker-copy-btn" data-text="${user.contact.wechat}">复制</button></p>` : ''}
                                ${user.contact.phone ? `<p><strong>电话:</strong> ${user.contact.phone} <button class="matchmaker-copy-btn" data-text="${user.contact.phone}">复制</button></p>` : ''}
                                ${user.contact.email ? `<p><strong>邮箱:</strong> ${user.contact.email} <button class="matchmaker-copy-btn" data-text="${user.contact.email}">复制</button></p>` : ''}
                            </div>
                        `;
                    } else {
                        contactHtml = `
                            <div class="matchmaker-vip-restricted">
                                <p>开通VIP后可查看联系方式</p>
                                <button class="matchmaker-vip-btn">立即开通VIP</button>
                            </div>
                        `;
                    }
                    
                    // 创建更多照片部分的HTML
                    let morePhotosHtml;
                    if (isVip && user.details.morePhotos && user.details.morePhotos.length > 0) {
                        morePhotosHtml = `
                            <div class="matchmaker-more-photos-grid">
                                ${user.details.morePhotos.map(photoUrl => `
                                    <div class="matchmaker-photo-item">
                                        <img src="${photoUrl}" alt="${user.name}的照片">
                                    </div>
                                `).join('')}
                            </div>
                        `;
                    } else {
                        morePhotosHtml = `
                            <div class="matchmaker-vip-restricted">
                                <p>开通VIP后可查看更多照片</p>
                                <button class="matchmaker-vip-btn">立即开通VIP</button>
                            </div>
                        `;
                    }
                    
                    // 创建模态框
                    const modal = document.createElement('div');
                    modal.className = 'matchmaker-user-detail-modal';
                    modal.innerHTML = `
                        <div class="matchmaker-user-detail-content">
                            <div class="matchmaker-user-detail-header">
                                <h3>${user.name} ${user.age}岁</h3>
                                ${isVip ? '<span class="matchmaker-vip-badge">VIP用户</span>' : ''}
                                <span class="matchmaker-user-detail-close">×</span>
                            </div>
                            <div class="matchmaker-user-detail-body">
                                <div class="matchmaker-user-detail-main-photo">
                                    <div class="gender-avatar ${user.photo}">
                                        <i class="fas fa-${user.photo === 'female' ? 'female' : 'male'}"></i>
                                    </div>
                                </div>
                                <div class="matchmaker-user-detail-info">
                                    <div class="matchmaker-user-detail-basic">
                                        <p><strong>性别:</strong> ${user.gender === 'female' ? '女' : '男'}</p>
                                        <p><strong>城市:</strong> ${user.location}</p>
                                        <p><strong>身高:</strong> ${user.details.height || '未知'}cm</p>
                                        <p><strong>体重:</strong> ${user.details.weight || '未知'}kg</p>

                                        <p><strong>职业:</strong> ${user.details.occupation || '未知'}</p>
                                        <p><strong>收入:</strong> ${user.details.income || '未知'}</p>
                                        <p><strong>性格:</strong> ${user.details.character || '未知'}</p>
                                    </div>
                                    <div class="matchmaker-user-detail-tags">
                                        <strong>标签:</strong>
                                        ${user.tags && user.tags.length > 0 ? user.tags.map(tag => `<span class="tag">${tag}</span>`).join('') : '暂无标签'}
                                    </div>
                                    <div class="matchmaker-user-detail-description">
                                        <strong>个人简介:</strong>
                                        <p>${user.description || '暂无简介'}</p>
                                    </div>
                                    <div class="matchmaker-user-detail-ideal-partner">
                                        <strong>择偶要求:</strong>
                                        <p>${user.idealPartner || '暂无择偶要求'}</p>
                                    </div>
                                    <div class="matchmaker-user-detail-contact" id="matchmaker-contact-section">
                                        <strong>联系方式:</strong>
                                        ${contactHtml}
                                    </div>
                                    <div class="matchmaker-user-detail-more-photos" id="matchmaker-more-photos-section">
                                        <strong>更多照片:</strong>
                                        ${morePhotosHtml}
                                    </div>
                                </div>
                            </div>
                            <div class="matchmaker-user-detail-footer">
                                <button class="matchmaker-contact-btn">获取联系方式</button>
                                <button class="matchmaker-like-btn">喜欢</button>
                            </div>
                        </div>
                    `;
                    
                    // 检查是否已存在模态框，如果存在则移除
                    const existingModals = document.querySelectorAll('.matchmaker-user-detail-modal');
                    existingModals.forEach(existingModal => {
                        document.body.removeChild(existingModal);
                    });
                    
                    // 添加到页面
                    document.body.appendChild(modal);
                    
                    // 关闭模态框
                    modal.querySelector('.matchmaker-user-detail-close').addEventListener('click', function() {
                        document.body.removeChild(modal);
                    });
                    
                    // 点击模态框外部关闭
                    modal.addEventListener('click', function(e) {
                        if (e.target === modal) {
                            document.body.removeChild(modal);
                        }
                    });
                    
                    // 获取联系方式按钮
                    modal.querySelector('.matchmaker-contact-btn').addEventListener('click', function() {
                        viewUserContact(user.id);
                    });
                    
                    // VIP按钮点击事件
                    modal.querySelectorAll('.matchmaker-vip-btn').forEach(btn => {
                        btn.addEventListener('click', function() {
                            // 跳转到VIP购买页面
                            alert('跳转到VIP购买页面');
                        });
                    });
                    
                    // 复制按钮事件处理
                    modal.querySelectorAll('.matchmaker-copy-btn').forEach(btn => {
                        btn.addEventListener('click', function() {
                            const textToCopy = this.getAttribute('data-text');
                            if (textToCopy) {
                                navigator.clipboard.writeText(textToCopy).then(function() {
                                    const originalText = btn.textContent;
                                    btn.textContent = '已复制!';
                                    btn.style.backgroundColor = '#4CAF50';
                                    setTimeout(function() {
                                        btn.textContent = originalText;
                                        btn.style.backgroundColor = '';
                                    }, 2000);
                                }).catch(function(err) {
                                    console.error('复制失败:', err);
                                    alert('复制失败，请手动复制');
                                });
                            }
                        });
                    });
                    
                    // 添加模态框样式
                    const style = document.createElement('style');
                    style.textContent = `
                        .matchmaker-user-detail-modal {
                            position: fixed;
                            top: 0;
                            left: 0;
                            width: 100%;
                            height: 100%;
                            background-color: rgba(0, 0, 0, 0.5);
                            display: flex;
                            justify-content: center;
                            align-items: center;
                            z-index: 1000;
                        }
                        .matchmaker-user-detail-content {
                            background-color: white;
                            border-radius: 10px;
                            width: 90%;
                            max-width: 800px;
                            max-height: 90vh;
                            overflow-y: auto;
                            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
                        }
                        .matchmaker-user-detail-header {
                            display: flex;
                            justify-content: space-between;
                            align-items: center;
                            padding: 20px;
                            border-bottom: 1px solid #f0f0f0;
                        }
                        .matchmaker-user-detail-header h3 {
                            margin: 0;
                            color: #5a6069;
                            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
                        }
                        .matchmaker-vip-badge {
                            background-color: rgba(255, 215, 0, 0.2);
                            color: #b8860b;
                            padding: 6px 12px;
                            border-radius: 12px;
                            font-size: 13px;
                            font-weight: 600;
                            margin-right: 15px;
                        }
                        .matchmaker-user-detail-close {
                            font-size: 30px;
                            cursor: pointer;
                            color: #adb5bd;
                            transition: color 0.2s ease;
                        }
                        .matchmaker-user-detail-close:hover {
                            color: #6c757d;
                        }
                        .matchmaker-user-detail-close:hover {
                            color: #333;
                        }
                        .matchmaker-user-detail-body {
                            padding: 20px;
                        }
                        .matchmaker-user-detail-main-photo {
                            width: 100%;
                            text-align: center;
                            margin-bottom: 20px;
                        }
                        .matchmaker-user-detail-main-photo img {
                            width: 200px;
                            height: 200px;
                            border-radius: 10px;
                            object-fit: cover;
                            border: 3px solid #f0f0f0;
                        }
                        .matchmaker-user-detail-info {
                            margin-top: 20px;
                        }
                        .matchmaker-user-detail-basic {
                            display: grid;
                            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
                            gap: 10px;
                            margin-bottom: 20px;
                        }
                        .matchmaker-user-detail-basic p {
                            margin: 5px 0;
                            color: #666;
                        }
                        .matchmaker-user-detail-tags {
                            margin-bottom: 20px;
                        }
                        .matchmaker-user-detail-tags .tag {
                            display: inline-block;
                            background-color: #f0f0f0;
                            padding: 5px 10px;
                            margin: 5px;
                            border-radius: 15px;
                            font-size: 14px;
                            color: #666;
                        }
                        .matchmaker-user-detail-description {
                            margin-bottom: 20px;
                            line-height: 1.6;
                            color: #666;
                        }
                        .matchmaker-user-detail-contact,
                        .matchmaker-user-detail-more-photos {
                            margin-bottom: 20px;
                        }
                        .matchmaker-vip-restricted {
                            background-color: #fff3cd;
                            padding: 15px;
                            border-radius: 5px;
                            text-align: center;
                            border: 1px solid #ffeaa7;
                        }
                        .matchmaker-vip-restricted p {
                            margin: 10px 0;
                            color: #856404;
                        }
                        .matchmaker-vip-btn {
                            background-color: #ff6b6b;
                            color: white;
                            border: none;
                            padding: 10px 20px;
                            border-radius: 5px;
                            cursor: pointer;
                            font-weight: bold;
                            transition: background-color 0.3s;
                        }
                        .matchmaker-vip-btn:hover {
                            background-color: #ee5253;
                        }
                        .matchmaker-contact-info {
                            background-color: #f8f9fa;
                            padding: 15px;
                            border-radius: 5px;
                            border: 1px solid #e9ecef;
                        }
                        .matchmaker-contact-info p {
                            margin: 10px 0;
                            display: flex;
                            align-items: center;
                            justify-content: space-between;
                            color: #495057;
                        }
                        .matchmaker-copy-btn {
                            background-color: #007bff;
                            color: white;
                            border: none;
                            padding: 5px 10px;
                            border-radius: 3px;
                            cursor: pointer;
                            font-size: 12px;
                            transition: background-color 0.3s;
                        }
                        .matchmaker-copy-btn:hover {
                            background-color: #0056b3;
                        }
                        .matchmaker-more-photos-grid {
                            display: grid;
                            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
                            gap: 10px;
                            margin-top: 10px;
                        }
                        .matchmaker-photo-item {
                            border-radius: 5px;
                            overflow: hidden;
                            border: 2px solid #e9ecef;
                            cursor: pointer;
                            transition: transform 0.3s, border-color 0.3s;
                        }
                        .matchmaker-photo-item:hover {
                            transform: scale(1.05);
                            border-color: #007bff;
                        }
                        .matchmaker-photo-item img {
                            width: 100%;
                            height: 150px;
                            object-fit: cover;
                        }
                        .matchmaker-user-detail-footer {
                            display: flex;
                            justify-content: space-around;
                            padding: 20px;
                            border-top: 1px solid #eee;
                        }
                        .matchmaker-contact-btn,
                        .matchmaker-like-btn {
                            padding: 12px 30px;
                            border: none;
                            border-radius: 5px;
                            cursor: pointer;
                            font-size: 16px;
                            font-weight: bold;
                            transition: background-color 0.3s;
                        }
                        .matchmaker-contact-btn {
                            background-color: #4CAF50;
                            color: white;
                        }
                        .matchmaker-contact-btn:hover {
                            background-color: #45a049;
                        }
                        .matchmaker-like-btn {
                            background-color: #2196F3;
                            color: white;
                        }
                        .matchmaker-like-btn:hover {
                            background-color: #0b7dda;
                        }
                    `;
                    document.head.appendChild(style);
                }
            }
            
            // 查看用户联系方式函数
            function viewUserContact(userId) {
                // 直接跳转到VIP服务付款页面
                // 首先确保当前在牵线服务页面
                switchSection('matchmakerSection');
                
                // 可以在这里添加一些逻辑，比如记录用户想要联系的用户ID
                localStorage.setItem('intendedContactUserId', userId);
                
                // 弹出一个提示，告知用户需要开通VIP才能查看联系方式
                alert('查看联系方式需要开通红娘牵线VIP服务，请在下方选择支付方式进行开通');
            }
            
            // 初始显示牵线用户列表
            displayMatchmakerUserList();
            
            // 城市选择器的VIP解锁逻辑
            const citySelector = document.getElementById('matchmakerCitySelector');
            if (citySelector) {
                citySelector.classList.remove('vip-restricted');
                // 生成城市选项
                const cityGrid = document.getElementById('matchmakerCityGrid');
                if (cityGrid) {
                    const cities = ['北京', '上海', '广州', '深圳', '杭州', '成都', '武汉', '西安'];
                    cityGrid.innerHTML = cities.map(city => `<div class="city-item">${city}</div>`).join('');
                    
                    // 添加城市选择事件
                    cityGrid.querySelectorAll('.city-item').forEach(item => {
                        item.addEventListener('click', function() {
                            alert(`已选择城市：${this.textContent}`);
                            selectedMatchmakerCity = this.textContent;
                        });
                    });
                }
            }
            
            // 已删除统计数据展示功能
        // 修正语法：多余的右大括号，直接删除即可
        
        // 创建用户卡片
        function createUserCard(userData) {
            const userCard = document.createElement('div');
            // 为不同性别的用户卡片添加特定类名
            const genderClass = userData.gender === 'male' ? 'user-card-male' : 'user-card-female';
            userCard.className = `matchmaker-user-card ${genderClass}`;
            
            // 添加性别图标
            const genderIcon = userData.gender === 'male' ? '<i class="fas fa-male gender-icon male-icon"></i>' : '<i class="fas fa-female gender-icon female-icon"></i>';
            
            userCard.innerHTML = `
                <div class="matchmaker-user-avatar">
                    <div class="gender-avatar ${userData.gender}">
                        <i class="fas fa-${userData.gender === 'female' ? 'female' : 'male'}"></i>
                    </div>
                    <div class="gender-badge">${genderIcon}</div>
                </div>
                <div class="matchmaker-user-name gradient-text">${userData.name}</div>
                <div class="matchmaker-user-info">
                    <span class="user-stat">${userData.age}岁</span>
                    <span class="user-stat gender-text">${genderIcon} ${userData.gender === 'male' ? '男' : '女'}</span>
                    <span class="user-stat gradient-text">${userData.location}</span>
                </div>
                <div class="matchmaker-user-info">
                    <span class="user-job highlight">${userData.job}</span>
                </div>
                <div class="matchmaker-user-tags">
                    ${userData.tags.map(tag => `<div class="matchmaker-user-tag gradient-bg">${tag}</div>`).join('')}
                </div>
                <div class="matchmaker-user-bio enhanced-paragraph">
                    ${userData.bio}
                </div>
            `;
            matchmakerContent.appendChild(userCard);
        }
        

        

        

        
        // 初始化城市折叠功能
        function initCityCollapse() {
            cityCollapseToggle.addEventListener('click', () => {
                cityCollapseToggle.classList.toggle('active');
                cityCollapseContent.classList.toggle('active');
                
                if (cityCollapseContent.classList.contains('active')) {
                    cityCollapseContent.style.maxHeight = cityCollapseContent.scrollHeight + 'px';
                } else {
                    cityCollapseContent.style.maxHeight = null;
                }
            });
        }
        
        // 初始化网站统计
        function initWebsiteStats() {
            // 更新访问统计
            websiteStats.totalVisits++;
            websiteStats.todayVisits++;
            
            // 更新在线用户数（模拟）
            websiteStats.onlineUsers = Math.floor(Math.random() * 50) + 10;
            
            // 计算支付数据
            const successOrders = orders.filter(order => order.status === 'paid');
            const failedOrders = orders.filter(order => order.status === 'failed');
            
            websiteStats.successPayments = successOrders.reduce((total, order) => total + order.amount, 0);
            websiteStats.failedPayments = failedOrders.length;
            
            // 更新热门城市
            if (selectedProvince && selectedCity) {
                const cityKey = `${selectedProvince}-${selectedCity}`;
                if (!websiteStats.popularCities[cityKey]) {
                    websiteStats.popularCities[cityKey] = 0;
                }
                websiteStats.popularCities[cityKey]++;
            }
            
            // 保存统计数据
            localStorage.setItem('websiteStats', JSON.stringify(websiteStats));
        }
        
        // 用户头像点击跳转到"我的"页面
        function initUserAvatarClick() {
            userAvatar.addEventListener('click', () => {
                switchSection('profileSection');
            });
        }
        
        // 初始化登录类型切换
        function initLoginTypeTabs() {
            loginTypeTabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    const loginType = tab.getAttribute('data-type');
                    
                    // 更新标签页状态
                    loginTypeTabs.forEach(t => t.classList.remove('active'));
                    tab.classList.add('active');
                    
                    // 更新登录表单显示
                    if (loginType === 'user') {
                        userLoginForm.classList.remove('hidden');
                    }
                });
            });
        }
        
        // 初始化订单查询功能
        function initOrderSearch() {
            orderSearchBtn.addEventListener('click', searchOrder);
            orderSearchInput.addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    searchOrder();
                }
            });
        }
        
        // 查询订单
        function searchOrder() {
            const orderId = orderSearchInput.value.trim();
            if (!orderId) {
                alert('请输入订单号');
                return;
            }
            
            // 在本地订单中查找
            const foundOrder = orders.find(order => order.id === orderId);
            
            if (foundOrder) {
                // 显示订单详情
                orderDetails.innerHTML = `
                    <div class="order-detail-item">
                        <div class="order-detail-label">订单号</div>
                        <div class="order-detail-value">${foundOrder.id}</div>
                    </div>
                    <div class="order-detail-item">
                        <div class="order-detail-label">商品名称</div>
                        <div class="order-detail-value">${foundOrder.province} - ${foundOrder.city} 交友群</div>
                    </div>
                    <div class="order-detail-item">
                        <div class="order-detail-label">订单金额</div>
                        <div class="order-detail-value">¥${foundOrder.amount}</div>
                    </div>
                    <div class="order-detail-item">
                        <div class="order-detail-label">订单状态</div>
                        <div class="order-detail-value">${foundOrder.status === 'paid' ? '已支付' : '已退款'}</div>
                    </div>
                    <div class="order-detail-item">
                        <div class="order-detail-label">下单时间</div>
                        <div class="order-detail-value">${foundOrder.time}</div>
                    </div>
                `;
                orderDetails.classList.add('active');
            } else {
                // 未找到订单
                orderDetails.innerHTML = `
                    <div class="no-order-found">
                        <i class="fas fa-search"></i>
                        <p>未找到相关订单</p>
                        <p style="font-size: 0.9rem; margin-top: 10px;">请检查订单号是否正确</p>
                    </div>
                `;
                orderDetails.classList.add('active');
            }
        }
        
        // 事件监听
        alipayBtn.addEventListener('click', submitPayment);
        wxpayBtn.addEventListener('click', submitPayment);
        retryPayBtn.addEventListener('click', submitPayment);
        
        // 红娘牵线支付按钮事件
        matchmakerAlipayBtn.addEventListener('click', submitMatchmakerPayment);
        matchmakerWxpayBtn.addEventListener('click', submitMatchmakerPayment);
        
        // 移除了VIP按钮相关代码
        
        // 移除了VIP按钮的事件监听
        
        closeFeatureInfoModalBtn.addEventListener('click', () => {
            featureInfoModal.classList.add('hidden');
        });
        
        orderBtn.addEventListener('click', () => {
            switchSection('orderSection');
            initOrderList();
        });
        
        backBtn.addEventListener('click', () => {
            switchSection('main');
        });
        
        chatBackBtn.addEventListener('click', () => {
            switchSection('main');
        });
        
        userDetailBackBtn.addEventListener('click', () => {
            switchSection('matchmakerSection');
        });
        
        closeFailedModalBtn.addEventListener('click', () => {
            failedModal.classList.add('hidden');
        });
        
        closeSuccessModalBtn.addEventListener('click', () => {
            successModal.classList.add('hidden');
        });
        
        // 联系客服按钮事件
        contactCustomerBtn.addEventListener('click', () => {
            successModal.classList.add('hidden');
            // 打开客服聊天窗口
            customerServiceChat.classList.remove('hidden');
        });
        
        contactCustomerBtn2.addEventListener('click', () => {
            failedModal.classList.add('hidden');
            // 打开客服聊天窗口
            customerServiceChat.classList.remove('hidden');
        });
        
        // 顶部用户信息点击事件 - 跳转到我的页面
        userAvatar.addEventListener('click', () => {
            switchSection('profileSection');
        });
        
        headerUserName.addEventListener('click', () => {
            switchSection('profileSection');
        });
        
        // 消息提醒功能
        notificationIcon.addEventListener('click', () => {
            // 显示客服消息提醒
            if (currentUser) {
                // 打开客服聊天窗口
                customerServiceChat.classList.remove('hidden');
                
                // 如果有未读消息，显示提醒
                const unreadMessages = getUnreadMessages();
                if (unreadMessages > 0) {
                    showMessageNotification('您有' + unreadMessages + '条未读客服消息');
                }
            } else {
                alert('请先登录后再查看消息');
                switchSection('profileSection');
            }
        });
        
        // 查看聊天记录按钮
        viewChatBtn.addEventListener('click', () => {
            if (selectedProvince && selectedCity) {
                // 检查用户是否为VIP
                const isVip = currentUser && currentUser.vip && currentUser.vip.group === true;
                
                if (!isVip) {
                    // 非VIP用户，提示开通VIP
                    const confirmOpenVip = confirm('开通VIP即可查看完整群聊记录，是否立即开通？');
                    if (confirmOpenVip) {
                        openPaymentModal('group');
                    } else {
                        // 用户取消开通，仍然显示群聊记录（但只显示预览）
                        showChatRecords(selectedProvince, selectedCity);
                    }
                } else {
                    // VIP用户，直接显示完整群聊记录
                    showChatRecords(selectedProvince, selectedCity);
                }
            }
        });
        
        // 支付方式选择
        paymentMethods.forEach(method => {
            method.addEventListener('click', () => {
                // 移除其他支付方式的active状态
                paymentMethods.forEach(m => {
                    m.classList.remove('active');
                });
                // 设置当前支付方式为active
                method.classList.add('active');
                
                // 更新选中的支付方式
                selectedPaymentMethod = method.getAttribute('data-method');
                
                // 显示对应的支付表单
                if (selectedPaymentMethod === 'alipay') {
                    alipayForm.classList.add('active');
                    wxpayForm.classList.remove('active');
                } else {
                    alipayForm.classList.remove('active');
                    wxpayForm.classList.add('active');
                }
            });
        });
        
        // 红娘牵线支付方式选择
        matchmakerPaymentMethods.forEach(method => {
            method.addEventListener('click', () => {
                // 移除其他支付方式的active状态
                matchmakerPaymentMethods.forEach(m => {
                    m.classList.remove('active');
                });
                // 设置当前支付方式为active
                method.classList.add('active');
                
                // 更新选中的支付方式
                selectedMatchmakerPaymentMethod = method.getAttribute('data-method');
                
                // 显示对应的支付表单
                if (selectedMatchmakerPaymentMethod === 'alipay') {
                    matchmakerAlipayForm.classList.add('active');
                    matchmakerWxpayForm.classList.remove('active');
                } else {
                    matchmakerAlipayForm.classList.remove('active');
                    matchmakerWxpayForm.classList.add('active');
                }
            });
        });
        
        // 导航点击事件
        navItems.forEach(item => {
            item.addEventListener('click', () => {
                const target = item.getAttribute('data-target');
                
                // 牵线服务需要登录检查
                if (target === 'matchmakerSection' && !currentUser) {
                    alert('请先登录后再使用红娘牵线功能');
                    switchSection('profileSection');
                    return;
                }
                
                switchSection(target);
                
                if (target === 'orderSection') {
                    initOrderList();
                } else if (target === 'matchmakerSection') {
                    initMatchmaker();
                    initMatchmakerCitySelector();
                } else if (target === 'feedbackSection') {
                    initFeedbackCenter();
                }
            });
        });
        
        // 用户相关事件监听
        editProfileBtn.addEventListener('click', showEditProfileForm);
        logoutBtn.addEventListener('click', logoutUser);
        
        // 注册相关事件
        registerSubmitBtn.addEventListener('click', registerUser);
        registerCancelBtn.addEventListener('click', () => {
            registerContent.classList.add('hidden');
            loginContent.classList.remove('hidden');
        });
        showLoginBtn.addEventListener('click', () => {
            registerContent.classList.add('hidden');
            loginContent.classList.remove('hidden');
        });
        
        // 登录相关事件
        loginSubmitBtn.addEventListener('click', loginUser);
        loginCancelBtn.addEventListener('click', () => {
            loginContent.classList.add('hidden');
            registerContent.classList.remove('hidden');
        });
        showRegisterBtn.addEventListener('click', () => {
            loginContent.classList.add('hidden');
            registerContent.classList.remove('hidden');
        });
        
        // 编辑资料相关事件
        editSubmitBtn.addEventListener('click', editUserProfile);
        editCancelBtn.addEventListener('click', () => {
            editProfileContent.classList.add('hidden');
            profileContent.classList.remove('hidden');
        });
        
        // 性别选择
        genderOptions.forEach(option => {
            option.addEventListener('click', () => {
                // 移除其他选项的active状态
                option.parentNode.querySelectorAll('.gender-option').forEach(item => {
                    item.classList.remove('active');
                });
                // 设置当前选项为active
                option.classList.add('active');
            });
        });
        
        // 头像上传
        avatarUploadBtn.addEventListener('click', () => {
            avatarInput.click();
        });
        
        avatarInput.addEventListener('change', function() {
            if (this.files && this.files[0]) {
                const reader = new FileReader();
                
                reader.onload = function(e) {
                    avatarPreview.innerHTML = '';
                    const img = document.createElement('img');
                    img.src = e.target.result;
                    avatarPreview.appendChild(img);
                }
                
                reader.readAsDataURL(this.files[0]);
            }
        });
        
        editAvatarUploadBtn.addEventListener('click', () => {
            editAvatarInput.click();
        });
        
        editAvatarInput.addEventListener('change', function() {
            if (this.files && this.files[0]) {
                const reader = new FileReader();
                
                reader.onload = function(e) {
                    editAvatarPreview.innerHTML = '';
                    const img = document.createElement('img');
                    img.src = e.target.result;
                    editAvatarPreview.appendChild(img);
                }
                
                reader.readAsDataURL(this.files[0]);
            }
        });
        
        // 反馈中心相关事件监听
        // 照片上传
        const photoUploadInput = document.getElementById('photoInput');
        if (photoUploadInput) {
            photoUploadInput.addEventListener('change', handlePhotoUpload);
        }
        
        // 点击照片上传区域触发文件选择
        const photoUploadArea = document.getElementById('photoUploadArea');
        if (photoUploadArea) {
            photoUploadArea.addEventListener('click', function() {
                document.getElementById('photoInput').click();
            });
        }
        
        // 提交反馈按钮
        const submitFeedbackBtn = document.getElementById('submitFeedbackBtn');
        if (submitFeedbackBtn) {
            submitFeedbackBtn.addEventListener('click', submitFeedback);
        }
        
        // 反馈页面导航切换 - 已禁用群聊和牵线反馈跳转功能
        const feedbackPageTabs = document.querySelectorAll('.feedback-page-tab');
        feedbackPageTabs.forEach(tab => {
            tab.addEventListener('click', () => {
                // 不再切换到独立的反馈页面
                return false;
            });
        });
        
        // 反馈模式切换
        const groupModeBtn = document.getElementById('groupMode');
        const matchmakerModeBtn = document.getElementById('matchmakerMode');
        
        if (groupModeBtn) {
            groupModeBtn.addEventListener('click', () => switchFeedbackMode('group'));
        }
        
        if (matchmakerModeBtn) {
            matchmakerModeBtn.addEventListener('click', () => switchFeedbackMode('matchmaker'));
        }
        
        // 反馈中心登录按钮
        const feedbackLoginBtn = document.getElementById('feedbackLoginBtn');
        if (feedbackLoginBtn) {
            feedbackLoginBtn.addEventListener('click', () => {
                switchSection('profileSection');
            });
        }
        
        // 红娘牵线登录按钮
        const matchmakerLoginBtn = document.getElementById('matchmakerLoginBtn');
        if (matchmakerLoginBtn) {
            matchmakerLoginBtn.addEventListener('click', () => {
                switchSection('profileSection');
            });
        }
        
        // 开通VIP按钮
        // 已在下方统一声明 openVipBtn，此处移除重复声明

        if (openVipBtn) {
            openVipBtn.addEventListener('click', () => {
                if (!currentUser) {
                    alert('请先登录后再开通VIP服务');
                    switchSection('profileSection');
                    return;
                }
                // 跳转到VIP支付页面
                switchSection('matchmakerSection');
            });
        }
        
        // 开通群聊VIP按钮
        const openGroupVipBtn = document.getElementById('openGroupVipBtn');
        if (openGroupVipBtn) {
            openGroupVipBtn.addEventListener('click', () => {
                if (!currentUser) {
                    alert('请先登录后再开通VIP服务');
                    switchSection('profileSection');
                    return;
                }
                // 跳转到VIP支付页面
                switchSection('matchmakerSection');
            });
        }
        
        // 开通红娘牵线VIP按钮
        const openMatchmakerVipBtn = document.getElementById('openMatchmakerVipBtn');
        if (openMatchmakerVipBtn) {
            openMatchmakerVipBtn.addEventListener('click', () => {
                if (!currentUser) {
                    alert('请先登录后再开通VIP服务');
                    switchSection('profileSection');
                    return;
                }
                // 跳转到VIP支付页面
                switchSection('matchmakerSection');
            });
        }
        
        // 反馈中心功能类
        class FeedbackCenter {
            constructor() {
                this.currentMode = 'group'; // 默认群聊模式
                this.feedbackList = [];
                this.init();
            }
            
            init() {
                this.loadFeedbackData();
                this.bindEvents();
                this.updateFeedbackDisplay();
            }
            
            // 加载反馈数据
            loadFeedbackData() {
                const savedData = localStorage.getItem('feedbackData');
                if (savedData) {
                    this.feedbackList = JSON.parse(savedData);
                } else {
                    // 初始化示例数据
                    this.feedbackList = [
                        {
                            id: 1,
                            type: 'group',
                            title: '第一次参加群聊活动',
                            content: '活动氛围很好，认识了很多新朋友',
                            image: '',
                            timestamp: new Date().toLocaleString(),
                            user: '匿名用户'
                        },
                        {
                            id: 2,
                            type: 'matchmaker',
                            title: '牵线服务体验',
                            content: '红娘很专业，匹配很精准',
                            image: '',
                            timestamp: new Date().toLocaleString(),
                            user: '匿名用户'
                        }
                    ];
                    this.saveFeedbackData();
                }
            }
            
            // 保存反馈数据
            saveFeedbackData() {
                localStorage.setItem('feedbackData', JSON.stringify(this.feedbackList));
            }
            
            // 绑定事件
            bindEvents() {
                // 反馈模式切换
                const groupModeBtn = document.getElementById('groupMode');
                const matchmakerModeBtn = document.getElementById('matchmakerMode');
                
                if (groupModeBtn) {
                    groupModeBtn.addEventListener('click', () => this.switchMode('group'));
                }
                
                if (matchmakerModeBtn) {
                    matchmakerModeBtn.addEventListener('click', () => this.switchMode('matchmaker'));
                }
                
                // 照片上传
                const photoUploadInput = document.getElementById('photoUpload');
                if (photoUploadInput) {
                    photoUploadInput.addEventListener('change', (e) => this.handlePhotoUpload(e));
                }
                
                // 提交反馈
                const submitFeedbackBtn = document.getElementById('submitFeedbackBtn');
                if (submitFeedbackBtn) {
                    submitFeedbackBtn.addEventListener('click', () => this.submitFeedback());
                }
                
                // 查看反馈详情
                this.bindFeedbackDetailEvents();
            }
            
            // 切换反馈模式
            switchMode(mode) {
                this.currentMode = mode;
                
                // 更新按钮状态
                const groupModeBtn = document.getElementById('groupMode');
                const matchmakerModeBtn = document.getElementById('matchmakerMode');
                
                if (groupModeBtn && matchmakerModeBtn) {
                    if (mode === 'group') {
                        groupModeBtn.classList.add('active');
                        matchmakerModeBtn.classList.remove('active');
                    } else {
                        groupModeBtn.classList.remove('active');
                        matchmakerModeBtn.classList.add('active');
                    }
                }
                
                this.updateFeedbackDisplay();
            }
            
            // 更新反馈显示
            updateFeedbackDisplay() {
                // 显示对应模式的反馈
                const groupFeedbackSection = document.getElementById('groupFeedbackSection');
                const matchmakerFeedbackSection = document.getElementById('matchmakerFeedbackSection');
                
                if (groupFeedbackSection && matchmakerFeedbackSection) {
                    if (this.currentMode === 'group') {
                        groupFeedbackSection.style.display = 'block';
                        matchmakerFeedbackSection.style.display = 'none';
                    } else {
                        groupFeedbackSection.style.display = 'none';
                        matchmakerFeedbackSection.style.display = 'block';
                    }
                }
                
                // 更新反馈列表
                this.updateFeedbackList();
            }
            
            // 更新反馈列表
            updateFeedbackList() {
                const feedbackListElement = document.getElementById('feedbackList');
                if (!feedbackListElement) return;
                
                // 过滤当前模式的反馈
                const currentModeFeedback = this.feedbackList.filter(feedback => 
                    feedback.type === this.currentMode
                );
                
                // 只显示前5条
                const displayFeedback = currentModeFeedback.slice(0, 5);
                
                feedbackListElement.innerHTML = '';
                
                displayFeedback.forEach(feedback => {
                    const feedbackItem = document.createElement('div');
                    feedbackItem.className = 'feedback-item';
                    feedbackItem.setAttribute('data-id', feedback.id);
                    
                    feedbackItem.innerHTML = `
                        <div class="feedback-header">
                            <div class="feedback-title">${feedback.title}</div>
                            <div class="feedback-time">${feedback.timestamp}</div>
                        </div>
                        <div class="feedback-content">${feedback.content}</div>
                        ${feedback.image ? `<div class="feedback-image"><img src="${feedback.image}" alt="反馈图片"></div>` : ''}
                        <div class="feedback-user">发布者: ${feedback.user}</div>
                    `;
                    
                    feedbackListElement.appendChild(feedbackItem);
                });
                
                // 显示VIP限制提示
                this.showVipRestriction(currentModeFeedback.length > 5);
                
                // 重新绑定详情查看事件
                this.bindFeedbackDetailEvents();
            }
            
            // 显示VIP限制提示
            showVipRestriction(hasMore) {
                const vipRestriction = document.getElementById('vipRestriction');
                if (!vipRestriction) return;
                
                if (hasMore) {
                    vipRestriction.style.display = 'block';
                    vipRestriction.innerHTML = `
                        <div class="vip-restriction-content">
                            <i class="fas fa-crown"></i>
                            <p>查看更多反馈需要开通VIP服务</p>
                            <button id="openGroupVipBtn" class="vip-button">开通VIP</button>
                        </div>
                    `;
                    
                    // 重新绑定VIP开通按钮事件
                    const openVipBtn = document.getElementById('openGroupVipBtn');
                    if (openVipBtn) {
                        openVipBtn.addEventListener('click', () => {
                            if (!currentUser) {
                                alert('请先登录后再开通VIP服务');
                                switchSection('profileSection');
                                return;
                            }
                            // 跳转到VIP支付页面
                            switchSection('matchmakerSection');
                        });
                    }
                } else {
                    vipRestriction.style.display = 'none';
                }
            }
            
            // 绑定反馈详情查看事件
            bindFeedbackDetailEvents() {
                const feedbackItems = document.querySelectorAll('.feedback-item');
                feedbackItems.forEach(item => {
                    item.addEventListener('click', () => {
                        const feedbackId = parseInt(item.getAttribute('data-id'));
                        this.showFeedbackDetail(feedbackId);
                    });
                });
            }
            
            // 显示反馈详情
            showFeedbackDetail(feedbackId) {
                const feedback = this.feedbackList.find(f => f.id === feedbackId);
                if (!feedback) return;
                
                // 创建详情模态框
                const detailModal = document.createElement('div');
                detailModal.className = 'feedback-detail-modal';
                detailModal.innerHTML = `
                    <div class="feedback-detail-content">
                        <div class="feedback-detail-header">
                            <h3>${feedback.title}</h3>
                            <button class="close-detail-btn">&times;</button>
                        </div>
                        <div class="feedback-detail-body">
                            <div class="feedback-detail-info">
                                <div class="feedback-detail-user">发布者: ${feedback.user}</div>
                                <div class="feedback-detail-time">时间: ${feedback.timestamp}</div>
                            </div>
                            <div class="feedback-detail-content-text">${feedback.content}</div>
                            ${feedback.image ? `<div class="feedback-detail-image"><img src="${feedback.image}" alt="反馈图片"></div>` : ''}
                        </div>
                    </div>
                `;
                
                document.body.appendChild(detailModal);
                
                // 绑定关闭事件
                const closeBtn = detailModal.querySelector('.close-detail-btn');
                closeBtn.addEventListener('click', () => {
                    document.body.removeChild(detailModal);
                });
                
                // 点击模态框外部关闭
                detailModal.addEventListener('click', (e) => {
                    if (e.target === detailModal) {
                        document.body.removeChild(detailModal);
                    }
                });
            }
            
            // 处理照片上传
            handlePhotoUpload(event) {
                const file = event.target.files[0];
                if (!file) return;
                
                // 检查文件类型
                if (!file.type.startsWith('image/')) {
                    alert('请上传图片文件');
                    return;
                }
                
                // 检查文件大小（限制5MB）
                if (file.size > 5 * 1024 * 1024) {
                    alert('图片大小不能超过5MB');
                    return;
                }
                
                const reader = new FileReader();
                reader.onload = (e) => {
                    // 显示预览
                    const photoPreview = document.getElementById('photoPreview');
                    if (photoPreview) {
                        photoPreview.innerHTML = `<img src="${e.target.result}" alt="预览图片">`;
                        photoPreview.style.display = 'block';
                    }
                };
                reader.readAsDataURL(file);
            }
            
            // 提交反馈
            submitFeedback() {
                // 检查登录状态
                if (!currentUser) {
                    alert('请先登录后再提交反馈');
                    switchSection('profileSection');
                    return;
                }
                
                // 检查VIP状态
                if (!this.checkVipStatus()) {
                    const vipTypeName = this.currentMode === 'group' ? '群聊VIP服务' : '红娘牵线VIP服务';
                    const confirmMsg = `提交反馈需要开通${vipTypeName}。是否立即开通？`;
                    
                    if (confirm(confirmMsg)) {
                        // 跳转到对应的VIP开通页面
                        if (this.currentMode === 'group') {
                            this.openGroupVipPage();
                        } else {
                            this.openMatchmakerVipPage();
                        }
                    }
                    return;
                }
                
                const titleInput = document.getElementById('feedbackTitle');
                const contentInput = document.getElementById('feedbackContent');
                const photoPreview = document.getElementById('photoPreview');
                
                const title = titleInput ? titleInput.value.trim() : '';
                const content = contentInput ? contentInput.value.trim() : '';
                
                // 验证输入
                if (!title) {
                    alert('请输入反馈标题');
                    return;
                }
                
                if (!content) {
                    alert('请输入反馈内容');
                    return;
                }
                
                // 获取图片数据
                let imageData = '';
                if (photoPreview && photoPreview.style.display !== 'none') {
                    const img = photoPreview.querySelector('img');
                    if (img) {
                        imageData = img.src;
                    }
                }
                
                // 创建反馈对象
                const newFeedback = {
                    id: Date.now(),
                    type: this.currentMode,
                    title: title,
                    content: content,
                    image: imageData,
                    timestamp: new Date().toLocaleString(),
                    user: currentUser.username || '匿名用户'
                };
                
                // 添加到列表
                this.feedbackList.unshift(newFeedback);
                this.saveFeedbackData();
                
                // 清空表单
                if (titleInput) titleInput.value = '';
                if (contentInput) contentInput.value = '';
                if (photoPreview) {
                    photoPreview.innerHTML = '';
                    photoPreview.style.display = 'none';
                }
                
                // 重置文件输入
                const photoUploadInput = document.getElementById('photoUpload');
                if (photoUploadInput) {
                    photoUploadInput.value = '';
                }
                
                // 更新显示
                this.updateFeedbackList();
                
                alert('反馈提交成功！');
            }
            
            // 检查VIP状态
            checkVipStatus() {
                if (!currentUser) return false;
                
                // 使用VIP服务管理器检查VIP状态
                if (this.currentMode === 'group') {
                    return vipServiceManager.checkUserVipStatus(currentUser, 'group');
                } else {
                    return vipServiceManager.checkUserVipStatus(currentUser, 'matchmaker');
                }
            }
            
            // 打开群聊VIP页面
            openGroupVipPage() {
                // 切换到群聊VIP开通页面
                switchSection('groupSection');
                
                // 显示VIP开通提示
                setTimeout(() => {
                    alert('请开通群聊VIP服务以提交反馈');
                }, 500);
            }
            
            // 打开红娘牵线VIP页面
            openMatchmakerVipPage() {
                // 切换到红娘牵线VIP开通页面
                switchSection('matchmakerSection');
                
                // 显示VIP开通提示
                setTimeout(() => {
                    alert('请开通红娘牵线VIP服务以提交反馈');
                }, 500);
            }
        }
        
        // 已合并到第一个initFeedbackCenter函数中
        

        
        // 初始化手机号验证功能
        function initPhoneValidation() {
            const registerPhoneInput = document.getElementById('registerPhone');
            
            if (registerPhoneInput) {
                // 实时验证手机号格式 - 优化：允许用户随时切换输入
                registerPhoneInput.addEventListener('input', function() {
                    const phone = this.value.trim();
                    const phoneRegex = /^1[3-9]\d{9}$/;
                    
                    // 移除之前的验证样式
                    this.classList.remove('valid', 'invalid');
                    
                    if (phone === '') {
                        // 空值时不显示验证状态，允许用户切换其他输入
                        return;
                    }
                    
                    // 只有当输入完整11位手机号时才验证格式
                    if (phone.length === 11) {
                        if (phoneRegex.test(phone)) {
                            this.classList.add('valid');
                        } else {
                            this.classList.add('invalid');
                        }
                    }
                    // 输入少于11位时不显示验证状态，允许用户继续输入或切换
                });
                
                // 失去焦点时显示详细提示 - 优化：只在输入完整手机号时验证
                registerPhoneInput.addEventListener('blur', function() {
                    const phone = this.value.trim();
                    const phoneRegex = /^1[3-9]\d{9}$/;
                    
                    // 只有当输入完整11位手机号时才验证格式
                    if (phone.length === 11 && !phoneRegex.test(phone)) {
                        // 显示错误提示
                        this.setCustomValidity('请输入有效的中国大陆手机号码（11位数字，以1开头）');
                        this.reportValidity();
                    } else {
                        this.setCustomValidity('');
                    }
                });
                
                // 获得焦点时清除提示
                registerPhoneInput.addEventListener('focus', function() {
                    this.setCustomValidity('');
                });
            }
        }
        
        // VIP服务管理模块
        class VipServiceManager {
            constructor() {
                this.vipTypes = {
                    group: {
                        name: '微信群聊VIP服务',
                        price: 39.99,
                        features: [
                            '无限查看群聊反馈',
                            '参与群聊讨论',
                            '优先匹配群聊成员',
                            '专属群聊活动'
                        ]
                    },
                    matchmaker: {
                        name: '红娘牵线VIP服务',
                        price: 199.99,
                        features: [
                            '无限查看牵线反馈',
                            '精准城市匹配',
                            '一对一红娘服务',
                            '优先推荐优质用户'
                        ]
                    },
                    private: {
                        name: '私密交友特权',
                        price: 39.99,
                        features: [
                            '开通上传反馈功能',
                            '加入私密交友圈',
                            '体验深夜陪伴',
                            '私密认证保护'
                        ]
                    }
                };
            }
            
            // 检查用户VIP状态
            checkUserVipStatus(user, vipType) {
                if (!user || !user.vip) return false;
                
                if (vipType === 'group') {
                    return user.vip.group === true;
                } else if (vipType === 'matchmaker') {
                    return user.vip.matchmaker === true;
                } else if (vipType === 'private') {
                    return user.vip.private === true;
                }
                
                return false;
            }
            
            // 开通VIP服务
            activateVipService(user, vipType) {
                if (!user) return false;
                
                // 确保vip对象存在
                if (!user.vip) {
                    user.vip = {};
                }
                
                if (vipType === 'group') {
                    user.vip.group = true;
                } else if (vipType === 'matchmaker') {
                    user.vip.matchmaker = true;
                } else if (vipType === 'private') {
                    user.vip.private = true;
                }
                
                // 更新用户数据
                this.updateUserData(user);
                
                return true;
            }
            
            // 更新用户数据
            updateUserData(user) {
                const users = JSON.parse(localStorage.getItem('users') || '[]');
                const userIndex = users.findIndex(u => u.username === user.username);
                
                if (userIndex !== -1) {
                    users[userIndex] = user;
                    localStorage.setItem('users', JSON.stringify(users));
                }
                
                // 更新当前用户
                if (currentUser && currentUser.username === user.username) {
                    currentUser = user;
                    localStorage.setItem('currentUser', JSON.stringify(user));
                }
            }
            
            // 获取VIP服务信息
            getVipServiceInfo(vipType) {
                return this.vipTypes[vipType] || null;
            }
            
            // 显示VIP开通提示
            showVipPrompt(vipType) {
                const serviceInfo = this.getVipServiceInfo(vipType);
                if (!serviceInfo) return false;
                
                const confirmMessage = `开通${serviceInfo.name}（¥${serviceInfo.price}）\n\n服务包含：\n${serviceInfo.features.join('\n')}\n\n是否确认开通？`;
                
                return confirm(confirmMessage);
            }
            
            // 验证VIP访问权限
            validateVipAccess(user, vipType, featureName) {
                if (!this.checkUserVipStatus(user, vipType)) {
                    const serviceInfo = this.getVipServiceInfo(vipType);
                    alert(`使用${featureName}功能需要开通${serviceInfo.name}`);
                    return false;
                }
                
                return true;
            }
        }
        
        // 初始化VIP服务管理器
        function initVipServiceManager() {
            if (typeof vipServiceManager === 'undefined') {
                window.vipServiceManager = new VipServiceManager();
            }
        }
        
        // 初始化牵线服务反馈页面

        

        
        // 初始化声明双击事件
        function initAgreementDoubleClick() {
            // 注册页面声明双击事件
            const registerAgreementCheckbox = document.getElementById('registerAgreementCheckbox');
            const registerAgreementContent = document.getElementById('registerAgreementContent');
            
            if (registerAgreementCheckbox && registerAgreementContent) {
                let clickCount = 0;
                let clickTimer = null;
                
                registerAgreementCheckbox.addEventListener('click', function(e) {
                    // 允许正常的复选框点击行为，不阻止默认行为
                    
                    clickCount++;
                    
                    if (clickCount === 1) {
                        // 第一次点击，设置定时器
                        clickTimer = setTimeout(() => {
                            clickCount = 0; // 重置计数
                        }, 300); // 300毫秒内没有第二次点击则重置
                    } else if (clickCount === 2) {
                        // 第二次点击，清除定时器
                        clearTimeout(clickTimer);
                        clickCount = 0;
                        
                        // 切换声明内容的显示/隐藏
                        if (registerAgreementContent.classList.contains('hidden')) {
                            registerAgreementContent.classList.remove('hidden');
                        } else {
                            registerAgreementContent.classList.add('hidden');
                        }
                    }
                });
            }
            
            // 登录页面声明双击事件
            const loginAgreementCheckbox = document.getElementById('loginAgreementCheckbox');
            const loginAgreementContent = document.getElementById('loginAgreementContent');
            
            if (loginAgreementCheckbox && loginAgreementContent) {
                let clickCount = 0;
                let clickTimer = null;
                
                loginAgreementCheckbox.addEventListener('click', function(e) {
                    // 允许正常的复选框点击行为，不阻止默认行为
                    
                    clickCount++;
                    
                    if (clickCount === 1) {
                        // 第一次点击，设置定时器
                        clickTimer = setTimeout(() => {
                            clickCount = 0; // 重置计数
                        }, 300); // 300毫秒内没有第二次点击则重置
                    } else if (clickCount === 2) {
                        // 第二次点击，清除定时器
                        clearTimeout(clickTimer);
                        clickCount = 0;
                        
                        // 切换声明内容的显示/隐藏
                        if (loginAgreementContent.classList.contains('hidden')) {
                            loginAgreementContent.classList.remove('hidden');
                        } else {
                            loginAgreementContent.classList.add('hidden');
                        }
                    }
                });
            }
            
            // 支付页面声明双击事件
            const paymentAgreementCheckbox = document.getElementById('paymentAgreementCheckbox');
            const paymentAgreementContent = document.getElementById('paymentAgreementContent');
            
            if (paymentAgreementCheckbox && paymentAgreementContent) {
                let clickCount = 0;
                let clickTimer = null;
                
                paymentAgreementCheckbox.addEventListener('click', function(e) {
                    // 允许正常的复选框点击行为，不阻止默认行为
                    
                    clickCount++;
                    
                    if (clickCount === 1) {
                        // 第一次点击，设置定时器
                        clickTimer = setTimeout(() => {
                            clickCount = 0; // 重置计数
                        }, 300); // 300毫秒内没有第二次点击则重置
                    } else if (clickCount === 2) {
                        // 第二次点击，清除定时器
                        clearTimeout(clickTimer);
                        clickCount = 0;
                        
                        // 切换声明内容的显示/隐藏
                        if (paymentAgreementContent.classList.contains('hidden')) {
                            paymentAgreementContent.classList.remove('hidden');
                        } else {
                            paymentAgreementContent.classList.add('hidden');
                        }
                    }
                });
            }
            
            // 牵线服务支付页面声明双击事件
            const matchmakerPaymentAgreementCheckbox = document.getElementById('matchmakerPaymentAgreementCheckbox');
            const matchmakerPaymentAgreementContent = document.getElementById('matchmakerPaymentAgreementContent');
            
            if (matchmakerPaymentAgreementCheckbox && matchmakerPaymentAgreementContent) {
                let clickCount = 0;
                let clickTimer = null;
                
                matchmakerPaymentAgreementCheckbox.addEventListener('click', function(e) {
                    // 允许正常的复选框点击行为，不阻止默认行为
                    
                    clickCount++;
                    
                    if (clickCount === 1) {
                        // 第一次点击，设置定时器
                        clickTimer = setTimeout(() => {
                            clickCount = 0; // 重置计数
                        }, 300); // 300毫秒内没有第二次点击则重置
                    } else if (clickCount === 2) {
                        // 第二次点击，清除定时器
                        clearTimeout(clickTimer);
                        clickCount = 0;
                        
                        // 切换声明内容的显示/隐藏
                        if (matchmakerPaymentAgreementContent.classList.contains('hidden')) {
                            matchmakerPaymentAgreementContent.classList.remove('hidden');
                        } else {
                            matchmakerPaymentAgreementContent.classList.add('hidden');
                        }
                    }
                });
            }
        }
        
        // 客服系统功能
        function initCustomerService() {
            const customerServiceBtn = document.getElementById('customerServiceBtn');
            const customerServiceChat = document.getElementById('customerServiceChat');
            const closeCustomerService = document.getElementById('closeCustomerService');
            const customerServiceInput = document.getElementById('customerServiceInput');
            const sendCustomerMessage = document.getElementById('sendCustomerMessage');
            const customerServiceMessages = document.getElementById('customerServiceMessages');
            
            if (!customerServiceBtn || !customerServiceChat) return;
            
            // 打开客服聊天窗口
            customerServiceBtn.addEventListener('click', () => {
                customerServiceChat.classList.remove('hidden');
                customerServiceInput.focus();
            });
            
            // 关闭客服聊天窗口
            closeCustomerService.addEventListener('click', () => {
                customerServiceChat.classList.add('hidden');
            });
            
            // 发送消息
            sendCustomerMessage.addEventListener('click', sendMessage);
            customerServiceInput.addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    sendMessage();
                }
            });
            
            function sendMessage() {
                const message = customerServiceInput.value.trim();
                if (!message) return;
                
                // 添加用户消息
                addMessage(message, 'user');
                customerServiceInput.value = '';
                
                // 发送消息到后端API
                sendMessageToAPI(message);
            }
            
            function sendMessageToAPI(message) {
                // 显示发送成功状态
                addMessage('✓ 消息已发送，客服正在为您服务...', 'system');
                
                // 模拟客服回复（延迟2-5秒）
                setTimeout(() => {
                    const smartResponses = [
                        '您好，很高兴为您服务！有什么可以帮助您的吗？',
                        '我理解您的问题，让我为您详细解答。',
                        '感谢您的咨询，我们的专业客服正在为您处理。',
                        '这个问题需要进一步了解，请稍等片刻。',
                        '我们已经收到您的反馈，会尽快为您提供解决方案。',
                        '建议您查看常见问题解答，可能对您有帮助。',
                        '感谢您的耐心等待，正在为您查询相关信息。',
                        '这个问题比较常见，让我为您详细说明处理流程。'
                    ];
                    
                    const smartResponse = smartResponses[Math.floor(Math.random() * smartResponses.length)];
                    addMessage(smartResponse, 'customer');
                    
                    // 30%概率添加QQ客服提示
                    if (Math.random() < 0.3) {
                        setTimeout(() => {
                            addMessage('💬 如果长时间没有回复，请添加专属客服QQ：1158980053', 'customer');
                        }, 1500);
                    }
                }, 2000 + Math.random() * 3000);
            }
            
            function addMessage(text, sender) {
                const messageDiv = document.createElement('div');
                messageDiv.className = `message ${sender}-message`;
                
                const now = new Date();
                const timeString = `${now.getHours().toString().padStart(2, '0')}:${now.getMinutes().toString().padStart(2, '0')}`;
                
                messageDiv.innerHTML = `
                    <div class="message-content">
                        <div class="message-text">${text}</div>
                        <div class="message-time">${timeString}</div>
                    </div>
                `;
                
                customerServiceMessages.appendChild(messageDiv);
                customerServiceMessages.scrollTop = customerServiceMessages.scrollHeight;
            }
            
            // 点击外部关闭聊天窗口
            document.addEventListener('click', (e) => {
                if (!customerServiceChat.contains(e.target) && 
                    !customerServiceBtn.contains(e.target) && 
                    !customerServiceChat.classList.contains('hidden')) {
                    customerServiceChat.classList.add('hidden');
                }
            });
        }
        
        // 初始化
        document.addEventListener('DOMContentLoaded', () => {
            initProvinceList();
            initOrderList();
            initUI();
            
            // 检查支付结果
            checkPaymentResult();
            checkMatchmakerPaymentResult();


            initCityCollapse();
            initWebsiteStats();
            initUserAvatarClick();
            initMatchmakerCitySelector();
            initLoginTypeTabs();
            initOrderSearch();
            initPhoneValidation();
            initVipServiceManager();
            // 移除自动初始化，反馈中心将在用户点击时初始化
            // initMatchmakerFeedbackPage();
            // initGroupFeedbackPage();
            initAgreementDoubleClick();
            initCustomerService();
        });
    </script>
    
    <!-- 私密约会体验 -->
    <div class="security-footer">
        <div class="security-footer-content">
            <h3><i class="fas fa-heart"></i> 深夜私密约会体验</h3>
            <div class="security-features">
                <div class="security-feature">
                    <i class="fas fa-user-secret"></i>
                    <div>
                        <h4>绝对私密空间</h4>
                        <p>全程匿名交流，让您无拘无束地释放真实自我</p>
                    </div>
                </div>
                <div class="security-feature">
                    <i class="fas fa-heartbeat"></i>
                    <div>
                        <h4>心动瞬间</h4>
                        <p>专业匹配算法，为您找到最契合的深夜伴侣</p>
                    </div>
                </div>
                <div class="security-feature">
                    <i class="fas fa-moon"></i>
                    <div>
                        <h4>深夜暧昧</h4>
                        <p>24小时在线陪伴，满足您的每一个深夜需求</p>
                    </div>
                </div>
                <div class="security-feature">
                    <i class="fas fa-hand-holding-heart"></i>
                    <div>
                        <h4>真实体验</h4>
                        <p>真人认证体系，确保每一次约会都真实可靠</p>
                    </div>
                </div>
            </div>
            <div class="legal-info">
                <p>© 2024 深夜私密约会 | 本平台仅提供交友服务，严禁任何违法违规行为</p>
            </div>
        </div>
    </div>
    
    <script>
        // 倒计时计时器功能
        function startCountdown() {
            const countdownElement = document.getElementById('countdown');
            if (!countdownElement) return;
            
            // 设置倒计时时间为24小时
            let seconds = 24 * 60 * 60;
            
            const timer = setInterval(() => {
                if (seconds <= 0) {
                    clearInterval(timer);
                    countdownElement.textContent = '活动已结束';
                    return;
                }
                
                seconds--;
                
                // 计算时分秒
                const hours = Math.floor(seconds / 3600);
                const minutes = Math.floor((seconds % 3600) / 60);
                const remainingSeconds = seconds % 60;
                
                // 格式化显示
                countdownElement.textContent = `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${remainingSeconds.toString().padStart(2, '0')}`;
            }, 1000);
        }
        
        // 页面加载完成后启动倒计时
        document.addEventListener('DOMContentLoaded', startCountdown);

        // 可折叠区块功能
        function toggleCollapse(header) {
            const content = header.nextElementSibling;
            const icon = header.querySelector('.collapse-icon');
            
            content.classList.toggle('show');
            icon.classList.toggle('rotate');
        }
        
        // 测试牵线功能的函数
        
        // 反馈展览功能
        function showFeedbackExhibition() {
            const modal = document.getElementById('feedbackExhibitionModal');
            const grid = document.getElementById('feedbackExhibitionGrid');
            
            // 清空网格
            grid.innerHTML = '';
            
            // 用户反馈数据 - 全部改为男性用户，增加更多反馈以营造丰富感
            // 生成最近1-3天的日期
            const today = new Date();
            const formatDate = (date) => {
                const year = date.getFullYear();
                const month = String(date.getMonth() + 1).padStart(2, '0');
                const day = String(date.getDate()).padStart(2, '0');
                return `${year}-${month}-${day}`;
            };
            
            const userFeedbacks = [
                {                    id: 1,                    name: '李先生',                    avatar: 'https://ui-avatars.com/api/?name=李先生&background=random',                    location: '北京',                    date: formatDate(new Date(today.getTime() - Math.floor(Math.random() * 3) * 24 * 60 * 60 * 1000)),                    rating: 5,                    comment: '服务非常专业，体验超出预期！从咨询到完成，整个过程都很顺畅，工作人员态度也很好。',                    isVerified: true,                    image: 'https://s3.bmp.ovh/imgs/2025/11/14/573db0f35da7d6ee.jpg'                },
                {                    id: 2,                    name: '张先生',                    avatar: 'https://ui-avatars.com/api/?name=张先生&background=random',                    location: '上海',                    date: formatDate(new Date(today.getTime() - Math.floor(Math.random() * 3) * 24 * 60 * 60 * 1000)),                    rating: 4,                    comment: '整体不错，细节处理得很好！尤其是最后的效果让我非常满意，值得推荐。',                    isVerified: true,                    image: 'https://s3.bmp.ovh/imgs/2025/11/14/75b7d3342388866e.png'                },
                {                    id: 3,                    name: '王先生',                    avatar: 'https://ui-avatars.com/api/?name=王先生&background=random',                    location: '广州',                    date: formatDate(new Date(today.getTime() - Math.floor(Math.random() * 3) * 24 * 60 * 60 * 1000)),                    rating: 5,                    comment: '非常满意这次的服务！提供了很多专业建议，结果超出了我的期望，强烈推荐给大家！',                    isVerified: true,                    images: [                        'https://s3.bmp.ovh/imgs/2025/11/14/2876c21173df3c75.jpg',                        'https://s3.bmp.ovh/imgs/2025/11/14/16bc8514b2e33acf.jpg'                    ]                },
                {                    id: 4,                    name: '赵先生',                    avatar: 'https://ui-avatars.com/api/?name=赵先生&background=random',                    location: '深圳',                    date: formatDate(new Date(today.getTime() - Math.floor(Math.random() * 3) * 24 * 60 * 60 * 1000)),                    rating: 5,                    comment: '服务态度很好，工作效率也很高，非常满意！',                    isVerified: true,                    image: 'https://s3.bmp.ovh/imgs/2025/11/14/09615d0a87903164.png'                },
                {                    id: 5,                    name: '刘先生',                    avatar: 'https://ui-avatars.com/api/?name=刘先生&background=random',                    location: '杭州',                    date: formatDate(new Date(today.getTime() - Math.floor(Math.random() * 3) * 24 * 60 * 60 * 1000)),                    rating: 4,                    comment: '整体服务不错，值得信赖！',                    isVerified: true,                    image: 'https://s3.bmp.ovh/imgs/2025/11/14/3f50c9611cb43dc7.jpg'                },
                {                    id: 6,                    name: '陈先生',                    avatar: 'https://ui-avatars.com/api/?name=陈先生&background=random',                    location: '成都',                    date: formatDate(new Date(today.getTime() - Math.floor(Math.random() * 3) * 24 * 60 * 60 * 1000)),                    rating: 5,                    comment: '非常专业的团队，效果超出预期！',                    isVerified: true,                    image: 'https://s3.bmp.ovh/imgs/2025/11/14/71ce30d88b94dcad.jpg'                },
                {                    id: 7,                    name: '杨先生',                    avatar: 'https://ui-avatars.com/api/?name=杨先生&background=random',                    location: '武汉',                    date: formatDate(new Date(today.getTime() - Math.floor(Math.random() * 3) * 24 * 60 * 60 * 1000)),                    rating: 5,                    comment: '服务非常周到，团队专业可靠，强烈推荐！',                    isVerified: true,                    images: [                        'https://s3.bmp.ovh/imgs/2025/11/14/95dc0633799af85f.jpg',                        'https://s3.bmp.ovh/imgs/2025/11/14/52f9c737995f501e.jpg'                    ]                },
                {                    id: 8,                    name: '吴先生',                    avatar: 'https://ui-avatars.com/api/?name=吴先生&background=random',                    location: '西安',                    date: formatDate(new Date(today.getTime() - Math.floor(Math.random() * 3) * 24 * 60 * 60 * 1000)),                    rating: 5,                    comment: '服务质量非常高，团队协作默契，值得信赖！',                    isVerified: true,                    images: [                        'https://s3.bmp.ovh/imgs/2025/11/14/aad3c757fd3f240e.png',                        'https://s3.bmp.ovh/imgs/2025/11/14/09615d0a87903164.png'                    ]                }
            ];
            
            // 添加用户反馈到网格，使用交错布局增加视觉多样性
            userFeedbacks.forEach((feedback, index) => {
                const item = document.createElement('div');
                item.className = 'feedback-exhibition-item';
                
                // 用户信息区域
                const userInfo = document.createElement('div');
                userInfo.className = 'feedback-user-info';
                
                // 用户头像
                const avatar = document.createElement('img');
                avatar.className = 'feedback-user-avatar';
                avatar.src = feedback.avatar || 'https://via.placeholder.com/60x60?text=用户头像';
                avatar.alt = feedback.name;
                
                // 用户详情
                const userDetails = document.createElement('div');
                userDetails.className = 'feedback-user-details';
                
                // 用户名和认证徽章
                const nameContainer = document.createElement('div');
                nameContainer.className = 'feedback-user-name-container';
                
                const name = document.createElement('span');
                name.className = 'feedback-user-name';
                name.textContent = feedback.name;
                
                // 认证徽章
                if (feedback.isVerified) {
                    const verifiedBadge = document.createElement('span');
                    verifiedBadge.className = 'feedback-verified-badge';
                    verifiedBadge.innerHTML = '<i class="fas fa-check-circle"></i> 已认证用户';
                    nameContainer.appendChild(verifiedBadge);
                }
                
                // 地点和日期
                const locationDate = document.createElement('div');
                locationDate.className = 'feedback-location-date';
                locationDate.innerHTML = `<i class="fas fa-map-marker-alt"></i> ${feedback.location} · <i class="far fa-calendar"></i> ${feedback.date}`;
                
                // 评分
                const rating = document.createElement('div');
                rating.className = 'feedback-rating';
                for (let i = 0; i < 5; i++) {
                    const star = document.createElement('i');
                    star.className = `fas fa-star ${i < feedback.rating ? 'filled' : 'empty'}`;
                    rating.appendChild(star);
                }
                
                // 评论
                const comment = document.createElement('div');
                comment.className = 'feedback-comment';
                comment.textContent = feedback.comment;
                
                // 图片容器
                const imgContainer = document.createElement('div');
                imgContainer.className = 'feedback-exhibition-image-container';
                
                // 处理单个图片或图片数组
                const imagesToRender = feedback.images || (feedback.image ? [feedback.image] : []);
                
                imagesToRender.forEach((imageUrl, imgIndex) => {
                    // 图片
                    const img = document.createElement('img');
                    img.className = 'feedback-exhibition-image';
                    img.src = imageUrl;
                    img.alt = `用户反馈 ${index + 1} - 图片 ${imgIndex + 1}`;
                    img.onclick = () => showImagePreview(imageUrl);
                    // 图片加载失败处理
                    img.onerror = () => {
                        img.src = 'https://via.placeholder.com/400x300?text=用户反馈图片';
                    };
                    
                    // 图片悬停效果
                    const imgOverlay = document.createElement('div');
                    imgOverlay.className = 'feedback-exhibition-image-overlay';
                    imgOverlay.innerHTML = '<i class="fas fa-search-plus"></i> 点击查看大图';
                    
                    imgContainer.appendChild(img);
                    imgContainer.appendChild(imgOverlay);
                });
                
                // 组装元素
                nameContainer.appendChild(name);
                userDetails.appendChild(nameContainer);
                userDetails.appendChild(locationDate);
                userDetails.appendChild(rating);
                userInfo.appendChild(avatar);
                userInfo.appendChild(userDetails);
                
                item.appendChild(userInfo);
                item.appendChild(imgContainer);
                item.appendChild(comment);
                grid.appendChild(item);
            });
            
            // 显示模态框，添加淡入效果
            modal.style.opacity = '0';
            modal.style.transition = 'opacity 0.3s ease-in-out';
            modal.classList.add('active');
            setTimeout(() => {
                modal.style.opacity = '1';
            }, 10);
        }

        
        function closeFeedbackExhibition() {
            const modal = document.getElementById('feedbackExhibitionModal');
            modal.classList.remove('active');
        }
        
        function showImagePreview(imageUrl) {
            const modal = document.getElementById('imagePreviewModal');
            const previewImg = document.getElementById('imagePreview');
            
            previewImg.src = imageUrl;
            modal.classList.add('active');
        }
        
        function closeImagePreview() {
            const modal = document.getElementById('imagePreviewModal');
            modal.classList.remove('active');
        }
        
        // VIP提示功能
        function showVIPPrompt() {
            const modal = document.getElementById('vipPromptModal');
            modal.classList.add('active');
        }
        
        function closeVIPPrompt() {
            const modal = document.getElementById('vipPromptModal');
            modal.classList.remove('active');
        }
        
        // 法律条款相关功能
        let userAgreedToTerms = false;
        
        // 显示法律条款
        function showLegalTerms() {
            const modal = document.getElementById('legalTermsModal');
            modal.classList.add('active');
        }
        
        // 关闭法律条款
        function closeLegalTerms() {
            const modal = document.getElementById('legalTermsModal');
            modal.classList.remove('active');
        }
        
        // 接受法律条款
        function acceptLegalTerms() {
            userAgreedToTerms = true;
            localStorage.setItem('userAgreedToTerms', 'true');
            localStorage.setItem('userAgreedToTermsDate', new Date().toISOString());
            closeLegalTerms();
        }
        
        // 检查用户是否已同意条款
        function checkTermsAgreement() {
            // 从localStorage获取用户同意状态
            const storedAgreement = localStorage.getItem('userAgreedToTerms');
            if (storedAgreement === 'true') {
                userAgreedToTerms = true;
            } else {
                userAgreedToTerms = false;
                showLegalTerms();
            }
        }
        
        // 点击模态框外部关闭
        document.addEventListener('click', (e) => {
            const exhibitionModal = document.getElementById('feedbackExhibitionModal');
            const imageModal = document.getElementById('imagePreviewModal');
            const vipModal = document.getElementById('vipPromptModal');
            const legalModal = document.getElementById('legalTermsModal');
            
            if (e.target === exhibitionModal) {
                closeFeedbackExhibition();
            }
            
            if (e.target === imageModal) {
                closeImagePreview();
            }
            
            if (e.target === vipModal) {
                closeVIPPrompt();
            }
            
            if (e.target === legalModal) {
                closeLegalTerms();
            }
        });
        
        // 监听复选框变化，启用/禁用同意按钮
        document.addEventListener('DOMContentLoaded', function() {
            const agreeCheckbox = document.getElementById('agreeTerms');
            const acceptBtn = document.getElementById('acceptTermsBtn');
            
            if (agreeCheckbox && acceptBtn) {
                agreeCheckbox.addEventListener('change', function() {
                    acceptBtn.disabled = !this.checked;
                });
            }
            
            // 页面加载时检查用户是否已同意条款
            checkTermsAgreement();
        });
        
        // 为关键功能添加条款检查
        const originalGeneratePaymentRequest = generatePaymentRequest;
        generatePaymentRequest = function() {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return null;
            }
            return originalGeneratePaymentRequest.apply(this, arguments);
        };
        
        const originalGenerateMatchmakerPaymentRequest = generateMatchmakerPaymentRequest;
        generateMatchmakerPaymentRequest = function() {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return null;
            }
            return originalGenerateMatchmakerPaymentRequest.apply(this, arguments);
        };
        
        if (typeof originalRedirectToPayment === 'undefined') {
            const originalRedirectToPayment = redirectToPayment;
        }
        redirectToPayment = function(params) {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return;
            }
            originalRedirectToPayment.apply(this, arguments);
        };
        
        const originalSubmitPayment = submitPayment;
        submitPayment = function() {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return;
            }
            originalSubmitPayment.apply(this, arguments);
        };
        
        const originalSubmitMatchmakerPayment = submitMatchmakerPayment;
        submitMatchmakerPayment = function() {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return;
            }
            originalSubmitMatchmakerPayment.apply(this, arguments);
        };
        
        const originalRefundOrder = refundOrder;
        refundOrder = function(orderIndex) {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return;
            }
            originalRefundOrder.apply(this, arguments);
        };
        
        const originalViewUserDetail = viewUserDetail;
        viewUserDetail = function(userObj) {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return;
            }
            originalViewUserDetail.apply(this, arguments);
        };
        
        const originalViewUserContact = viewUserContact;
        viewUserContact = function(userId) {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return;
            }
            originalViewUserContact.apply(this, arguments);
        };
        
        const originalRegisterUser = registerUser;
        registerUser = function() {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return;
            }
            originalRegisterUser.apply(this, arguments);
        };
        
        const originalLoginUser = loginUser;
        loginUser = function() {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return;
            }
            originalLoginUser.apply(this, arguments);
        };
        
        const originalEditUserProfile = editUserProfile;
        editUserProfile = function() {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return;
            }
            originalEditUserProfile.apply(this, arguments);
        };
        
        const originalSubmitFeedback = submitFeedback;
        submitFeedback = function() {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return;
            }
            originalSubmitFeedback.apply(this, arguments);
        };
        
        const originalHandlePhotoUpload = handlePhotoUpload;
        handlePhotoUpload = function(event) {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return;
            }
            originalHandlePhotoUpload.apply(this, arguments);
        };
        
        const originalShowFeedbackExhibition = showFeedbackExhibition;
        showFeedbackExhibition = function() {
            if (!userAgreedToTerms) {
                alert('请先阅读并同意服务条款');
                showLegalTerms();
                return;
            }
            originalShowFeedbackExhibition.apply(this, arguments);
        };

    </script>
    
    <!-- 反馈展览模态框 -->
    <div class="feedback-exhibition-modal" id="feedbackExhibitionModal">
        <div class="feedback-exhibition-content">
            <div class="feedback-exhibition-header">
                <h2>用户真实反馈展览</h2>
                <button class="feedback-exhibition-close" onclick="closeFeedbackExhibition()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div class="feedback-exhibition-grid" id="feedbackExhibitionGrid">
                <!-- 图片将通过JavaScript动态添加 -->
            </div>
            <div class="feedback-exhibition-more">
                <button class="btn btn-primary gradient-bg" onclick="showVIPPrompt()">
                    <i class="fas fa-star"></i> 查看更多反馈
                </button>
            </div>
        </div>
    </div>
    
    <!-- VIP提示模态框 -->
    <div class="vip-prompt-modal" id="vipPromptModal">
        <div class="vip-prompt-content">
            <div class="vip-prompt-header">
                <h3><i class="fas fa-crown text-primary"></i> VIP专属特权</h3>
                <button class="vip-prompt-close" onclick="closeVIPPrompt()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div class="vip-prompt-body">
                <p>您好！查看更多用户真实反馈需要开通VIP会员。</p>
                <p>开通VIP后，您将享受：</p>
                <ul class="vip-privileges">
                    <li><i class="fas fa-check-circle text-success"></i> 查看全部用户反馈</li>
                    <li><i class="fas fa-check-circle text-success"></i> 无限次牵线服务</li>
                    <li><i class="fas fa-check-circle text-success"></i> 专属红娘服务</li>
                    <li><i class="fas fa-check-circle text-success"></i> 优先匹配权</li>
                </ul>
                <div class="vip-prompt-actions">
                    <button class="btn btn-primary gradient-bg" onclick="closeVIPPrompt()">
                        <i class="fas fa-thumbs-up"></i> 了解更多
                    </button>
                    <button class="btn btn-secondary" onclick="closeVIPPrompt()">
                        <i class="fas fa-times"></i> 稍后再说
                    </button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- 图片预览模态框 -->
    <div class="image-preview-modal" id="imagePreviewModal">
        <div class="image-preview-content">
            <img src="" alt="预览图片" class="image-preview" id="imagePreview">
            <button class="image-preview-close" onclick="closeImagePreview()">
                <i class="fas fa-times"></i>
            </button>
        </div>
    </div>

    <!-- 法律条款模态框 -->
    <div class="legal-terms-modal" id="legalTermsModal">
        <div class="legal-terms-content">
            <div class="legal-terms-header">
                <h3><i class="fas fa-gavel text-primary"></i> 服务条款与法律声明</h3>
            </div>
            <div class="legal-terms-body">
                <div class="terms-section">
                    <h4>1. 双方同意原则</h4>
                    <p>本平台所有服务均严格遵循双方自愿同意原则提供。用户在使用本平台任何服务前，必须明确表示同意本条款及相关规定。</p>
                    <p><strong>1.1 互动同意要求</strong></p>
                    <p>在进行任何形式的互动、交流或服务（包括但不限于用户匹配、信息交换、线下见面安排、礼物赠送、视频通话等）前，必须获得双方明确的书面或电子同意。</p>
                    <p><strong>1.2 数据使用同意</strong></p>
                    <p>本平台仅在获得用户明确同意的情况下，才会收集、使用、存储或分享用户的个人信息。用户有权随时撤回对数据使用的同意。</p>
                    <p><strong>1.3 服务变更同意</strong></p>
                    <p>如平台服务内容、收费标准或条款发生重大变更，将提前通知用户，并获得用户的明确同意后生效。</p>
                    <p><strong>1.4 同意的获取与确认</strong></p>
                    <p>双方同意可通过以下方式获取和确认：
                    <ul>
                        <li>用户主动点击"同意"、"确认"等按钮</li>
                        <li>用户通过平台内消息系统明确表示同意</li>
                        <li>用户通过电话、视频等方式明确口头同意（平台建议记录相关证明）</li>
                    </ul></p>
                    <p><strong>1.5 同意的撤回</strong></p>
                    <p>任何一方均可随时撤回已给出的同意，无需提供理由。撤回同意后，相关服务将立即终止。</p>
                    <p><strong>1.6 违反同意原则的后果</strong></p>
                    <p>任何违反双方同意原则的行为都可能导致账户被暂停或永久封禁。如造成损失，违规方需承担相应的法律责任。</p>
                </div>
                
                <div class="terms-section">
                    <h4>2. 用户隐私保护</h4>
                    <p>本平台严格保护用户个人隐私，未经用户明确同意，不会向任何第三方披露用户个人信息。</p>
                    <p>用户在与其他用户互动时，应自行保护个人隐私，避免泄露敏感信息。</p>
                </div>
                
                <div class="terms-section">
                    <h4>3. 服务使用条款</h4>
                    <p>用户必须年满18周岁且具备完全民事行为能力才能使用本平台服务。</p>
                    <p>用户需提供真实、准确的个人信息，不得冒用他人身份或提供虚假信息。</p>
                    <p>用户应遵守国家法律法规，不得利用本平台进行任何违法活动。</p>
                </div>
                
                <div class="terms-section">
                    <h4>4. 免责声明</h4>
                    <p>本平台仅提供信息撮合服务，不对用户之间的互动结果负责。</p>
                    <p>用户应对自己的行为负责，在与其他用户见面时应确保自身安全。</p>
                    <p>本平台保留根据法律法规或运营需要修改本条款的权利，修改后将通过平台公告通知用户。</p>
                </div>
                
                <div class="terms-section">
                    <h4>5. 法律适用</h4>
                    <p>本条款受中华人民共和国法律管辖，如有争议，应提交平台所在地有管辖权的人民法院解决。</p>
                </div>
            </div>
            <div class="legal-terms-footer">
                <div class="terms-checkbox">
                    <input type="checkbox" id="agreeTerms" name="agreeTerms">
                    <label for="agreeTerms">我已阅读并同意以上条款</label>
                </div>
                <div class="terms-actions">
                    <button class="btn btn-primary gradient-bg" id="acceptTermsBtn" disabled onclick="acceptLegalTerms()">
                        <i class="fas fa-check"></i> 同意并继续
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- 页面底部法律信息 -->
    <div class="footer-legal">
        <p>&copy; 2024 交友平台. 保留所有权利.</p>
        <p><a href="#" onclick="showLegalTerms()">服务条款</a> | <a href="#" onclick="showLegalTerms()">隐私政策</a> | <a href="#" onclick="showLegalTerms()">法律声明</a></p>
    </div>
</body>
</html>
