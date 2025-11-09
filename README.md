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
        
        .city-list {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
            max-height: 300px;
            overflow-y: auto;
            padding: 5px;
        }
        
        .city-item {
            padding: 15px 10px;
            text-align: center;
            background: linear-gradient(to bottom, #f8f8f8, #f0f0f0);
            border-radius: 12px;
            font-size: 0.9rem;
            transition: all 0.3s;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
            border: 1px solid rgba(255, 75, 145, 0.1);
        }
        
        .city-item.active {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            box-shadow: 0 4px 10px rgba(255, 75, 145, 0.3);
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
            box-shadow: 0 8px 20px rgba(255, 75, 145, 0.3);
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
            background: rgba(255, 75, 145, 0.05);
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
        
        .floating-action {
            position: fixed;
            bottom: 80px;
            right: 20px;
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
            box-shadow: 0 4px 20px rgba(255, 75, 145, 0.4);
            z-index: 99;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { box-shadow: 0 4px 20px rgba(255, 75, 145, 0.4); }
            50% { box-shadow: 0 4px 25px rgba(255, 75, 145, 0.7); }
            100% { box-shadow: 0 4px 20px rgba(255, 75, 145, 0.4); }
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
            box-shadow: 0 0 0 3px rgba(255, 75, 145, 0.1);
        }
        
        .success-section {
            text-align: center;
            padding: 20px 0;
        }
        
        #paymentForm {
            display: none;
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
            box-shadow: 0 8px 20px rgba(255, 75, 145, 0.3);
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
        }
        
        .gender-option.active {
            border-color: var(--primary);
            background: rgba(255, 75, 145, 0.05);
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
            background: rgba(255, 75, 145, 0.05);
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
            border: 1px solid rgba(255, 75, 145, 0.1);
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
        }
        
        .collapse-header:hover {
            background: rgba(255, 75, 145, 0.05);
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
            border-bottom: 1px solid rgba(255, 75, 145, 0.1);
        }
        
        .back-button {
            background: none;
            border: none;
            font-size: 1.2rem;
            color: var(--primary);
            cursor: pointer;
            margin-right: 15px;
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
            border: 1px solid rgba(255, 75, 145, 0.1);
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
        
        /* 优化城市选择样式 */
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
            border: 1px solid rgba(255, 75, 145, 0.1);
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
            box-shadow: 0 8px 20px rgba(255, 75, 145, 0.3);
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
            background: rgba(255, 75, 145, 0.1);
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
            background: rgba(255, 75, 145, 0.05);
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
            background: linear-gradient(135deg, #fff9fb 0%, #ffeef6 100%);
            border-radius: 20px;
            padding: 25px;
            margin: 20px 0;
            text-align: center;
            border: 1px solid rgba(255, 75, 145, 0.1);
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
        }
        
        .matchmaker-payment-method.active {
            border-color: var(--primary);
            background: rgba(255, 75, 145, 0.05);
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
    </style>
</head>
<body>
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
            domain: 'https://tudpu123.github.io/tcq.CCCC/'
        };
        
        // 红娘牵线支付配置
        const MATCHMAKER_PAYMENT_CONFIG = {
            apiUrl: 'https://2a.mazhifupay.com/submit.php',
            pid: '131517535',
            key: '6K1yVk6M16BK72Ms2ZB8wEyM020bZxK2',
            amount: '199.99',
            domain: 'https://tudpu123.github.io/tcq.CCCC/'
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
        
        // 红娘牵线用户数据
        const matchmakerUsers = [
            {
                id: 1,
                name: "小美",
                age: 25,
                gender: "female",
                location: "北京市",
                job: "设计师",
                tags: ["摄影", "旅行", "美食"],
                bio: "喜欢旅行和摄影的文艺女青年，寻找志同道合的你",
                avatar: null
            },
            {
                id: 2,
                name: "小李",
                age: 28,
                gender: "male",
                location: "上海市",
                job: "工程师",
                tags: ["运动", "科技", "音乐"],
                bio: "热爱生活的IT男，期待遇见有趣的灵魂",
                avatar: null
            },
            {
                id: 3,
                name: "小芳",
                age: 26,
                gender: "female",
                location: "广州市",
                job: "教师",
                tags: ["阅读", "瑜伽", "电影"],
                bio: "温柔善良的小学老师，希望找到有责任心的另一半",
                avatar: null
            },
            {
                id: 4,
                name: "小王",
                age: 30,
                gender: "male",
                location: "深圳市",
                job: "创业者",
                tags: ["创业", "投资", "健身"],
                bio: "积极向上的创业者，寻找能一起奋斗的伴侣",
                avatar: null
            }
        ];
        
        // 当前选中的省份、城市和群聊
        let selectedProvince = "";
        let selectedCity = "";
        let selectedPaymentMethod = "alipay";
        let selectedMatchmakerPaymentMethod = "alipay";
        
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
        const orderList = document.getElementById('orderList');
        const backBtn = document.getElementById('backBtn');
        const chatBackBtn = document.getElementById('chatBackBtn');
        const chatTitle = document.getElementById('chatTitle');
        const chatContent = document.getElementById('chatContent');
        const matchmakerContent = document.getElementById('matchmakerContent');
        const processingModal = document.getElementById('processingModal');
        const failedModal = document.getElementById('failedModal');
        const successModal = document.getElementById('successModal');
        const closeFailedModalBtn = document.getElementById('closeFailedModalBtn');
        const closeSuccessModalBtn = document.getElementById('closeSuccessModalBtn');
        const retryPayBtn = document.getElementById('retryPayBtn');
        const navItems = document.querySelectorAll('.nav-item');
        const paymentMethods = document.querySelectorAll('.payment-method');
        const alipayForm = document.getElementById('alipayForm');
        const wxpayForm = document.getElementById('wxpayForm');
        const paymentForm = document.getElementById('paymentForm');
        
        // 红娘牵线支付相关DOM元素
        const matchmakerPaymentMethods = document.querySelectorAll('.matchmaker-payment-method');
        const matchmakerAlipayForm = document.getElementById('matchmakerAlipayForm');
        const matchmakerWxpayForm = document.getElementById('matchmakerWxpayForm');
        const matchmakerAlipayBtn = document.getElementById('matchmakerAlipayBtn');
        const matchmakerWxpayBtn = document.getElementById('matchmakerWxpayBtn');
        const matchmakerPaymentForm = document.getElementById('matchmakerPaymentForm');
        
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
                    
                    // 显示该城市的聊天记录
                    showChatRecords(province, city);
                });
                cityGrid.appendChild(cityCard);
            });
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
        
        // 生成支付请求
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
                notify_url: PAYMENT_CONFIG.domain + 'payment_notify.html',
                return_url: PAYMENT_CONFIG.domain + 'payment_success.html',
                name: productName,
                money: '39.99',
                // 其他可选参数
                device: 'mobile',
                sign: '', // 签名将在下面计算
                sign_type: 'MD5'
            };
            
            // 计算签名
            params.sign = generateSign(params, PAYMENT_CONFIG.key);
            
            return params;
        }
        
        // 生成红娘牵线支付请求
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
                notify_url: MATCHMAKER_PAYMENT_CONFIG.domain + 'payment_notify.html',
                return_url: MATCHMAKER_PAYMENT_CONFIG.domain + 'payment_success.html',
                name: productName,
                money: MATCHMAKER_PAYMENT_CONFIG.amount,
                // 其他可选参数
                device: 'mobile',
                sign: '', // 签名将在下面计算
                sign_type: 'MD5'
            };
            
            // 计算签名
            params.sign = generateSign(params, MATCHMAKER_PAYMENT_CONFIG.key);
            
            return params;
        }
        
        // 生成签名 - 优化版本
        function generateSign(params, key) {
            // 按照参数名ASCII码从小到大排序
            const sortedKeys = Object.keys(params).sort();
            let signStr = '';
            
            sortedKeys.forEach(key => {
                if (params[key] !== '' && key !== 'sign' && key !== 'sign_type') {
                    signStr += key + '=' + params[key] + '&';
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
            
            // 提交表单到支付平台
            setTimeout(() => {
                paymentForm.submit();
            }, 1000);
        }
        
        // 提交红娘牵线支付请求
        function submitMatchmakerPayment() {
            const paymentParams = generateMatchmakerPaymentRequest();
            if (!paymentParams) return;
            
            // 显示处理中模态框
            processingModal.classList.remove('hidden');
            
            // 填充支付表单
            document.getElementById('matchmakerPid').value = paymentParams.pid;
            document.getElementById('matchmakerType').value = paymentParams.type;
            document.getElementById('matchmakerOutTradeNo').value = paymentParams.out_trade_no;
            document.getElementById('matchmakerNotifyUrl').value = paymentParams.notify_url;
            document.getElementById('matchmakerReturnUrl').value = paymentParams.return_url;
            document.getElementById('matchmakerName').value = paymentParams.name;
            document.getElementById('matchmakerMoney').value = paymentParams.money;
            document.getElementById('matchmakerDevice').value = paymentParams.device;
            document.getElementById('matchmakerSign').value = paymentParams.sign;
            document.getElementById('matchmakerSignType').value = paymentParams.sign_type;
            
            // 提交表单到支付平台
            setTimeout(() => {
                matchmakerPaymentForm.submit();
            }, 1000);
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
                document.querySelectorAll('.card:not(#orderSection):not(#profileSection):not(#chatSection):not(#matchmakerSection)').forEach(card => {
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
            if (currentMatchIndex >= matchmakerUsers.length) {
                // 所有用户已浏览完，重置索引
                currentMatchIndex = 0;
            }
            
            const currentUserData = matchmakerUsers[currentMatchIndex];
            
            // 创建用户卡片
            const userCard = document.createElement('div');
            userCard.className = 'matchmaker-card';
            userCard.innerHTML = `
                <div class="matchmaker-avatar">
                    <i class="fas fa-user"></i>
                </div>
                <div class="matchmaker-name">${currentUserData.name}</div>
                <div class="matchmaker-info">
                    <span>${currentUserData.age}岁</span>
                    <span>${currentUserData.gender === 'male' ? '男' : '女'}</span>
                    <span>${currentUserData.location}</span>
                </div>
                <div class="matchmaker-info">
                    <span>${currentUserData.job}</span>
                </div>
                <div class="matchmaker-tags">
                    ${currentUserData.tags.map(tag => `<div class="matchmaker-tag">${tag}</div>`).join('')}
                </div>
                <div class="tips">
                    ${currentUserData.bio}
                </div>
                <div class="matchmaker-actions">
                    <button class="btn matchmaker-skip" id="skipBtn">跳过</button>
                    <button class="btn matchmaker-like" id="likeBtn">喜欢</button>
                </div>
            `;
            matchmakerContent.appendChild(userCard);
            
            // 添加操作按钮事件
            document.getElementById('skipBtn').addEventListener('click', () => {
                currentMatchIndex++;
                matchmakerStats.views++;
                localStorage.setItem('matchmakerStats', JSON.stringify(matchmakerStats));
                initMatchmaker();
            });
            
            document.getElementById('likeBtn').addEventListener('click', () => {
                currentMatchIndex++;
                matchmakerStats.likes++;
                matchmakerStats.views++;
                localStorage.setItem('matchmakerStats', JSON.stringify(matchmakerStats));
                alert(`您喜欢了${currentUserData.name}！如果对方也喜欢您，我们会通知您！`);
                initMatchmaker();
            });
            
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
        
        // 事件监听
        alipayBtn.addEventListener('click', submitPayment);
        wxpayBtn.addEventListener('click', submitPayment);
        retryPayBtn.addEventListener('click', submitPayment);
        
        // 红娘牵线支付按钮事件
        matchmakerAlipayBtn.addEventListener('click', submitMatchmakerPayment);
        matchmakerWxpayBtn.addEventListener('click', submitMatchmakerPayment);
        
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
        
        closeFailedModalBtn.addEventListener('click', () => {
            failedModal.classList.add('hidden');
        });
        
        closeSuccessModalBtn.addEventListener('click', () => {
            successModal.classList.add('hidden');
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
        });
    </script>
</body>
</html>
