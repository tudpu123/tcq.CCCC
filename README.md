<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>同城交友 - 微信入群平台</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
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
            --primary: #ff2d8e;
            --primary-light: #ff7eb3;
            --secondary: #ff2d55;
            --accent: #ff6b9c;
            --text: #333;
            --text-light: #666;
            --bg: #fff5f9;
            --card-bg: #ffffff;
            --shadow: 0 4px 20px rgba(255, 45, 142, 0.2);
        }
        
        body {
            background: linear-gradient(135deg, #fff5f9 0%, #ffe6f1 100%);
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
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .user-avatar:active {
            transform: scale(0.95);
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
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
            font-size: 1.5rem;
            margin-bottom: 8px;
            text-shadow: 0 2px 5px rgba(0,0,0,0.1);
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .header-content h1:active {
            transform: scale(0.98);
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
            border: 1px solid rgba(255, 45, 142, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(255, 45, 142, 0.25);
        }
        
        .section-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 20px;
            color: var(--text);
            display: flex;
            align-items: center;
            padding-bottom: 10px;
            border-bottom: 1px solid rgba(255, 45, 142, 0.1);
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
            transition: all 0.2s ease;
        }
        
        .btn:active {
            transform: scale(0.98);
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
        }
        
        .btn-primary:active {
            transform: scale(0.98);
            box-shadow: 0 2px 10px rgba(255, 45, 142, 0.4);
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
            background: linear-gradient(135deg, #f8f8f8, #f0f0f0);
            border-radius: 20px;
            padding: 20px;
            margin-bottom: 20px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            border: 1px solid rgba(255, 45, 142, 0.1);
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
            box-shadow: 0 8px 20px rgba(255, 45, 142, 0.3);
            overflow: hidden;
        }
        
        .matchmaker-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .matchmaker-name {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 5px;
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
            background: linear-gradient(135deg, #fff5f9 0%, #ffe6f1 100%);
            border-radius: 20px;
            padding: 25px;
            margin: 20px 0;
            text-align: center;
            border: 1px solid rgba(255, 45, 142, 0.1);
            box-shadow: var(--shadow);
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
        }
        
        .matchmaker-payment-method:active {
            transform: scale(0.98);
        }
        
        .matchmaker-payment-method.active {
            border-color: var(--primary);
            background: rgba(255, 45, 142, 0.05);
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
        .customer-service-btn {
            position: fixed;
            bottom: 80px;
            left: 20px;
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #07c160 0%, #0baa53 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
            box-shadow: 0 4px 20px rgba(7, 193, 96, 0.4);
            z-index: 99;
            animation: pulse 2s infinite;
            transition: all 0.2s ease;
        }
        
        .customer-service-btn:active {
            transform: scale(0.95);
        }
        
        .customer-service-chat {
            position: fixed;
            bottom: 150px;
            left: 20px;
            width: 320px;
            height: 450px;
            background: white;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            z-index: 100;
            display: flex;
            flex-direction: column;
            overflow: hidden;
            transition: all 0.3s;
        }
        
        .customer-service-chat.hidden {
            display: none;
        }
        
        .chat-header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            padding: 15px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .chat-header-title {
            font-size: 1.1rem;
            font-weight: 600;
        }
        
        .chat-close-btn {
            background: none;
            border: none;
            color: white;
            font-size: 1.2rem;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .chat-close-btn:active {
            transform: scale(0.9);
        }
        
        .chat-messages-container {
            flex: 1;
            padding: 15px;
            overflow-y: auto;
            background: #f8f8f8;
        }
        
        .chat-message {
            margin-bottom: 15px;
            display: flex;
        }
        
        .chat-message.customer {
            justify-content: flex-end;
        }
        
        .message-bubble {
            max-width: 80%;
            padding: 10px 15px;
            border-radius: 18px;
            font-size: 0.9rem;
        }
        
        .message-bubble.user {
            background: var(--primary);
            color: white;
            border-bottom-right-radius: 5px;
        }
        
        .message-bubble.support {
            background: white;
            color: var(--text);
            border: 1px solid #e0e0e0;
            border-bottom-left-radius: 5px;
        }
        
        .message-time {
            font-size: 0.7rem;
            color: var(--text-light);
            margin-top: 5px;
            text-align: right;
        }
        
        .chat-input-container {
            padding: 15px;
            border-top: 1px solid #e0e0e0;
            display: flex;
            gap: 10px;
        }
        
        .chat-input {
            flex: 1;
            padding: 12px 15px;
            border: 1px solid #e0e0e0;
            border-radius: 20px;
            font-size: 0.9rem;
            outline: none;
        }
        
        .chat-send-btn {
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .chat-send-btn:active {
            transform: scale(0.95);
        }
        
        /* 客服后台样式 */
        .admin-panel {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: white;
            z-index: 1000;
            display: flex;
            flex-direction: column;
        }
        
        .admin-header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            padding: 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .admin-title {
            font-size: 1.2rem;
            font-weight: 600;
        }
        
        .admin-logout-btn {
            background: rgba(255,255,255,0.2);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .admin-logout-btn:active {
            transform: scale(0.95);
        }
        
        .admin-content {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
        }
        
        .user-list {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }
        
        .user-item {
            background: #f8f8f8;
            border-radius: 12px;
            padding: 15px;
            cursor: pointer;
            transition: all 0.3s;
            transition: all 0.2s ease;
        }
        
        .user-item:active {
            transform: scale(0.98);
        }
        
        .user-item:hover {
            background: rgba(255, 45, 142, 0.05);
        }
        
        .user-item.active {
            background: rgba(255, 45, 142, 0.1);
            border: 1px solid var(--primary);
        }
        
        .user-name {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .user-last-message {
            font-size: 0.9rem;
            color: var(--text-light);
        }
        
        .admin-chat-container {
            display: flex;
            flex-direction: column;
            height: 100%;
        }
        
        .admin-chat-header {
            padding: 15px;
            border-bottom: 1px solid #e0e0e0;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .admin-chat-messages {
            flex: 1;
            padding: 15px;
            overflow-y: auto;
            background: #f8f8f8;
        }
        
        .admin-chat-input-container {
            padding: 15px;
            border-top: 1px solid #e0e0e0;
            display: flex;
            gap: 10px;
        }
        
        .admin-back-btn {
            background: none;
            border: none;
            color: var(--primary);
            font-size: 1.2rem;
            cursor: pointer;
            margin-right: 10px;
            transition: all 0.2s ease;
        }
        
        .admin-back-btn:active {
            transform: scale(0.9);
        }
        
        .no-user-selected {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100%;
            color: var(--text-light);
            text-align: center;
        }
        
        .no-user-selected i {
            font-size: 3rem;
            margin-bottom: 15px;
            color: #e0e0e0;
        }
        
        /* 新增客服后台统计面板样式 */
        .admin-stats-panel {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .stat-card {
            background: linear-gradient(135deg, #f8f8f8, #f0f0f0);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            border: 1px solid rgba(255, 45, 142, 0.1);
        }
        
        .stat-card .stat-value {
            font-size: 2rem;
            font-weight: bold;
            margin-bottom: 5px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .stat-card .stat-label {
            font-size: 0.9rem;
            color: var(--text-light);
        }
        
        .admin-tabs {
            display: flex;
            margin-bottom: 20px;
            border-bottom: 1px solid #e0e0e0;
        }
        
        .admin-tab {
            padding: 12px 20px;
            cursor: pointer;
            transition: all 0.3s;
            border-bottom: 3px solid transparent;
            transition: all 0.2s ease;
        }
        
        .admin-tab:active {
            transform: scale(0.98);
        }
        
        .admin-tab.active {
            border-bottom: 3px solid var(--primary);
            color: var(--primary);
            font-weight: 600;
        }
        
        .admin-tab-content {
            display: none;
        }
        
        .admin-tab-content.active {
            display: block;
        }
        
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
            background: linear-gradient(135deg, #f8f8f8, #f0f0f0);
            border-radius: 20px;
            padding: 20px;
            margin-bottom: 20px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            border: 1px solid rgba(255, 45, 142, 0.1);
            position: relative;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .matchmaker-user-card:active {
            transform: scale(0.98);
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
            background: linear-gradient(135deg, #f8f8f8, #f0f0f0);
            border-radius: 20px;
            padding: 20px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            border: 1px solid rgba(255, 45, 142, 0.1);
            transition: all 0.3s;
            cursor: pointer;
            transition: all 0.2s ease;
        }
        
        .matchmaker-user-list-item:active {
            transform: scale(0.98);
        }
        
        .matchmaker-user-list-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(255, 45, 142, 0.2);
        }
        
        .matchmaker-user-list-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            margin: 0 auto 10px;
            overflow: hidden;
            border: 2px solid var(--primary);
        }
        
        .matchmaker-user-list-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .matchmaker-user-list-name {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 5px;
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
            padding: 15px;
            background: rgba(255, 45, 142, 0.05);
            border-radius: 15px;
            border: 1px solid rgba(255, 45, 142, 0.1);
        }
        
        .matchmaker-city-selector-title {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: var(--primary);
            text-align: center;
        }
        
        .matchmaker-city-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
        }
        
        .matchmaker-city-item {
            padding: 10px 5px;
            text-align: center;
            background: white;
            border-radius: 10px;
            font-size: 0.85rem;
            cursor: pointer;
            transition: all 0.3s;
            border: 1px solid rgba(255, 45, 142, 0.1);
            transition: all 0.2s ease;
        }
        
        .matchmaker-city-item:active {
            transform: scale(0.98);
        }
        
        .matchmaker-city-item.active {
            background: var(--primary);
            color: white;
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
            <div class="notification-icon">
                <i class="fas fa-bell"></i>
            </div>
        </div>
        <div class="header-content">
            <h1 id="mainTitle">同城交友微信群</h1>
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
                
                <!-- 城市折叠区域 -->
                <div class="city-collapse">
                    <div class="collapse-toggle" id="cityCollapseToggle">
                        <span>选择城市</span>
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="collapse-content" id="cityCollapseContent">
                        <div class="city-grid" id="cityGrid">
                            <!-- 城市列表将通过JS动态生成 -->
                        </div>
                    </div>
                </div>
                
                <!-- 查看聊天记录按钮 -->
                <button class="view-chat-btn" id="viewChatBtn" disabled>
                    <i class="fas fa-comments"></i> 查看群聊记录
                </button>
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
                    <div class="login-type-tab" data-type="admin">客服后台登录</div>
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
                    
                    <div class="form-actions">
                        <button class="btn btn-primary" id="loginSubmitBtn">登录</button>
                        <button class="btn btn-secondary" id="loginCancelBtn">取消</button>
                    </div>
                    
                    <div class="login-prompt">
                        <p>还没有账号？</p>
                        <button class="btn btn-secondary" id="showRegisterBtn">立即注册</button>
                    </div>
                </div>
                
                <!-- 客服后台登录表单 -->
                <div class="login-form hidden" id="adminLoginForm">
                    <div class="section-title">
                        <i class="fas fa-lock"></i> 客服后台登录
                    </div>
                    
                    <div class="form-group">
                        <label for="adminUsername">账号</label>
                        <input type="text" id="adminUsername" placeholder="请输入账号">
                    </div>
                    
                    <div class="form-group">
                        <label for="adminPassword">密码</label>
                        <input type="password" id="adminPassword" placeholder="请输入密码">
                    </div>
                    
                    <div class="form-actions">
                        <button class="btn btn-primary" id="adminLoginBtn">登录</button>
                        <button class="btn btn-secondary" id="adminLoginCancelBtn">取消</button>
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
        
        <!-- 红娘牵线区域（默认隐藏） -->
        <div class="card hidden" id="matchmakerSection">
            <div class="section-title">
                <i class="fas fa-heart"></i> 红娘牵线
            </div>
            
            <!-- 城市选择区域（VIP限制） -->
            <div class="matchmaker-city-selector vip-restricted" id="matchmakerCitySelector">
                <div class="matchmaker-city-selector-title">选择你所在的城市区域</div>
                <div class="matchmaker-city-grid" id="matchmakerCityGrid">
                    <!-- 城市区域将通过JS动态生成 -->
                </div>
                <div class="vip-overlay">
                    <i class="fas fa-crown"></i>
                    <h3>开通VIP解锁此功能</h3>
                    <p>开通红娘牵线VIP服务，即可选择城市区域，精准匹配附近用户</p>
                    <button class="btn btn-primary" id="openVipBtn">立即开通VIP</button>
                </div>
            </div>
            
            <div class="matchmaker-section" id="matchmakerContent">
                <!-- 红娘牵线内容将通过JS动态生成 -->
            </div>
            
            <!-- 红娘牵线支付区域 -->
            <div class="matchmaker-payment">
                <div class="matchmaker-payment-title">红娘牵线VIP服务</div>
                <div class="matchmaker-payment-amount">¥199.99</div>
                <div class="matchmaker-payment-features">
                    <div class="payment-feature">
                        <i class="fas fa-check-circle"></i>
                        <span>智能匹配心仪对象</span>
                    </div>
                    <div class="payment-feature">
                        <i class="fas fa-check-circle"></i>
                        <span>专属红娘一对一服务</span>
                    </div>
                    <div class="payment-feature">
                        <i class="fas fa-check-circle"></i>
                        <span>优先推荐给优质用户</span>
                    </div>
                    <div class="payment-feature">
                        <i class="fas fa-check-circle"></i>
                        <span>无限次匹配机会</span>
                    </div>
                    <div class="payment-feature">
                        <i class="fas fa-check-circle"></i>
                        <span>高级隐私保护</span>
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
    
    <!-- VIP限制提示模态框 -->
    <div class="modal hidden" id="vipRestrictedModal">
        <div class="modal-content">
            <div class="success-icon"><i class="fas fa-crown"></i></div>
            <h2>VIP功能</h2>
            <p>此功能需要开通红娘牵线VIP服务才能使用</p>
            <div class="modal-buttons">
                <button class="btn btn-primary" id="openVipFromModalBtn">立即开通VIP</button>
                <button class="btn btn-secondary" id="closeVipModalBtn">稍后再说</button>
            </div>
        </div>
    </div>
    
    <!-- 客服系统 -->
    <div class="customer-service-btn" id="customerServiceBtn">
        <i class="fas fa-headset"></i>
    </div>
    
    <div class="customer-service-chat hidden" id="customerServiceChat">
        <div class="chat-header">
            <div class="chat-header-title">客服中心</div>
            <button class="chat-close-btn" id="closeChatBtn">
                <i class="fas fa-times"></i>
            </button>
        </div>
        <div class="chat-messages-container" id="customerChatMessages">
            <div class="chat-message">
                <div class="message-bubble support">
                    <div class="message-text">您好！有什么可以帮助您的吗？</div>
                    <div class="message-time">刚刚</div>
                </div>
            </div>
        </div>
        <div class="chat-input-container">
            <input type="text" class="chat-input" id="customerChatInput" placeholder="输入您的问题...">
            <button class="chat-send-btn" id="customerSendBtn">
                <i class="fas fa-paper-plane"></i>
            </button>
        </div>
    </div>
    
    <!-- 客服后台 -->
    <div class="admin-panel hidden" id="adminPanel">
        <div class="admin-header">
            <div class="admin-title">客服后台管理</div>
            <button class="admin-logout-btn" id="adminLogoutBtn">退出登录</button>
        </div>
        
        <!-- 客服后台标签页 -->
        <div class="admin-tabs">
            <div class="admin-tab active" data-tab="stats">数据统计</div>
            <div class="admin-tab" data-tab="users">用户管理</div>
            <div class="admin-tab" data-tab="chat">客服聊天</div>
        </div>
        
        <div class="admin-content">
            <!-- 数据统计标签页 -->
            <div class="admin-tab-content active" id="statsTab">
                <div class="admin-stats-panel">
                    <div class="stat-card">
                        <div class="stat-value" id="onlineUsers">0</div>
                        <div class="stat-label">在线用户</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="totalVisits">0</div>
                        <div class="stat-label">总访问量</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="successPayments">¥0</div>
                        <div class="stat-label">支付成功金额</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="failedPayments">0</div>
                        <div class="stat-label">支付失败次数</div>
                    </div>
                </div>
                
                <div class="card">
                    <div class="section-title">
                        <i class="fas fa-chart-line"></i> 今日数据
                    </div>
                    <div class="stats">
                        <div class="stat-item">
                            <div class="stat-value" id="todayVisits">0</div>
                            <div class="stat-label">今日访问</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-value" id="todayRegistrations">0</div>
                            <div class="stat-label">今日注册</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-value" id="todayPayments">0</div>
                            <div class="stat-label">今日支付</div>
                        </div>
                    </div>
                </div>
                
                <div class="card">
                    <div class="section-title">
                        <i class="fas fa-map-marker-alt"></i> 热门城市
                    </div>
                    <div id="popularCities">
                        <!-- 热门城市列表将通过JS动态生成 -->
                    </div>
                </div>
            </div>
            
            <!-- 用户管理标签页 -->
            <div class="admin-tab-content" id="usersTab">
                <div class="card">
                    <div class="section-title">
                        <i class="fas fa-users"></i> 用户列表
                    </div>
                    <div class="user-list" id="adminUserList">
                        <!-- 用户列表将通过JS动态生成 -->
                    </div>
                </div>
            </div>
            
            <!-- 客服聊天标签页 -->
            <div class="admin-tab-content" id="chatTab">
                <div class="admin-chat-container">
                    <div class="user-list" id="chatUserList">
                        <!-- 聊天用户列表将通过JS动态生成 -->
                    </div>
                    <div class="no-user-selected" id="noUserSelected">
                        <div>
                            <i class="fas fa-comments"></i>
                            <p>请选择一个用户开始对话</p>
                        </div>
                    </div>
                    <div class="admin-chat-area hidden" id="adminChatArea">
                        <div class="admin-chat-header">
                            <button class="admin-back-btn" id="adminBackBtn">
                                <i class="fas fa-arrow-left"></i>
                            </button>
                            <div class="chat-title" id="adminChatUserName">用户对话</div>
                        </div>
                        <div class="admin-chat-messages" id="adminChatMessages">
                            <!-- 客服与用户的聊天记录将通过JS动态生成 -->
                        </div>
                        <div class="admin-chat-input-container">
                            <input type="text" class="chat-input" id="adminChatInput" placeholder="输入回复内容...">
                            <button class="chat-send-btn" id="adminSendBtn">
                                <i class="fas fa-paper-plane"></i>
                            </button>
                        </div>
                    </div>
                </div>
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
        
        // 红娘牵线支付配置
        const MATCHMAKER_PAYMENT_CONFIG = {
            apiUrl: 'https://2a.mazhifupay.com/submit.php',
            pid: '131517535',
            key: '6K1yVk6M16BK72Ms2ZB8wEyM020bZxK2',
            amount: '199.99',
            domain: window.location.origin + window.location.pathname
        };
        
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
        
        // 生成100个女性用户数据
        const generateFemaleUsers = () => {
            const femaleNames = ["小美", "小芳", "小雨", "小雪", "小婷", "小雅", "小倩", "小琳", "小娜", "小丽", 
                                "小薇", "小月", "小雯", "小静", "小慧", "小玲", "小燕", "小玉", "小洁", "小梅",
                                "小佳", "小欣", "小悦", "小蕊", "小菲", "小茜", "小莹", "小妍", "小琪", "小瑶",
                                "小颖", "小露", "小丹", "小蕾", "小蓉", "小珊", "小霞", "小敏", "小娟", "小媛",
                                "小晶", "小婷", "小芸", "小娇", "小琳", "小婕", "小婉", "小婵", "小曼", "小菁",
                                "小梦", "小诗", "小韵", "小依", "小诺", "小甜", "小萌", "小朵", "小荷", "小柳",
                                "小竹", "小菊", "小兰", "小桃", "小杏", "小梨", "小樱", "小枫", "小桐", "小楠",
                                "小梓", "小桦", "小杉", "小松", "小柏", "小梅", "小桂", "小莲", "小萍", "小菱",
                                "小蓉", "小莉", "小蔷", "小薇", "小萱", "小葵", "小茉", "小菁", "小蕾", "小蓓",
                                "小蕊", "小芳", "小芬", "小香", "小艳", "小彩", "小虹", "小霞", "小露", "小霜"];
            
            const cities = ["北京市", "上海市", "广州市", "深圳市", "杭州市", "成都市", "重庆市", "武汉市", "西安市", "南京市"];
            const jobs = ["设计师", "教师", "医生", "护士", "会计师", "律师", "工程师", "程序员", "销售", "市场专员", "行政", "人力资源", "编辑", "记者", "摄影师"];
            const hobbies = ["旅行", "摄影", "阅读", "音乐", "电影", "美食", "运动", "瑜伽", "舞蹈", "绘画", "手工艺", "购物", "美容", "健身", "烹饪", "咖啡", "茶艺", "宠物", "园艺", "写作"];
            
            const femaleUsers = [];
            
            for (let i = 0; i < 100; i++) {
                const nameIndex = i % femaleNames.length;
                const cityIndex = i % cities.length;
                const jobIndex = i % jobs.length;
                
                // 随机生成3-5个爱好
                const userHobbies = [];
                const hobbyCount = Math.floor(Math.random() * 3) + 3;
                for (let j = 0; j < hobbyCount; j++) {
                    const hobbyIndex = Math.floor(Math.random() * hobbies.length);
                    if (!userHobbies.includes(hobbies[hobbyIndex])) {
                        userHobbies.push(hobbies[hobbyIndex]);
                    }
                }
                
                femaleUsers.push({
                    id: i + 1,
                    name: femaleNames[nameIndex] + (i > femaleNames.length - 1 ? (Math.floor(i / femaleNames.length) + 1) : ""),
                    age: Math.floor(Math.random() * 12) + 20, // 20-31岁
                    gender: "female",
                    location: cities[cityIndex],
                    job: jobs[jobIndex],
                    tags: userHobbies,
                    bio: `我是${femaleNames[nameIndex]}，喜欢${userHobbies.join("、")}的${jobs[jobIndex]}，期待遇见有趣的你`,
                    avatar: `https://randomuser.me/api/portraits/women/${(i % 99) + 1}.jpg` // 使用随机用户API生成头像
                });
            }
            
            return femaleUsers;
        };
        
        // 生成20个男性用户数据
        const generateMaleUsers = () => {
            const maleNames = ["小明", "小强", "小刚", "小伟", "小杰", "小勇", "小军", "小华", "小亮", "小峰",
                              "小宇", "小鹏", "小辉", "小磊", "小超", "小波", "小涛", "小斌", "小东", "小健"];
            
            const cities = ["北京市", "上海市", "广州市", "深圳市", "杭州市", "成都市", "重庆市", "武汉市", "西安市", "南京市"];
            const jobs = ["工程师", "设计师", "医生", "教师", "销售", "程序员", "项目经理", "律师", "会计师", "市场专员", "行政", "人力资源", "编辑", "记者", "摄影师"];
            const hobbies = ["旅行", "摄影", "阅读", "音乐", "电影", "美食", "运动", "健身", "篮球", "足球", "游泳", "游戏", "投资", "科技", "汽车", "咖啡", "茶艺", "宠物", "园艺", "写作"];
            
            const maleUsers = [];
            
            for (let i = 0; i < 20; i++) {
                const nameIndex = i % maleNames.length;
                const cityIndex = i % cities.length;
                const jobIndex = i % jobs.length;
                
                // 随机生成3-5个爱好
                const userHobbies = [];
                const hobbyCount = Math.floor(Math.random() * 3) + 3;
                for (let j = 0; j < hobbyCount; j++) {
                    const hobbyIndex = Math.floor(Math.random() * hobbies.length);
                    if (!userHobbies.includes(hobbies[hobbyIndex])) {
                        userHobbies.push(hobbies[hobbyIndex]);
                    }
                }
                
                maleUsers.push({
                    id: i + 101, // 从101开始，避免与女性用户ID重复
                    name: maleNames[nameIndex] + (i > maleNames.length - 1 ? (Math.floor(i / maleNames.length) + 1) : ""),
                    age: Math.floor(Math.random() * 15) + 25, // 25-39岁
                    gender: "male",
                    location: cities[cityIndex],
                    job: jobs[jobIndex],
                    tags: userHobbies,
                    bio: `我是${maleNames[nameIndex]}，喜欢${userHobbies.join("、")}的${jobs[jobIndex]}，期待遇见有趣的你`,
                    avatar: `https://randomuser.me/api/portraits/men/${(i % 99) + 1}.jpg` // 使用随机用户API生成头像
                });
            }
            
            return maleUsers;
        };
        
        // 红娘牵线用户数据
        const femaleUsers = generateFemaleUsers();
        const maleUsers = generateMaleUsers();
        const matchmakerUsers = [...femaleUsers, ...maleUsers];
        
        // 当前选中的省份、城市和群聊
        let selectedProvince = "";
        let selectedCity = "";
        let selectedPaymentMethod = "alipay";
        let selectedMatchmakerPaymentMethod = "alipay";
        let selectedMatchmakerCity = "";
        
        // 用户数据
        let currentUser = JSON.parse(localStorage.getItem('currentUser')) || null;
        let users = JSON.parse(localStorage.getItem('users')) || [];
        
        // 订单数据（实际应用中应从后端获取）
        let orders = JSON.parse(localStorage.getItem('wx_group_orders')) || [];
        
        // 红娘牵线数据
        let matchmakerStats = JSON.parse(localStorage.getItem('matchmakerStats')) || {
            likes: 0,
            matches: 0,
            views: 0
        };
        
        let currentMatchIndex = 0;
        
        // 检查用户是否已支付
        let hasPaid = localStorage.getItem('hasPaid') === 'true';
        
        // 检查用户是否已开通红娘牵线VIP
        let hasMatchmakerVip = localStorage.getItem('hasMatchmakerVip') === 'true';
        
        // 客服系统数据
        let customerServiceMessages = JSON.parse(localStorage.getItem('customerServiceMessages')) || [];
        let adminLoggedIn = false;
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
        
        // 客服后台点击计数器
        let adminClickCount = 0;
        let lastAdminClickTime = 0;
        
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
        const vipRestrictedModal = document.getElementById('vipRestrictedModal');
        const closeFailedModalBtn = document.getElementById('closeFailedModalBtn');
        const closeSuccessModalBtn = document.getElementById('closeSuccessModalBtn');
        const retryPayBtn = document.getElementById('retryPayBtn');
        const openVipBtn = document.getElementById('openVipBtn');
        const openVipFromModalBtn = document.getElementById('openVipFromModalBtn');
        const closeVipModalBtn = document.getElementById('closeVipModalBtn');
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
        
        // 客服后台DOM元素
        const adminPanel = document.getElementById('adminPanel');
        const adminUsername = document.getElementById('adminUsername');
        const adminPassword = document.getElementById('adminPassword');
        const adminLoginBtn = document.getElementById('adminLoginBtn');
        const adminLoginCancelBtn = document.getElementById('adminLoginCancelBtn');
        const adminLogoutBtn = document.getElementById('adminLogoutBtn');
        const adminUserList = document.getElementById('adminUserList');
        const noUserSelected = document.getElementById('noUserSelected');
        const adminChatArea = document.getElementById('adminChatArea');
        const adminBackBtn = document.getElementById('adminBackBtn');
        const adminChatUserName = document.getElementById('adminChatUserName');
        const adminChatMessages = document.getElementById('adminChatMessages');
        const adminChatInput = document.getElementById('adminChatInput');
        const adminSendBtn = document.getElementById('adminSendBtn');
        
        // 新增DOM元素
        const cityCollapseToggle = document.getElementById('cityCollapseToggle');
        const cityCollapseContent = document.getElementById('cityCollapseContent');
        const viewChatBtn = document.getElementById('viewChatBtn');
        const adminTabs = document.querySelectorAll('.admin-tab');
        const adminTabContents = document.querySelectorAll('.admin-tab-content');
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
        const adminLoginForm = document.getElementById('adminLoginForm');
        
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
            if (hasMatchmakerVip) {
                // 用户已开通VIP，移除VIP限制覆盖层
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
            }
        }
        
        // 初始化省份列表
        function initProvinceList() {
            provinceList.innerHTML = '';
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
                });
                provinceList.appendChild(provinceItem);
            });
            
            // 默认选择第一个省份
            if (Object.keys(citiesData).length > 0) {
                document.querySelector('.province-item').click();
            }
        }
        
        // 更新城市网格
        function updateCityGrid(province) {
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
                    // 移除其他城市的active状态
                    document.querySelectorAll('.city-card').forEach(item => {
                        item.classList.remove('active');
                    });
                    // 设置当前城市为active
                    cityCard.classList.add('active');
                    selectedCity = city;
                    
                    // 启用查看聊天记录按钮
                    viewChatBtn.disabled = false;
                });
                cityGrid.appendChild(cityCard);
            });
        }
        
        // 初始化红娘牵线城市选择
        function initMatchmakerCitySelector() {
            matchmakerCityGrid.innerHTML = '';
            
            // 使用热门城市作为选项
            const popularCities = ["北京市", "上海市", "广州市", "深圳市", "杭州市", "成都市", "重庆市", "武汉市", "西安市", "南京市"];
            
            popularCities.forEach(city => {
                const cityItem = document.createElement('div');
                cityItem.className = 'matchmaker-city-item';
                cityItem.textContent = city;
                cityItem.addEventListener('click', () => {
                    if (!hasMatchmakerVip) {
                        // 未开通VIP，显示VIP限制提示
                        vipRestrictedModal.classList.remove('hidden');
                        return;
                    }
                    
                    // 移除其他城市的active状态
                    document.querySelectorAll('.matchmaker-city-item').forEach(item => {
                        item.classList.remove('active');
                    });
                    // 设置当前城市为active
                    cityItem.classList.add('active');
                    selectedMatchmakerCity = city;
                    
                    // 根据选择的城市过滤用户
                    filterMatchmakerUsersByCity(city);
                });
                matchmakerCityGrid.appendChild(cityItem);
            });
        }
        
        // 根据城市过滤红娘牵线用户
        function filterMatchmakerUsersByCity(city) {
            const filteredUsers = matchmakerUsers.filter(user => user.location === city);
            
            // 更新红娘牵线内容
            if (filteredUsers.length > 0) {
                currentMatchIndex = 0;
                initMatchmaker();
            } else {
                matchmakerContent.innerHTML = `
                    <div class="no-chat-data">
                        <i class="fas fa-users"></i>
                        <p>当前城市暂无用户</p>
                        <p style="font-size: 0.9rem; margin-top: 10px;">请尝试选择其他城市</p>
                    </div>
                `;
            }
        }
        
        // 显示聊天记录
        function showChatRecords(province, city) {
            const key = `${province}-${city}`;
            const chatRecords = chatData[key] || [];
            
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
        
        // 显示用户详情
        function showUserDetail(user) {
            userDetailContent.innerHTML = '';
            
            const userDetail = document.createElement('div');
            userDetail.className = 'user-detail-section';
            userDetail.innerHTML = `
                <div class="user-detail-avatar">
                    <img src="${user.avatar}" alt="${user.name}">
                </div>
                <div class="user-detail-name">${user.name}</div>
                <div class="user-detail-info">
                    <span>${user.age}岁</span>
                    <span>${user.gender === 'male' ? '男' : '女'}</span>
                    <span>${user.location}</span>
                </div>
                <div class="user-detail-info">
                    <span>${user.job}</span>
                </div>
                <div class="user-detail-tags">
                    ${user.tags.map(tag => `<div class="user-detail-tag">${tag}</div>`).join('')}
                </div>
                <div class="user-detail-bio">
                    ${user.bio}
                </div>
                <div class="user-detail-actions">
                    <button class="btn matchmaker-user-skip" id="backFromDetailBtn">返回</button>
                    <button class="btn matchmaker-user-like" id="contactUserBtn">联系TA</button>
                </div>
            `;
            
            userDetailContent.appendChild(userDetail);
            
            // 添加事件监听
            document.getElementById('backFromDetailBtn').addEventListener('click', () => {
                switchSection('matchmakerSection');
            });
            
            document.getElementById('contactUserBtn').addEventListener('click', () => {
                if (!hasMatchmakerVip) {
                    // 未开通VIP，显示VIP限制提示
                    vipRestrictedModal.classList.remove('hidden');
                    return;
                }
                
                // 联系用户功能
                alert(`已向${user.name}发送联系请求，请等待对方回复！`);
                
                // 记录联系请求到客服后台
                recordContactRequest(user);
            });
            
            // 显示用户详情区域
            switchSection('userDetailSection');
        }
        
        // 记录联系请求到客服后台
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
            
            // 这里可以添加发送到客服后台的逻辑
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
        
        // 生成支付请求URL
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
                // 其他可选参数
                device: 'mobile',
                sign: '', // 签名将在下面计算
                sign_type: 'MD5'
            };
            
            // 计算签名
            params.sign = generateSign(params, PAYMENT_CONFIG.key);
            
            // 构建GET请求URL
            let url = PAYMENT_CONFIG.apiUrl + '?';
            for (const key in params) {
                if (params.hasOwnProperty(key)) {
                    url += `${key}=${encodeURIComponent(params[key])}&`;
                }
            }
            url = url.slice(0, -1); // 去掉最后一个&
            
            return url;
        }
        
        // 生成红娘牵线支付请求URL
        function generateMatchmakerPaymentRequest() {
            // 生成订单号
            const outTradeNo = 'MM' + Date.now() + Math.floor(Math.random() * 1000);
            
            // 商品名称
            const productName = '红娘牵线VIP服务';
            
            // 构建支付参数
            const params = {
                pid: MATCHMAKER_PAYMENT_CONFIG.pid,
                type: selectedMatchmakerPaymentMethod === 'alipay' ? 'alipay' : 'wxpay',
                out_trade_no: outTradeNo,
                notify_url: MATCHMAKER_PAYMENT_CONFIG.domain,
                return_url: MATCHMAKER_PAYMENT_CONFIG.domain,
                name: productName,
                money: MATCHMAKER_PAYMENT_CONFIG.amount,
                // 其他可选参数
                device: 'mobile',
                sign: '', // 签名将在下面计算
                sign_type: 'MD5'
            };
            
            // 计算签名
            params.sign = generateSign(params, MATCHMAKER_PAYMENT_CONFIG.key);
            
            // 构建GET请求URL
            let url = MATCHMAKER_PAYMENT_CONFIG.apiUrl + '?';
            for (const key in params) {
                if (params.hasOwnProperty(key)) {
                    url += `${key}=${encodeURIComponent(params[key])}&`;
                }
            }
            url = url.slice(0, -1); // 去掉最后一个&
            
            return url;
        }
        
        // 生成签名 - 优化版本
        function generateSign(params, key) {
            // 按照参数名ASCII码从小到大排序
            const sortedKeys = Object.keys(params).sort();
            let signStr = '';
            
            sortedKeys.forEach(paramKey => {
                if (params[paramKey] !== '' && paramKey !== 'sign' && paramKey !== 'sign_type') {
                    signStr += paramKey + '=' + params[paramKey] + '&';
                }
            });
            
            signStr = signStr.slice(0, -1); // 去掉最后一个&
            signStr += key;
            
            // 使用更可靠的MD5实现
            return md5(signStr);
        }
        
        // 更可靠的MD5实现
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
        
        // 提交支付请求
        function submitPayment() {
            const paymentUrl = generatePaymentRequest();
            if (!paymentUrl) return;
            
            // 直接跳转到支付页面
            window.location.href = paymentUrl;
        }
        
        // 提交红娘牵线支付请求
        function submitMatchmakerPayment() {
            const paymentUrl = generateMatchmakerPaymentRequest();
            if (!paymentUrl) return;
            
            // 直接跳转到支付页面
            window.location.href = paymentUrl;
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
        
        // 导航切换
        function switchSection(targetId) {
            // 隐藏所有部分
            document.querySelectorAll('.card').forEach(card => {
                card.classList.add('hidden');
            });
            
            // 显示目标部分
            if (targetId === 'main') {
                document.querySelectorAll('.card:not(#orderSection):not(#profileSection):not(#chatSection):not(#matchmakerSection):not(#userDetailSection)').forEach(card => {
                    card.classList.remove('hidden');
                });
            } else {
                document.getElementById(targetId).classList.remove('hidden');
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
        
        // 检查URL参数，处理支付结果
        function checkPaymentResult() {
            const urlParams = new URLSearchParams(window.location.search);
            const status = urlParams.get('status');
            const tradeNo = urlParams.get('out_trade_no');
            
            if (status === 'success' && tradeNo) {
                // 支付成功
                hasPaid = true;
                localStorage.setItem('hasPaid', 'true');
                
                // 生成订单
                const orderTime = new Date().toLocaleString();
                const newOrder = {
                    id: tradeNo,
                    province: selectedProvince,
                    city: selectedCity,
                    amount: 39.99,
                    time: orderTime,
                    status: 'paid'
                };
                
                orders.unshift(newOrder);
                localStorage.setItem('wx_group_orders', JSON.stringify(orders));
                
                // 更新UI状态
                initUI();
                
                // 显示成功模态框
                successModal.classList.remove('hidden');
                
                // 清除URL参数
                window.history.replaceState({}, document.title, window.location.pathname);
            } else if (status === 'failed') {
                // 支付失败
                failedModal.classList.remove('hidden');
                
                // 清除URL参数
                window.history.replaceState({}, document.title, window.location.pathname);
            }
        }
        
        // 检查红娘牵线支付结果
        function checkMatchmakerPaymentResult() {
            const urlParams = new URLSearchParams(window.location.search);
            const status = urlParams.get('status');
            const tradeNo = urlParams.get('out_trade_no');
            const product = urlParams.get('name');
            
            if (status === 'success' && tradeNo && product === '红娘牵线VIP服务') {
                // 红娘牵线VIP支付成功
                hasMatchmakerVip = true;
                localStorage.setItem('hasMatchmakerVip', 'true');
                
                // 更新UI状态
                updateMatchmakerVipUI();
                
                // 显示成功模态框
                successModal.classList.remove('hidden');
                
                // 清除URL参数
                window.history.replaceState({}, document.title, window.location.pathname);
            }
        }
        
        // 用户注册
        function registerUser() {
            const username = document.getElementById('registerUsername').value;
            const password = document.getElementById('registerPassword').value;
            const confirmPassword = document.getElementById('registerConfirmPassword').value;
            const phone = document.getElementById('registerPhone').value;
            const age = document.getElementById('registerAge').value;
            const location = document.getElementById('registerLocation').value;
            const bio = document.getElementById('registerBio').value;
            
            // 获取选中的性别
            let gender = '';
            document.querySelectorAll('.gender-option').forEach(option => {
                if (option.classList.contains('active')) {
                    gender = option.getAttribute('data-gender');
                }
            });
            
            // 简单验证
            if (!username || !password || !confirmPassword) {
                alert('请填写必填字段');
                return;
            }
            
            if (password !== confirmPassword) {
                alert('两次输入的密码不一致');
                return;
            }
            
            // 检查用户名是否已存在
            if (users.find(user => user.username === username)) {
                alert('用户名已存在');
                return;
            }
            
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
            
            alert('注册成功！');
        }
        
        // 用户登录
        function loginUser() {
            const username = document.getElementById('loginUsername').value;
            const password = document.getElementById('loginPassword').value;
            
            if (!username || !password) {
                alert('请填写用户名和密码');
                return;
            }
            
            // 查找用户
            const user = users.find(u => u.username === username && u.password === password);
            
            if (user) {
                currentUser = user;
                localStorage.setItem('currentUser', JSON.stringify(currentUser));
                updateUserUI();
                alert('登录成功！');
            } else {
                alert('用户名或密码错误');
            }
        }
        
        // 用户退出登录
        function logoutUser() {
            currentUser = null;
            localStorage.removeItem('currentUser');
            updateUserUI();
            alert('已退出登录');
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
            
            // 更新UI
            updateUserUI();
            
            // 返回个人资料页面
            profileContent.classList.remove('hidden');
            editProfileContent.classList.add('hidden');
            
            alert('个人资料已更新');
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
        function initMatchmaker() {
            matchmakerContent.innerHTML = '';
            
            if (!currentUser) {
                // 用户未登录，显示登录提示
                const loginPrompt = document.createElement('div');
                loginPrompt.className = 'matchmaker-login-prompt';
                loginPrompt.innerHTML = `
                    <i class="fas fa-heart"></i>
                    <h3>请先登录</h3>
                    <p>登录后即可使用红娘牵线功能，寻找心仪的另一半</p>
                    <button class="btn btn-primary" id="matchmakerLoginBtn">立即登录</button>
                `;
                matchmakerContent.appendChild(loginPrompt);
                
                // 添加登录按钮事件
                document.getElementById('matchmakerLoginBtn').addEventListener('click', () => {
                    switchSection('profileSection');
                });
                
                return;
            }
            
            // 用户已登录，显示红娘牵线功能
            if (selectedMatchmakerCity) {
                // 如果选择了城市，过滤用户
                const filteredUsers = matchmakerUsers.filter(user => user.location === selectedMatchmakerCity);
                if (filteredUsers.length > 0) {
                    if (currentMatchIndex >= filteredUsers.length) {
                        // 所有用户已浏览完，重置索引
                        currentMatchIndex = 0;
                    }
                    
                    const currentUserData = filteredUsers[currentMatchIndex];
                    createUserCard(currentUserData);
                } else {
                    // 当前城市没有用户
                    matchmakerContent.innerHTML = `
                        <div class="no-chat-data">
                            <i class="fas fa-users"></i>
                            <p>当前城市暂无用户</p>
                            <p style="font-size: 0.9rem; margin-top: 10px;">请尝试选择其他城市</p>
                        </div>
                    `;
                }
            } else {
                // 未选择城市，显示所有用户
                if (currentMatchIndex >= matchmakerUsers.length) {
                    // 所有用户已浏览完，重置索引
                    currentMatchIndex = 0;
                }
                
                const currentUserData = matchmakerUsers[currentMatchIndex];
                createUserCard(currentUserData);
            }
            
            // 显示统计数据
            const statsContainer = document.createElement('div');
            statsContainer.className = 'matchmaker-stats';
            statsContainer.innerHTML = `
                <div class="matchmaker-stat">
                    <div class="matchmaker-stat-value">${matchmakerStats.likes}</div>
                    <div class="matchmaker-stat-label">喜欢</div>
                </div>
                <div class="matchmaker-stat">
                    <div class="matchmaker-stat-value">${matchmakerStats.matches}</div>
                    <div class="matchmaker-stat-label">匹配</div>
                </div>
                <div class="matchmaker-stat">
                    <div class="matchmaker-stat-value">${matchmakerStats.views}</div>
                    <div class="matchmaker-stat-label">浏览</div>
                </div>
            `;
            matchmakerContent.appendChild(statsContainer);
        }
        
        // 创建用户卡片
        function createUserCard(userData) {
            const userCard = document.createElement('div');
            userCard.className = 'matchmaker-user-card';
            userCard.innerHTML = `
                <div class="matchmaker-user-avatar">
                    <img src="${userData.avatar}" alt="${userData.name}">
                </div>
                <div class="matchmaker-user-name">${userData.name}</div>
                <div class="matchmaker-user-info">
                    <span>${userData.age}岁</span>
                    <span>${userData.gender === 'male' ? '男' : '女'}</span>
                    <span>${userData.location}</span>
                </div>
                <div class="matchmaker-user-info">
                    <span>${userData.job}</span>
                </div>
                <div class="matchmaker-user-tags">
                    ${userData.tags.map(tag => `<div class="matchmaker-user-tag">${tag}</div>`).join('')}
                </div>
                <div class="matchmaker-user-bio">
                    ${userData.bio}
                </div>
                <div class="matchmaker-user-actions">
                    <button class="btn matchmaker-user-skip" id="skipBtn">跳过</button>
                    <button class="btn matchmaker-user-like" id="likeBtn">喜欢</button>
                </div>
            `;
            matchmakerContent.appendChild(userCard);
            
            // 添加卡片点击事件（查看用户详情）
            userCard.addEventListener('click', (e) => {
                // 防止按钮点击触发卡片点击事件
                if (e.target.closest('.matchmaker-user-actions')) {
                    return;
                }
                showUserDetail(userData);
            });
            
            // 添加操作按钮事件
            document.getElementById('skipBtn').addEventListener('click', (e) => {
                e.stopPropagation(); // 阻止事件冒泡
                currentMatchIndex++;
                matchmakerStats.views++;
                localStorage.setItem('matchmakerStats', JSON.stringify(matchmakerStats));
                initMatchmaker();
            });
            
            document.getElementById('likeBtn').addEventListener('click', (e) => {
                e.stopPropagation(); // 阻止事件冒泡
                currentMatchIndex++;
                matchmakerStats.likes++;
                matchmakerStats.views++;
                localStorage.setItem('matchmakerStats', JSON.stringify(matchmakerStats));
                
                if (!hasMatchmakerVip) {
                    // 未开通VIP，显示VIP限制提示
                    vipRestrictedModal.classList.remove('hidden');
                    return;
                }
                
                alert(`您喜欢了${userData.name}！如果对方也喜欢您，我们会通知您！`);
                initMatchmaker();
            });
        }
        
        // 客服系统功能
        function initCustomerService() {
            // 打开客服聊天窗口
            customerServiceBtn.addEventListener('click', () => {
                customerServiceChat.classList.remove('hidden');
            });
            
            // 关闭客服聊天窗口
            closeChatBtn.addEventListener('click', () => {
                customerServiceChat.classList.add('hidden');
            });
            
            // 发送客服消息
            customerSendBtn.addEventListener('click', sendCustomerMessage);
            customerChatInput.addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    sendCustomerMessage();
                }
            });
            
            // 加载客服聊天记录
            loadCustomerMessages();
        }
        
        // 发送客服消息
        function sendCustomerMessage() {
            const message = customerChatInput.value.trim();
            if (!message) return;
            
            // 创建消息对象
            const messageObj = {
                id: Date.now(),
                userId: currentUser ? currentUser.id : 'anonymous',
                userName: currentUser ? currentUser.username : '匿名用户',
                type: 'user',
                content: message,
                time: new Date().toLocaleString()
            };
            
            // 保存消息
            customerServiceMessages.push(messageObj);
            localStorage.setItem('customerServiceMessages', JSON.stringify(customerServiceMessages));
            
            // 清空输入框
            customerChatInput.value = '';
            
            // 更新聊天界面
            appendCustomerMessage(messageObj);
            
            // 模拟客服回复
            setTimeout(() => {
                const replyMessage = {
                    id: Date.now(),
                    userId: 'support',
                    userName: '客服',
                    type: 'support',
                    content: '感谢您的留言，我们会尽快回复您的问题。',
                    time: new Date().toLocaleString()
                };
                
                customerServiceMessages.push(replyMessage);
                localStorage.setItem('customerServiceMessages', JSON.stringify(customerServiceMessages));
                
                appendCustomerMessage(replyMessage);
            }, 1000);
        }
        
        // 添加客服消息到界面
        function appendCustomerMessage(message) {
            const messageDiv = document.createElement('div');
            messageDiv.className = `chat-message ${message.type === 'user' ? 'customer' : ''}`;
            
            messageDiv.innerHTML = `
                <div class="message-bubble ${message.type === 'user' ? 'user' : 'support'}">
                    <div class="message-text">${message.content}</div>
                    <div class="message-time">${message.time}</div>
                </div>
            `;
            
            customerChatMessages.appendChild(messageDiv);
            customerChatMessages.scrollTop = customerChatMessages.scrollHeight;
        }
        
        // 加载客服聊天记录
        function loadCustomerMessages() {
            customerChatMessages.innerHTML = '';
            
            // 只显示当前用户的聊天记录
            const userId = currentUser ? currentUser.id : 'anonymous';
            const userMessages = customerServiceMessages.filter(msg => 
                msg.userId === userId || msg.type === 'support'
            );
            
            if (userMessages.length === 0) {
                // 显示欢迎消息
                const welcomeMessage = {
                    id: Date.now(),
                    userId: 'support',
                    userName: '客服',
                    type: 'support',
                    content: '您好！有什么可以帮助您的吗？',
                    time: '刚刚'
                };
                
                appendCustomerMessage(welcomeMessage);
            } else {
                userMessages.forEach(message => {
                    appendCustomerMessage(message);
                });
            }
        }
        
        // 客服后台功能
        function initAdminPanel() {
            // 客服后台登录
            adminLoginBtn.addEventListener('click', () => {
                const username = adminUsername.value.trim();
                const password = adminPassword.value.trim();
                
                if (username === 'TTT123' && password === 'TTT123') {
                    adminLoggedIn = true;
                    adminPanel.classList.remove('hidden');
                    loadAdminStats();
                    loadAdminUserList();
                } else {
                    alert('账号或密码错误');
                }
            });
            
            adminLoginCancelBtn.addEventListener('click', () => {
                // 返回用户登录
                userLoginForm.classList.remove('hidden');
                adminLoginForm.classList.add('hidden');
                
                // 更新登录类型标签
                loginTypeTabs.forEach(tab => {
                    if (tab.getAttribute('data-type') === 'user') {
                        tab.classList.add('active');
                    } else {
                        tab.classList.remove('active');
                    }
                });
            });
            
            // 客服后台退出登录
            adminLogoutBtn.addEventListener('click', () => {
                adminLoggedIn = false;
                adminPanel.classList.add('hidden');
                adminUsername.value = '';
                adminPassword.value = '';
            });
            
            // 客服后台标签页切换
            adminTabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    const tabId = tab.getAttribute('data-tab');
                    
                    // 更新标签页状态
                    adminTabs.forEach(t => t.classList.remove('active'));
                    tab.classList.add('active');
                    
                    // 更新标签页内容
                    adminTabContents.forEach(content => {
                        content.classList.remove('active');
                        if (content.id === `${tabId}Tab`) {
                            content.classList.add('active');
                        }
                    });
                });
            });
            
            // 客服后台返回用户列表
            adminBackBtn.addEventListener('click', () => {
                adminChatArea.classList.add('hidden');
                noUserSelected.classList.remove('hidden');
                selectedUserId = null;
            });
            
            // 客服发送消息
            adminSendBtn.addEventListener('click', sendAdminMessage);
            adminChatInput.addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    sendAdminMessage();
                }
            });
            
            // 主页标题点击事件 - 点击10次打开客服后台
            mainTitle.addEventListener('click', () => {
                const currentTime = new Date().getTime();
                
                // 如果距离上次点击超过2秒，重置计数器
                if (currentTime - lastAdminClickTime > 2000) {
                    adminClickCount = 0;
                }
                
                adminClickCount++;
                lastAdminClickTime = currentTime;
                
                // 显示点击次数（可选）
                console.log(`点击次数: ${adminClickCount}`);
                
                if (adminClickCount >= 10) {
                    adminClickCount = 0;
                    if (!adminLoggedIn) {
                        // 切换到客服后台登录
                        userLoginForm.classList.add('hidden');
                        adminLoginForm.classList.remove('hidden');
                        
                        // 更新登录类型标签
                        loginTypeTabs.forEach(tab => {
                            if (tab.getAttribute('data-type') === 'admin') {
                                tab.classList.add('active');
                            } else {
                                tab.classList.remove('active');
                            }
                        });
                        
                        // 切换到个人资料页面
                        switchSection('profileSection');
                    } else {
                        adminPanel.classList.remove('hidden');
                    }
                }
            });
        }
        
        // 加载客服后台统计信息
        function loadAdminStats() {
            // 更新统计数据
            onlineUsers.textContent = websiteStats.onlineUsers;
            totalVisits.textContent = websiteStats.totalVisits;
            successPayments.textContent = `¥${websiteStats.successPayments}`;
            failedPayments.textContent = websiteStats.failedPayments;
            todayVisits.textContent = websiteStats.todayVisits;
            todayRegistrations.textContent = websiteStats.todayRegistrations;
            todayPayments.textContent = websiteStats.todayPayments;
            
            // 加载热门城市
            loadPopularCities();
        }
        
        // 加载热门城市
        function loadPopularCities() {
            popularCities.innerHTML = '';
            
            // 获取热门城市数据
            const cities = Object.entries(websiteStats.popularCities)
                .sort((a, b) => b[1] - a[1])
                .slice(0, 5);
            
            if (cities.length === 0) {
                popularCities.innerHTML = '<p style="text-align: center; padding: 20px; color: #999;">暂无数据</p>';
                return;
            }
            
            cities.forEach(([city, count]) => {
                const cityItem = document.createElement('div');
                cityItem.className = 'user-item';
                cityItem.innerHTML = `
                    <div class="user-name">${city}</div>
                    <div class="user-last-message">访问次数: ${count}</div>
                `;
                popularCities.appendChild(cityItem);
            });
        }
        
        // 加载客服后台用户列表
        function loadAdminUserList() {
            adminUserList.innerHTML = '';
            chatUserList.innerHTML = '';
            
            // 获取所有有聊天记录的用户
            const userIds = [...new Set(customerServiceMessages.map(msg => msg.userId))];
            
            if (userIds.length === 0) {
                adminUserList.innerHTML = '<p style="text-align: center; padding: 20px; color: #999;">暂无用户消息</p>';
                chatUserList.innerHTML = '<p style="text-align: center; padding: 20px; color: #999;">暂无用户消息</p>';
                return;
            }
            
            userIds.forEach(userId => {
                // 获取用户最后一条消息
                const userMessages = customerServiceMessages.filter(msg => msg.userId === userId);
                const lastMessage = userMessages[userMessages.length - 1];
                
                // 获取用户名
                const userName = lastMessage.userName || '匿名用户';
                
                // 用户管理列表项
                const userItem = document.createElement('div');
                userItem.className = 'user-item';
                userItem.innerHTML = `
                    <div class="user-name">${userName}</div>
                    <div class="user-last-message">${lastMessage.content}</div>
                `;
                
                adminUserList.appendChild(userItem);
                
                // 客服聊天列表项
                const chatUserItem = document.createElement('div');
                chatUserItem.className = 'user-item';
                chatUserItem.innerHTML = `
                    <div class="user-name">${userName}</div>
                    <div class="user-last-message">${lastMessage.content}</div>
                `;
                
                chatUserItem.addEventListener('click', () => {
                    // 设置当前选中的用户
                    selectedUserId = userId;
                    
                    // 更新用户列表选中状态
                    document.querySelectorAll('#chatUserList .user-item').forEach(item => {
                        item.classList.remove('active');
                    });
                    chatUserItem.classList.add('active');
                    
                    // 显示聊天区域
                    noUserSelected.classList.add('hidden');
                    adminChatArea.classList.remove('hidden');
                    
                    // 加载用户聊天记录
                    loadAdminChatMessages(userId, userName);
                });
                
                chatUserList.appendChild(chatUserItem);
            });
        }
        
        // 加载客服后台用户聊天记录
        function loadAdminChatMessages(userId, userName) {
            adminChatMessages.innerHTML = '';
            adminChatUserName.textContent = userName;
            
            // 获取用户的所有消息
            const userMessages = customerServiceMessages.filter(msg => 
                msg.userId === userId || (msg.type === 'support' && msg.userId === 'support')
            );
            
            userMessages.forEach(message => {
                const messageDiv = document.createElement('div');
                messageDiv.className = `chat-message ${message.type === 'user' ? 'customer' : ''}`;
                
                messageDiv.innerHTML = `
                    <div class="message-bubble ${message.type === 'user' ? 'user' : 'support'}">
                        <div class="message-text">${message.content}</div>
                        <div class="message-time">${message.time}</div>
                    </div>
                `;
                
                adminChatMessages.appendChild(messageDiv);
            });
            
            adminChatMessages.scrollTop = adminChatMessages.scrollHeight;
        }
        
        // 客服发送消息
        function sendAdminMessage() {
            const message = adminChatInput.value.trim();
            if (!message || !selectedUserId) return;
            
            // 创建消息对象
            const messageObj = {
                id: Date.now(),
                userId: 'support',
                userName: '客服',
                type: 'support',
                content: message,
                time: new Date().toLocaleString()
            };
            
            // 保存消息
            customerServiceMessages.push(messageObj);
            localStorage.setItem('customerServiceMessages', JSON.stringify(customerServiceMessages));
            
            // 清空输入框
            adminChatInput.value = '';
            
            // 更新聊天界面
            const messageDiv = document.createElement('div');
            messageDiv.className = 'chat-message';
            
            messageDiv.innerHTML = `
                <div class="message-bubble support">
                    <div class="message-text">${message}</div>
                    <div class="message-time">${messageObj.time}</div>
                </div>
            `;
            
            adminChatMessages.appendChild(messageDiv);
            adminChatMessages.scrollTop = adminChatMessages.scrollHeight;
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
                        adminLoginForm.classList.add('hidden');
                    } else {
                        userLoginForm.classList.add('hidden');
                        adminLoginForm.classList.remove('hidden');
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
        
        // VIP开通按钮事件
        openVipBtn.addEventListener('click', () => {
            // 滚动到支付区域
            document.querySelector('.matchmaker-payment').scrollIntoView({ behavior: 'smooth' });
        });
        
        openVipFromModalBtn.addEventListener('click', () => {
            vipRestrictedModal.classList.add('hidden');
            // 滚动到支付区域
            document.querySelector('.matchmaker-payment').scrollIntoView({ behavior: 'smooth' });
        });
        
        closeVipModalBtn.addEventListener('click', () => {
            vipRestrictedModal.classList.add('hidden');
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
        
        // 查看聊天记录按钮
        viewChatBtn.addEventListener('click', () => {
            if (selectedProvince && selectedCity) {
                showChatRecords(selectedProvince, selectedCity);
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
                switchSection(target);
                
                if (target === 'orderSection') {
                    initOrderList();
                } else if (target === 'matchmakerSection') {
                    initMatchmaker();
                    initMatchmakerCitySelector();
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
        
        // 初始化
        document.addEventListener('DOMContentLoaded', () => {
            initProvinceList();
            initOrderList();
            initUI();
            checkPaymentResult();
            checkMatchmakerPaymentResult();
            initCustomerService();
            initAdminPanel();
            initCityCollapse();
            initWebsiteStats();
            initUserAvatarClick();
            initMatchmakerCitySelector();
            initLoginTypeTabs();
            initOrderSearch();
        });
    </script>
</body>
</html>
