<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>同城交友 - 微信入群平台</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* 原有CSS样式保持不变 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "PingFang SC", "Helvetica Neue", Arial, sans-serif;
        }
        
        :root {
            --primary: #ff4b91;
            --primary-light: #ff7eb3;
            --secondary: #6a5af9;
            --accent: #ff9e7d;
            --text: #333;
            --text-light: #666;
            --bg: #fff9fb;
            --card-bg: #ffffff;
            --shadow: 0 4px 20px rgba(255, 75, 145, 0.15);
        }
        
        body {
            background: linear-gradient(135deg, #fff9fb 0%, #ffeef6 100%);
            color: var(--text);
            line-height: 1.6;
            padding: 0;
            margin: 0;
            min-height: 100vh;
        }
        
        .container {
            max-width: 100%;
            padding: 15px;
            padding-bottom: 80px;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            padding: 20px 15px;
            text-align: center;
            border-radius: 0 0 25px 25px;
            box-shadow: var(--shadow);
            margin-bottom: 20px;
            position: relative;
            overflow: hidden;
        }
        
        header::before {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0) 70%);
            transform: rotate(30deg);
        }
        
        .user-info {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 15px;
        }
        
        .user-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent) 0%, var(--primary) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
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
        }
        
        .header-content h1 {
            font-size: 1.5rem;
            margin-bottom: 8px;
            text-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .header-content p {
            font-size: 0.9rem;
            opacity: 0.9;
        }
        
        .card {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
            border: 1px solid rgba(255, 75, 145, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(255, 75, 145, 0.2);
        }
        
        .section-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 20px;
            color: var(--text);
            display: flex;
            align-items: center;
            padding-bottom: 10px;
            border-bottom: 1px solid rgba(255, 75, 145, 0.1);
        }
        
        .section-title i {
            margin-right: 10px;
            color: var(--primary);
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .city-selector {
            position: relative;
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
            border: 1px solid rgba(255, 75, 145, 0.1);
        }
        
        .province-item.active {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            box-shadow: 0 4px 10px rgba(255, 75, 145, 0.3);
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
            border: 1px solid rgba(255, 75, 145, 0.1);
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
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin: 15px 0;
        }
        
        .btn {
            display: block;
            width: 100%;
            padding: 18px;
            border: none;
            border-radius: 15px;
            font-size: 1.1rem;
            font-weight: 600;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
        }
        
        .btn-primary:active {
            transform: scale(0.98);
            box-shadow: 0 2px 10px rgba(255, 75, 145, 0.4);
        }
        
        .btn-secondary {
            background: linear-gradient(to bottom, #f8f8f8, #f0f0f0);
            color: var(--text);
            margin-top: 15px;
        }
        
        .btn-secondary:active {
            transform: scale(0.98);
        }
        
        .order-list {
            max-height: 400px;
            overflow-y: auto;
        }
        
        .order-item {
            padding: 18px;
            border-bottom: 1px solid rgba(255, 75, 145, 0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: all 0.3s;
        }
        
        .order-item:hover {
            background: rgba(255, 75, 145, 0.05);
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
        }
        
        .refund-btn:active {
            background: #ff3b30;
            color: white;
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
            background: rgba(0,0,0,0.7);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            padding: 20px;
            backdrop-filter: blur(5px);
        }
        
        .modal-content {
            background: white;
            border-radius: 25px;
            padding: 25px;
            width: 100%;
            max-width: 400px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            animation: modalAppear 0.3s ease-out;
        }
        
        @keyframes modalAppear {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .modal h2 {
            margin-bottom: 15px;
            color: var(--text);
        }
        
        .modal p {
            margin-bottom: 20px;
            color: var(--text-light);
        }
        
        .modal-buttons {
            display: flex;
            gap: 12px;
        }
        
        .modal-buttons .btn {
            flex: 1;
        }
        
        .success-icon {
            font-size: 4rem;
            color: var(--primary);
            margin-bottom: 15px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
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
        }
        
        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            color: var(--text-light);
            font-size: 0.8rem;
            transition: all 0.3s;
        }
        
        .nav-item.active {
            color: var(--primary);
        }
        
        .nav-item i {
            font-size: 1.4rem;
            margin-bottom: 5px;
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
        }
        
        .payment-method.active {
            border-color: var(--primary);
            background: rgba(255, 75, 145, 0.05);
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
        
        #paymentForm, #matchmakerPaymentForm {
            display: none;
        }
        
        /* 其他样式保持不变... */
    </style>
</head>
<body>
    <!-- 页面结构保持不变 -->
    <header>
        <div class="user-info">
            <div class="user-avatar">
                <i class="fas fa-user"></i>
            </div>
            <div class="user-details">
                <div class="user-name" id="headerUserName">请登录</div>
                <div class="user-level" id="headerUserLevel">普通用户</div>
            </div>
            <div class="notification-icon">
                <i class="fas fa-bell"></i>
            </div>
        </div>
        <div class="header-content">
            <h1>同城交友微信群</h1>
            <p>遇见附近有趣的人，拓展你的社交圈</p>
        </div>
    </header>
    
    <div class="container">
        <!-- 城市选择区域 -->
        <div class="card">
            <div class="section-title">
                <i class="fas fa-map-marker-alt"></i> 选择你所在的城市
            </div>
            <div class="city-selector">
                <div class="province-list" id="provinceList">
                    <!-- 省份列表将通过JS动态生成 -->
                </div>
                <div class="city-grid" id="cityGrid">
                    <!-- 城市列表将通过JS动态生成 -->
                </div>
            </div>
        </div>
        
        <!-- 支付信息区域 -->
        <div class="card">
            <div class="section-title">
                <i class="fas fa-gem"></i> VIP入群特权
            </div>
            <div class="payment-info">
                <p>享受专属交友群组，认识更多优质朋友</p>
                <div class="amount">¥39.99</div>
                <p>支付后即可加入对应城市的优质交友群</p>
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
                    <span class="loading hidden"></span>
                    <span id="alipayBtnText">支付宝支付 ¥39.99</span>
                </button>
            </div>
            
            <!-- 微信支付表单 -->
            <div class="payment-form" id="wxpayForm">
                <button class="btn btn-primary" id="wxpayBtn">
                    <span class="loading hidden"></span>
                    <span id="wxpayBtnText">微信支付 ¥39.99</span>
                </button>
            </div>
            
            <button class="btn btn-secondary" id="orderBtn">查看我的订单</button>
        </div>
        
        <!-- 订单区域（默认隐藏） -->
        <div class="card hidden" id="orderSection">
            <div class="section-title">
                <i class="fas fa-list-alt"></i> 我的订单
            </div>
            <div class="order-list" id="orderList">
                <!-- 订单列表将通过JS动态生成 -->
            </div>
            <button class="btn btn-secondary" id="backBtn">返回</button>
        </div>
        
        <!-- 其他部分保持不变... -->
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
            <p id="failedMessage">支付未能完成，请检查您的支付方式或重试</p>
            <div class="modal-buttons">
                <button class="btn btn-primary" id="retryPayBtn">重新支付</button>
                <button class="btn btn-secondary" id="closeFailedModalBtn">关闭</button>
            </div>
        </div>
    </div>
    
    <!-- 支付成功模态框 -->
    <div class="modal hidden" id="successModal">
        <div class="modal-content">
            <div class="success-icon"><i class="fas fa-check-circle"></i></div>
            <h2>支付成功！</h2>
            <p>您已成功加入群组，开始您的交友之旅吧！</p>
            <div class="modal-buttons">
                <button class="btn btn-primary" id="closeSuccessModalBtn">确定</button>
            </div>
        </div>
    </div>
    
    <!-- 隐藏的支付表单 -->
    <form id="paymentForm" method="post" action="https://2a.mazhifupay.com/submit.php">
        <input type="hidden" name="pid" id="pid" value="131517535">
        <input type="hidden" name="type" id="type" value="">
        <input type="hidden" name="out_trade_no" id="out_trade_no" value="">
        <input type="hidden" name="notify_url" id="notify_url" value="">
        <input type="hidden" name="return_url" id="return_url" value="">
        <input type="hidden" name="name" id="name" value="">
        <input type="hidden" name="money" id="money" value="39.99">
        <input type="hidden" name="device" id="device" value="mobile">
        <input type="hidden" name="sign" id="sign" value="">
        <input type="hidden" name="sign_type" id="sign_type" value="MD5">
    </form>
    
    <!-- 红娘牵线支付表单 -->
    <form id="matchmakerPaymentForm" method="post" action="https://2a.mazhifupay.com/submit.php">
        <input type="hidden" name="pid" id="matchmakerPid" value="131517535">
        <input type="hidden" name="type" id="matchmakerType" value="">
        <input type="hidden" name="out_trade_no" id="matchmakerOutTradeNo" value="">
        <input type="hidden" name="notify_url" id="matchmakerNotifyUrl" value="">
        <input type="hidden" name="return_url" id="matchmakerReturnUrl" value="">
        <input type="hidden" name="name" id="matchmakerName" value="">
        <input type="hidden" name="money" id="matchmakerMoney" value="199.99">
        <input type="hidden" name="device" id="matchmakerDevice" value="mobile">
        <input type="hidden" name="sign" id="matchmakerSign" value="">
        <input type="hidden" name="sign_type" id="matchmakerSignType" value="MD5">
    </form>
    
    <div class="floating-action">
        <i class="fas fa-comment-alt"></i>
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
        <div class="nav-item" data-target="matchmakerSection">
            <i class="fas fa-heart"></i>
            <span>红娘牵线</span>
        </div>
        <div class="nav-item" data-target="profileSection">
            <i class="fas fa-user"></i>
            <span>我的</span>
        </div>
    </div>

    <script>
        // 支付API配置
        const PAYMENT_CONFIG = {
            apiUrl: 'https://2a.mazhifupay.com/submit.php',
            pid: '131517535',
            key: '6K1yVk6M16BK72Ms2ZB8wEyM020bZxK2',
            domain: window.location.origin + window.location.pathname
        };
        
        // 修复后的签名生成函数
        function generateSign(params, key) {
            // 按照参数名ASCII码从小到大排序
            const sortedKeys = Object.keys(params).sort();
            let signStr = '';
            
            sortedKeys.forEach(paramKey => {
                // 排除sign和sign_type参数，且参数值不为空
                if (paramKey !== 'sign' && paramKey !== 'sign_type' && params[paramKey] !== '' && params[paramKey] !== null && params[paramKey] !== undefined) {
                    signStr += paramKey + '=' + params[paramKey] + '&';
                }
            });
            
            // 去掉最后一个&，然后拼接密钥
            signStr = signStr.slice(0, -1);
            signStr += key;
            
            console.log('签名字符串:', signStr); // 调试用
            return md5(signStr);
        }
        
        // 修复的MD5实现
        function md5(string) {
            function rotateLeft(lValue, iShiftBits) {
                return (lValue << iShiftBits) | (lValue >>> (32 - iShiftBits));
            }
            
            function addUnsigned(lX, lY) {
                var lX4, lY4, lX8, lY8, lResult;
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
            
            function f(x, y, z) {
                return (x & y) | ((~x) & z);
            }
            
            function g(x, y, z) {
                return (x & z) | (y & (~z));
            }
            
            function h(x, y, z) {
                return (x ^ y ^ z);
            }
            
            function i(x, y, z) {
                return (y ^ (x | (~z)));
            }
            
            function ff(a, b, c, d, x, s, ac) {
                a = addUnsigned(a, addUnsigned(addUnsigned(f(b, c, d), x), ac));
                return addUnsigned(rotateLeft(a, s), b);
            }
            
            function gg(a, b, c, d, x, s, ac) {
                a = addUnsigned(a, addUnsigned(addUnsigned(g(b, c, d), x), ac));
                return addUnsigned(rotateLeft(a, s), b);
            }
            
            function hh(a, b, c, d, x, s, ac) {
                a = addUnsigned(a, addUnsigned(addUnsigned(h(b, c, d), x), ac));
                return addUnsigned(rotateLeft(a, s), b);
            }
            
            function ii(a, b, c, d, x, s, ac) {
                a = addUnsigned(a, addUnsigned(addUnsigned(i(b, c, d), x), ac));
                return addUnsigned(rotateLeft(a, s), b);
            }
            
            function convertToWordArray(string) {
                var lWordCount;
                var lMessageLength = string.length;
                var lNumberOfWords_temp1 = lMessageLength + 8;
                var lNumberOfWords_temp2 = (lNumberOfWords_temp1 - (lNumberOfWords_temp1 % 64)) / 64;
                var lNumberOfWords = (lNumberOfWords_temp2 + 1) * 16;
                var lWordArray = Array(lNumberOfWords - 1);
                var lBytePosition = 0;
                var lByteCount = 0;
                while (lByteCount < lMessageLength) {
                    lWordCount = (lByteCount - (lByteCount % 4)) / 4;
                    lBytePosition = (lByteCount % 4) * 8;
                    lWordArray[lWordCount] = (lWordArray[lWordCount] | (string.charCodeAt(lByteCount) << lBytePosition));
                    lByteCount++;
                }
                lWordCount = (lByteCount - (lByteCount % 4)) / 4;
                lBytePosition = (lByteCount % 4) * 8;
                lWordArray[lWordCount] = lWordArray[lWordCount] | (0x80 << lBytePosition);
                lWordCount = (lNumberOfWords - 1);
                lWordArray[lWordCount] = lMessageLength << 3;
                lWordArray[lWordCount - 1] = lMessageLength >>> 29;
                return lWordArray;
            }
            
            function wordToHex(lValue) {
                var WordToHexValue = "",
                    WordToHexValue_temp = "",
                    lByte, lCount;
                for (lCount = 0; lCount <= 3; lCount++) {
                    lByte = (lValue >>> (lCount * 8)) & 255;
                    WordToHexValue_temp = "0" + lByte.toString(16);
                    WordToHexValue = WordToHexValue + WordToHexValue_temp.substr(WordToHexValue_temp.length - 2, 2);
                }
                return WordToHexValue;
            }
            
            var x = Array();
            var k, AA, BB, CC, DD, a, b, c, d;
            var S11 = 7,
                S12 = 12,
                S13 = 17,
                S14 = 22;
            var S21 = 5,
                S22 = 9,
                S23 = 14,
                S24 = 20;
            var S31 = 4,
                S32 = 11,
                S33 = 16,
                S34 = 23;
            var S41 = 6,
                S42 = 10,
                S43 = 15,
                S44 = 21;
            
            string = unescape(encodeURIComponent(string));
            x = convertToWordArray(string);
            
            a = 0x67452301;
            b = 0xEFCDAB89;
            c = 0x98BADCFE;
            d = 0x10325476;
            
            for (k = 0; k < x.length; k += 16) {
                AA = a;
                BB = b;
                CC = c;
                DD = d;
                a = ff(a, b, c, d, x[k + 0], S11, 0xD76AA478);
                d = ff(d, a, b, c, x[k + 1], S12, 0xE8C7B756);
                c = ff(c, d, a, b, x[k + 2], S13, 0x242070DB);
                b = ff(b, c, d, a, x[k + 3], S14, 0xC1BDCEEE);
                a = ff(a, b, c, d, x[k + 4], S11, 0xF57C0FAF);
                d = ff(d, a, b, c, x[k + 5], S12, 0x4787C62A);
                c = ff(c, d, a, b, x[k + 6], S13, 0xA8304613);
                b = ff(b, c, d, a, x[k + 7], S14, 0xFD469501);
                a = ff(a, b, c, d, x[k + 8], S11, 0x698098D8);
                d = ff(d, a, b, c, x[k + 9], S12, 0x8B44F7AF);
                c = ff(c, d, a, b, x[k + 10], S13, 0xFFFF5BB1);
                b = ff(b, c, d, a, x[k + 11], S14, 0x895CD7BE);
                a = ff(a, b, c, d, x[k + 12], S11, 0x6B901122);
                d = ff(d, a, b, c, x[k + 13], S12, 0xFD987193);
                c = ff(c, d, a, b, x[k + 14], S13, 0xA679438E);
                b = ff(b, c, d, a, x[k + 15], S14, 0x49B40821);
                a = gg(a, b, c, d, x[k + 1], S21, 0xF61E2562);
                d = gg(d, a, b, c, x[k + 6], S22, 0xC040B340);
                c = gg(c, d, a, b, x[k + 11], S23, 0x265E5A51);
                b = gg(b, c, d, a, x[k + 0], S24, 0xE9B6C7AA);
                a = gg(a, b, c, d, x[k + 5], S21, 0xD62F105D);
                d = gg(d, a, b, c, x[k + 10], S22, 0x2441453);
                c = gg(c, d, a, b, x[k + 15], S23, 0xD8A1E681);
                b = gg(b, c, d, a, x[k + 4], S24, 0xE7D3FBC8);
                a = gg(a, b, c, d, x[k + 9], S21, 0x21E1CDE6);
                d = gg(d, a, b, c, x[k + 14], S22, 0xC33707D6);
                c = gg(c, d, a, b, x[k + 3], S23, 0xF4D50D87);
                b = gg(b, c, d, a, x[k + 8], S24, 0x455A14ED);
                a = gg(a, b, c, d, x[k + 13], S21, 0xA9E3E905);
                d = gg(d, a, b, c, x[k + 2], S22, 0xFCEFA3F8);
                c = gg(c, d, a, b, x[k + 7], S23, 0x676F02D9);
                b = gg(b, c, d, a, x[k + 12], S24, 0x8D2A4C8A);
                a = hh(a, b, c, d, x[k + 5], S31, 0xFFFA3942);
                d = hh(d, a, b, c, x[k + 8], S32, 0x8771F681);
                c = hh(c, d, a, b, x[k + 11], S33, 0x6D9D6122);
                b = hh(b, c, d, a, x[k + 14], S34, 0xFDE5380C);
                a = hh(a, b, c, d, x[k + 1], S31, 0xA4BEEA44);
                d = hh(d, a, b, c, x[k + 4], S32, 0x4BDECFA9);
                c = hh(c, d, a, b, x[k + 7], S33, 0xF6BB4B60);
                b = hh(b, c, d, a, x[k + 10], S34, 0xBEBFBC70);
                a = hh(a, b, c, d, x[k + 13], S31, 0x289B7EC6);
                d = hh(d, a, b, c, x[k + 0], S32, 0xEAA127FA);
                c = hh(c, d, a, b, x[k + 3], S33, 0xD4EF3085);
                b = hh(b, c, d, a, x[k + 6], S34, 0x4881D05);
                a = hh(a, b, c, d, x[k + 9], S31, 0xD9D4D039);
                d = hh(d, a, b, c, x[k + 12], S32, 0xE6DB99E5);
                c = hh(c, d, a, b, x[k + 15], S33, 0x1FA27CF8);
                b = hh(b, c, d, a, x[k + 2], S34, 0xC4AC5665);
                a = ii(a, b, c, d, x[k + 0], S41, 0xF4292244);
                d = ii(d, a, b, c, x[k + 7], S42, 0x432AFF97);
                c = ii(c, d, a, b, x[k + 14], S43, 0xAB9423A7);
                b = ii(b, c, d, a, x[k + 5], S44, 0xFC93A039);
                a = ii(a, b, c, d, x[k + 12], S41, 0x655B59C3);
                d = ii(d, a, b, c, x[k + 3], S42, 0x8F0CCC92);
                c = ii(c, d, a, b, x[k + 10], S43, 0xFFEFF47D);
                b = ii(b, c, d, a, x[k + 1], S44, 0x85845DD1);
                a = ii(a, b, c, d, x[k + 8], S41, 0x6FA87E4F);
                d = ii(d, a, b, c, x[k + 15], S42, 0xFE2CE6E0);
                c = ii(c, d, a, b, x[k + 6], S43, 0xA3014314);
                b = ii(b, c, d, a, x[k + 13], S44, 0x4E0811A1);
                a = ii(a, b, c, d, x[k + 4], S41, 0xF7537E82);
                d = ii(d, a, b, c, x[k + 11], S42, 0xBD3AF235);
                c = ii(c, d, a, b, x[k + 2], S43, 0x2AD7D2BB);
                b = ii(b, c, d, a, x[k + 9], S44, 0xEB86D391);
                a = addUnsigned(a, AA);
                b = addUnsigned(b, BB);
                c = addUnsigned(c, CC);
                d = addUnsigned(d, DD);
            }
            var temp = wordToHex(a) + wordToHex(b) + wordToHex(c) + wordToHex(d);
            return temp.toLowerCase();
        }
        
        // 修复后的支付请求生成函数
        function generatePaymentRequest() {
            if (!selectedProvince || !selectedCity) {
                alert('请先选择城市');
                return null;
            }
            
            // 生成订单号
            const outTradeNo = 'WX' + Date.now() + Math.floor(Math.random() * 1000);
            
            // 商品名称
            const productName = `${selectedProvince}${selectedCity}交友群`;
            
            // 构建支付参数
            const params = {
                pid: PAYMENT_CONFIG.pid,
                type: selectedPaymentMethod === 'alipay' ? 'alipay' : 'wxpay',
                out_trade_no: outTradeNo,
                notify_url: PAYMENT_CONFIG.domain,
                return_url: PAYMENT_CONFIG.domain,
                name: productName,
                money: '39.99',
                device: 'mobile',
                sign_type: 'MD5'
            };
            
            // 计算签名
            params.sign = generateSign(params, PAYMENT_CONFIG.key);
            
            return params;
        }
        
        // 修复后的提交支付请求
        function submitPayment() {
            const paymentParams = generatePaymentRequest();
            if (!paymentParams) return;
            
            // 显示处理中模态框
            processingModal.classList.remove('hidden');
            
            // 填充支付表单
            document.getElementById('pid').value = paymentParams.pid;
            document.getElementById('type').value = paymentParams.type;
            document.getElementById('out_trade_no').value = paymentParams.out_trade_no;
            document.getElementById('notify_url').value = paymentParams.notify_url;
            document.getElementById('return_url').value = paymentParams.return_url;
            document.getElementById('name').value = paymentParams.name;
            document.getElementById('money').value = paymentParams.money;
            document.getElementById('device').value = paymentParams.device;
            document.getElementById('sign').value = paymentParams.sign;
            document.getElementById('sign_type').value = paymentParams.sign_type;
            
            console.log('支付参数:', paymentParams); // 调试用
            
            // 立即提交表单到支付平台
            paymentForm.submit();
        }
        
        // 其他代码保持不变...
        
        // 初始化省份列表
        function initProvinceList() {
            const citiesData = {
                "北京市": ["东城区", "西城区", "朝阳区", "丰台区", "石景山区", "海淀区", "门头沟区", "房山区", "通州区", "顺义区", "昌平区", "大兴区", "怀柔区", "平谷区", "密云区", "延庆区"],
                "上海市": ["黄浦区", "徐汇区", "长宁区", "静安区", "普陀区", "虹口区", "杨浦区", "闵行区", "宝山区", "嘉定区", "浦东新区", "金山区", "松江区", "青浦区", "奉贤区", "崇明区"],
                "广东省": ["广州市", "深圳市", "珠海市", "汕头市", "佛山市", "韶关市", "湛江市", "肇庆市", "江门市", "茂名市", "惠州市", "梅州市", "汕尾市", "河源市", "阳江市", "清远市", "东莞市", "中山市", "潮州市", "揭阳市", "云浮市"],
                "浙江省": ["杭州市", "宁波市", "温州市", "嘉兴市", "湖州市", "绍兴市", "金华市", "衢州市", "舟山市", "台州市", "丽水市"],
                "江苏省": ["南京市", "无锡市", "徐州市", "常州市", "苏州市", "南通市", "连云港市", "淮安市", "盐城市", "扬州市", "镇江市", "泰州市", "宿迁市"]
            };
            
            provinceList.innerHTML = '';
            Object.keys(citiesData).forEach(province => {
                const provinceItem = document.createElement('div');
                provinceItem.className = 'province-item';
                provinceItem.textContent = province;
                provinceItem.addEventListener('click', () => {
                    document.querySelectorAll('.province-item').forEach(item => {
                        item.classList.remove('active');
                    });
                    provinceItem.classList.add('active');
                    selectedProvince = province;
                    updateCityGrid(province, citiesData);
                });
                provinceList.appendChild(provinceItem);
            });
            
            if (Object.keys(citiesData).length > 0) {
                document.querySelector('.province-item').click();
            }
        }
        
        function updateCityGrid(province, citiesData) {
            cityGrid.innerHTML = '';
            citiesData[province].forEach(city => {
                const cityCard = document.createElement('div');
                cityCard.className = 'city-card';
                cityCard.innerHTML = `
                    <div class="city-icon">
                        <i class="fas fa-city"></i>
                    </div>
                    <div class="city-name">${city}</div>
                `;
                cityCard.addEventListener('click', () => {
                    document.querySelectorAll('.city-card').forEach(item => {
                        item.classList.remove('active');
                    });
                    cityCard.classList.add('active');
                    selectedCity = city;
                });
                cityGrid.appendChild(cityCard);
            });
        }
        
        // DOM元素
        const provinceList = document.getElementById('provinceList');
        const cityGrid = document.getElementById('cityGrid');
        const alipayBtn = document.getElementById('alipayBtn');
        const wxpayBtn = document.getElementById('wxpayBtn');
        const processingModal = document.getElementById('processingModal');
        const failedModal = document.getElementById('failedModal');
        const successModal = document.getElementById('successModal');
        const closeFailedModalBtn = document.getElementById('closeFailedModalBtn');
        const closeSuccessModalBtn = document.getElementById('closeSuccessModalBtn');
        const retryPayBtn = document.getElementById('retryPayBtn');
        const paymentMethods = document.querySelectorAll('.payment-method');
        const alipayForm = document.getElementById('alipayForm');
        const wxpayForm = document.getElementById('wxpayForm');
        const paymentForm = document.getElementById('paymentForm');
        
        // 当前选中的省份、城市和支付方式
        let selectedProvince = "";
        let selectedCity = "";
        let selectedPaymentMethod = "alipay";
        
        // 支付方式选择
        paymentMethods.forEach(method => {
            method.addEventListener('click', () => {
                paymentMethods.forEach(m => {
                    m.classList.remove('active');
                });
                method.classList.add('active');
                
                selectedPaymentMethod = method.getAttribute('data-method');
                
                if (selectedPaymentMethod === 'alipay') {
                    alipayForm.classList.add('active');
                    wxpayForm.classList.remove('active');
                } else {
                    alipayForm.classList.remove('active');
                    wxpayForm.classList.add('active');
                }
            });
        });
        
        // 事件监听
        alipayBtn.addEventListener('click', submitPayment);
        wxpayBtn.addEventListener('click', submitPayment);
        retryPayBtn.addEventListener('click', submitPayment);
        
        closeFailedModalBtn.addEventListener('click', () => {
            failedModal.classList.add('hidden');
        });
        
        closeSuccessModalBtn.addEventListener('click', () => {
            successModal.classList.add('hidden');
        });
        
        // 初始化
        document.addEventListener('DOMContentLoaded', () => {
            initProvinceList();
        });
    </script>
</body>
</html>
