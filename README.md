<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>XRO VPN | فروشگاه کانفیگ اختصاصی</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* استایل‌های پایه و متغیرهای جدید */
        :root {
            --primary: #6e45e2;
            --primary-dark: #4a2bbd;
            --secondary: #88d3ce;
            --secondary-dark: #50c9c3;
            --accent: #ff7e5f;
            --accent-dark: #f95a3b;
            --dark: #0f0f1a;
            --darker: #0a0a12;
            --dark-light: #1a1a2e;
            --light: rgba(255,255,255,0.95);
            --lighter: rgba(255,255,255,0.7);
            --neon-shadow: 0 0 15px rgba(110, 69, 226, 0.5);
            --radius: 16px;
            --radius-sm: 10px;
            --shadow: 0 8px 20px rgba(0,0,0,0.3);
            --shadow-lg: 0 15px 40px rgba(0,0,0,0.4);
            --transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
            --transition-slow: all 0.5s cubic-bezier(0.25, 0.8, 0.25, 1);
            --phone-color: #4CAF50;
            --phone-dark: #2E7D32;
            --modem-color: #2196F3;
            --modem-dark: #1565C0;
            --affiliate-color: #9C27B0;
            --affiliate-dark: #7B1FA2;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Yekan', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: var(--darker);
            color: #f0f0f0;
            overflow-x: hidden;
            line-height: 1.6;
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(110, 69, 226, 0.1) 0%, transparent 20%),
                radial-gradient(circle at 90% 80%, rgba(136, 211, 206, 0.1) 0%, transparent 20%);
        }

        /* صفحه لودینگ بهبود یافته */
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--darker);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            overflow: hidden;
        }
        
        .logo-container {
            text-align: center;
            margin-bottom: 80px;
            margin-top: -30px;
            animation: fadeIn 1s both;
            position: relative;
        }
        
        .logo-text {
            font-size: 48px;
            font-weight: bold;
            display: flex;
            justify-content: center;
            gap: 15px;
            text-shadow: var(--neon-shadow);
            position: relative;
        }
        
        .mr {
            color: var(--secondary);
            opacity: 0;
            animation: slideInRight 0.8s forwards 0.3s;
        }
        
        .xero {
            color: var(--primary);
            opacity: 0;
            animation: slideInLeft 0.8s forwards 0.3s;
        }
        
        .logo-container::before {
            content: '';
            position: absolute;
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, rgba(110, 69, 226, 0.3) 0%, transparent 70%);
            border-radius: 50%;
            filter: blur(20px);
            animation: pulse 4s infinite alternate;
        }
        
        @keyframes pulse {
            0% { transform: scale(0.8); opacity: 0.5; }
            100% { transform: scale(1.2); opacity: 0.8; }
        }
        
        @keyframes slideInRight {
            0% { transform: translateX(100px); opacity: 0; }
            100% { transform: translateX(0); opacity: 1; }
        }
        
        @keyframes slideInLeft {
            0% { transform: translateX(-100px); opacity: 0; }
            100% { transform: translateX(0); opacity: 1; }
        }
        
        @keyframes slideOutRight {
            0% { transform: translateX(0); opacity: 1; }
            100% { transform: translateX(100px); opacity: 0; }
        }
        
        @keyframes slideOutLeft {
            0% { transform: translateX(0); opacity: 1; }
            100% { transform: translateX(-100px); opacity: 0; }
        }
        
        .loading-footer {
            position: absolute;
            bottom: 120px;
            width: 80%;
            max-width: 500px;
            animation: fadeIn 1s both 0.5s;
        }
        
        .waiting-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .waiting-text {
            font-size: 18px;
            color: var(--secondary);
            display: flex;
            align-items: center;
        }
        
        .dot {
            opacity: 0;
            animation: dotAnimation 1.5s infinite;
            margin-right: 2px;
        }
        
        .dot:nth-child(1) { animation-delay: 0.2s; }
        .dot:nth-child(2) { animation-delay: 0.4s; }
        .dot:nth-child(3) { animation-delay: 0.6s; }
        
        @keyframes dotAnimation {
            0%, 100% { opacity: 0; }
            50% { opacity: 1; }
        }
        
        .loading-bar-container {
            width: 100%;
            height: 15px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 8px;
            overflow: hidden;
            margin-bottom: 8px;
            box-shadow: 0 0 15px rgba(110, 69, 226, 0.3);
            position: relative;
        }
        
        .loading-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            width: 0%;
            transition: width 0.3s;
            border-radius: 8px;
            position: relative;
            overflow: hidden;
        }
        
        .loading-bar::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255, 255, 255, 0.3), 
                transparent);
            animation: loadingShine 2s infinite;
        }
        
        @keyframes loadingShine {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        
        .counter {
            font-size: 16px;
            font-weight: bold;
            background: linear-gradient(90deg, var(--accent), var(--primary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        /* صفحه اصلی */
        .main-screen {
            display: none;
            animation: fadeIn 1s ease;
            opacity: 0;
            min-height: 100vh;
            overflow-y: auto;
            padding-bottom: 80px;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* هدر بهبود یافته */
        .app-header {
            padding: 2rem 0 1rem;
            text-align: center;
            animation: fadeIn 0.8s both 0.3s;
            position: relative;
        }
        
        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1.5rem;
            position: relative;
        }
        
        .logo-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-left: 12px;
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.1),
                inset -2px -2px 5px rgba(0,0,0,0.5);
            transition: var(--transition);
            position: relative;
            z-index: 1;
        }
        
        .logo-icon:hover {
            transform: rotate(15deg) scale(1.1);
            box-shadow: 
                0 12px 25px rgba(110, 69, 226, 0.4),
                inset 2px 2px 5px rgba(255,255,255,0.1),
                inset -2px -2px 5px rgba(0,0,0,0.5);
        }
        
        .logo-icon::after {
            content: '';
            position: absolute;
            top: -5px;
            left: -5px;
            right: -5px;
            bottom: -5px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 18px;
            z-index: -1;
            opacity: 0.5;
            filter: blur(10px);
            animation: pulse 3s infinite alternate;
        }
        
        .logo-text {
            font-size: 1.8rem;
            font-weight: 800;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            position: relative;
            text-shadow: var(--neon-shadow);
        }
        
        .logo-text::after {
            content: 'ویرایش ویژه';
            position: absolute;
            top: -10px;
            left: 0;
            font-size: 0.6rem;
            background: var(--accent);
            color: #000;
            padding: 2px 8px;
            border-radius: 50px;
            font-weight: 700;
            box-shadow: 0 3px 10px rgba(255, 126, 95, 0.3);
        }
        
        /* کادر اعلانات بهبود یافته */
        .announcement-box {
            font-size: 0.95rem;
            color: var(--light);
            max-width: 90%;
            margin: 1.5rem auto;
            background: rgba(30, 30, 50, 0.6);
            padding: 1rem;
            border-radius: var(--radius);
            border: 1px solid rgba(110, 69, 226, 0.3);
            animation: fadeIn 1s both 0.5s;
            min-height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.05),
                inset -2px -2px 5px rgba(0,0,0,0.5);
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
        }
        
        .announcement-box::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(110, 69, 226, 0.1), transparent);
            z-index: -1;
        }
        
        .typing-text {
            display: inline-block;
            overflow: hidden;
            border-right: 2px solid var(--primary);
            white-space: nowrap;
            margin: 0 auto;
            letter-spacing: 1px;
            animation: blink-caret 0.75s step-end infinite;
        }
        
        /* استوری‌های بهبود یافته */
        .stories-container {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 1.5rem 0;
            padding: 0 10px;
            overflow-x: auto;
            scrollbar-width: none;
            animation: fadeIn 0.8s both 0.4s;
        }
        
        .stories-container::-webkit-scrollbar {
            display: none;
        }
        
        .story-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            cursor: pointer;
            flex: 0 0 auto;
            transition: var(--transition);
        }
        
        .story-item:hover {
            transform: translateY(-5px);
        }
        
        .story-circle {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            position: relative;
            margin-bottom: 8px;
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.1),
                inset -2px -2px 5px rgba(0,0,0,0.5);
        }
        
        .story-circle::before {
            content: '';
            position: absolute;
            top: -3px;
            left: -3px;
            right: -3px;
            bottom: -3px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            z-index: -1;
            opacity: 0.6;
            filter: blur(5px);
        }
        
        .story-icon {
            width: 60px;
            height: 60px;
            background: var(--dark-light);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
            box-shadow: 
                inset 2px 2px 5px rgba(255,255,255,0.1),
                inset -2px -2px 5px rgba(0,0,0,0.5);
        }
        
        .story-label {
            font-size: 0.8rem;
            color: var(--lighter);
            text-align: center;
        }
        
        /* تب‌های اصلی بهبود یافته */
        .main-tabs {
            display: flex;
            margin: 1.5rem 0;
            background: var(--dark-light);
            border-radius: var(--radius);
            overflow: hidden;
            border: 1px solid rgba(110, 69, 226, 0.2);
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.05),
                inset -2px -2px 5px rgba(0,0,0,0.5);
            position: relative;
            animation: fadeIn 0.8s both 0.5s;
        }
        
        .main-tab {
            flex: 1;
            padding: 1rem;
            background: transparent;
            border: none;
            cursor: pointer;
            font-weight: 600;
            color: var(--lighter);
            transition: var(--transition);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 5px;
            position: relative;
        }
        
        .main-tab i {
            font-size: 1.2rem;
        }
        
        .main-tab.active {
            color: white;
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            box-shadow: 
                inset 2px 2px 5px rgba(255,255,255,0.1),
                inset -2px -2px 5px rgba(0,0,0,0.5);
        }
        
        .main-tab:hover:not(.active) {
            background: rgba(110, 69, 226, 0.1);
        }
        
        /* محتوای تب‌های اصلی */
        .main-tab-content {
            margin: 1rem 0;
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        .main-tab-content.active {
            display: block;
        }
        
        .message {
            background: rgba(67,97,238,0.2);
            padding: 1rem;
            border-radius: var(--radius);
            margin: 1rem 0;
            border: 1px solid rgba(110, 69, 226, 0.3);
            display: flex;
            align-items: center;
            color: #e0e0e0;
            animation: fadeIn 0.8s both 0.6s;
            box-shadow: 
                0 5px 15px rgba(0,0,0,0.2),
                inset 2px 2px 5px rgba(255,255,255,0.05);
            backdrop-filter: blur(5px);
        }
        
        .notice-label {
            background: var(--primary);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 50px;
            font-weight: 700;
            font-size: 0.8rem;
            margin-left: 0;
            margin-right: 10px;
            box-shadow: 0 3px 10px rgba(110, 69, 226, 0.3);
        }
        
        /* فلگ‌های بهبود یافته */
        .flag-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1rem;
            padding: 1rem 0;
            animation: fadeIn 0.8s both 0.7s;
        }
        
        .flag-item {
            background: var(--dark-light);
            padding: 1.5rem 1rem;
            text-align: center;
            border-radius: var(--radius);
            cursor: pointer;
            border: 1px solid rgba(110, 69, 226, 0.2);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.05),
                inset -2px -2px 5px rgba(0,0,0,0.5);
        }
        
        .flag-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,255,255,0.03), transparent);
            z-index: 0;
            opacity: 0;
            transition: var(--transition);
        }
        
        .flag-item:hover {
            transform: translateY(-5px);
            box-shadow: 
                0 15px 40px rgba(0,0,0,0.4),
                inset 2px 2px 5px rgba(255,255,255,0.05),
                inset -2px -2px 5px rgba(0,0,0,0.5);
            border-color: var(--primary);
        }
        
        .flag-item:hover::before {
            opacity: 1;
        }
        
        .flag-item.phone {
            background: rgba(76, 175, 80, 0.1);
            border: 1px solid rgba(76, 175, 80, 0.3);
        }
        
        .flag-item.phone::before {
            background: linear-gradient(135deg, rgba(76, 175, 80, 0.1), transparent);
        }
        
        .flag-item.modem {
            background: rgba(33, 150, 243, 0.1);
            border: 1px solid rgba(33, 150, 243, 0.3);
        }
        
        .flag-item.modem::before {
            background: linear-gradient(135deg, rgba(33, 150, 243, 0.1), transparent);
        }
        
        .flag-item span {
            font-size: 2.5rem;
            display: block;
            margin-bottom: 0.5rem;
            transition: var(--transition);
        }
        
        .flag-item:hover span {
            transform: scale(1.1);
        }
        
        .flag-item p {
            margin: 0;
            font-size: 0.95rem;
            font-weight: 600;
            color: #f0f0f0;
        }
        
        .flag-item .flag-description {
            font-size: 0.8rem;
            color: var(--lighter);
            margin-top: 0.8rem;
            opacity: 0;
            max-height: 0;
            overflow: hidden;
            transition: var(--transition-slow);
        }
        
        .flag-item:hover .flag-description {
            opacity: 1;
            max-height: 100px;
        }
        
        .status-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            font-size: 0.7rem;
            padding: 0.3rem 0.6rem;
            border-radius: 50px;
            font-weight: 700;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }
        
        .status-badge.phone {
            background: rgba(76,175,80,0.2);
            color: var(--phone-color);
            border: 1px solid var(--phone-color);
        }
        
        .status-badge.modem {
            background: rgba(33, 150, 243, 0.2);
            color: var(--modem-color);
            border: 1px solid var(--modem-color);
        }
        
        /* مودال سفارش بهبود یافته */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.95);
            z-index: 1000;
            overflow-y: auto;
        }
        
        .modal-content {
            background: var(--dark-light);
            border-radius: var(--radius);
            max-width: 95%;
            width: 100%;
            margin: 5% auto;
            overflow: hidden;
            border: 1px solid rgba(110, 69, 226, 0.3);
            box-shadow: 
                0 25px 50px rgba(0,0,0,0.5),
                inset 2px 2px 5px rgba(255,255,255,0.05),
                inset -2px -2px 5px rgba(0,0,0,0.5);
            animation: modalFadeIn 0.3s ease;
            transform-origin: center;
            backdrop-filter: blur(10px);
        }
        
        @keyframes modalFadeIn {
            from { opacity: 0; transform: scale(0.95); }
            to { opacity: 1; transform: scale(1); }
        }
        
        .modal-header {
            padding: 1.5rem;
            color: white;
            text-align: center;
            position: relative;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .modal-header.phone {
            background: linear-gradient(90deg, var(--phone-color), var(--phone-dark));
        }
        
        .modal-header.modem {
            background: linear-gradient(90deg, var(--modem-color), var(--modem-dark));
        }
        
        .modal-header.affiliate {
            background: linear-gradient(90deg, var(--affiliate-color), var(--affiliate-dark));
        }
        
        .modal-header h2 {
            font-size: 1.3rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .modal-header h2 span {
            margin-left: 10px;
            font-size: 1.6rem;
        }
        
        .close-modal {
            position: absolute;
            top: 1rem;
            left: 1.5rem;
            font-size: 1.8rem;
            cursor: pointer;
            color: white;
            transition: var(--transition);
            text-shadow: 0 2px 5px rgba(0,0,0,0.3);
        }
        
        .close-modal:hover {
            transform: rotate(90deg);
            color: var(--accent);
        }
        
        .modal-body {
            padding: 1.5rem;
        }
        
        /* تب‌های مودال بهبود یافته */
        .modal-tabs {
            display: flex;
            border-bottom: 1px solid rgba(110, 69, 226, 0.2);
            margin-bottom: 1.5rem;
            overflow-x: auto;
            white-space: nowrap;
            position: relative;
        }
        
        .modal-tabs::after {
            content: '';
            position: absolute;
            bottom: -1px;
            left: 0;
            width: 100%;
            height: 1px;
            background: rgba(110, 69, 226, 0.1);
        }
        
        .modal-tab {
            padding: 0.8rem 1.2rem;
            cursor: pointer;
            font-weight: 600;
            color: var(--lighter);
            position: relative;
            transition: var(--transition);
            min-width: 100px;
            text-align: center;
            background: transparent;
            border: none;
            outline: none;
        }
        
        .modal-tab::after {
            content: '';
            position: absolute;
            bottom: -1px;
            right: 0;
            width: 0;
            height: 3px;
            transition: var(--transition);
            border-radius: 3px 3px 0 0;
        }
        
        .modal-tab.phone::after {
            background: var(--phone-color);
        }
        
        .modal-tab.modem::after {
            background: var(--modem-color);
        }
        
        .modal-tab.affiliate::after {
            background: var(--affiliate-color);
        }
        
        .modal-tab.active {
            color: var(--primary);
        }
        
        .modal-tab.phone.active {
            color: var(--phone-color);
        }
        
        .modal-tab.modem.active {
            color: var(--modem-color);
        }
        
        .modal-tab.affiliate.active {
            color: var(--affiliate-color);
        }
        
        .modal-tab.active::after {
            width: 100%;
        }
        
        /* محتوای تب‌های مودال با انیمیشن */
        .modal-tab-content {
            display: none;
            animation: fadeIn 0.3s ease;
        }
        
        .modal-tab-content.active {
            display: block;
        }
        
        /* گزینه‌های مدت زمان بهبود یافته */
        .duration-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 1rem;
            margin: 1.5rem 0;
        }
        
        .duration-option {
            background: rgba(30,30,50,0.7);
            padding: 1.2rem 1rem;
            border-radius: var(--radius-sm);
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
            border: 1px solid rgba(110, 69, 226, 0.2);
            position: relative;
            overflow: hidden;
            box-shadow: 
                0 5px 15px rgba(0,0,0,0.2),
                inset 2px 2px 5px rgba(255,255,255,0.05);
        }
        
        .duration-option::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,255,255,0.05), transparent);
            z-index: 0;
            opacity: 0;
            transition: var(--transition);
        }
        
        .duration-option:hover {
            transform: translateY(-3px);
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.05);
            border-color: var(--primary);
        }
        
        .duration-option:hover::before {
            opacity: 1;
        }
        
        .duration-option.phone {
            border-color: rgba(76, 175, 80, 0.3);
        }
        
        .duration-option.modem {
            border-color: rgba(33, 150, 243, 0.3);
        }
        
        .duration-option.affiliate {
            border-color: rgba(156, 39, 176, 0.3);
        }
        
        .duration-option.selected {
            background: rgba(255,255,255,0.1);
            border-color: var(--primary);
            box-shadow: 
                inset 0 0 10px rgba(110, 69, 226, 0.3),
                0 5px 15px rgba(0,0,0,0.2);
        }
        
        .duration-option.phone.selected {
            background: rgba(76, 175, 80, 0.2);
            border-color: var(--phone-color);
            box-shadow: 
                inset 0 0 10px rgba(76, 175, 80, 0.3),
                0 5px 15px rgba(0,0,0,0.2);
        }
        
        .duration-option.modem.selected {
            background: rgba(33, 150, 243, 0.2);
            border-color: var(--modem-color);
            box-shadow: 
                inset 0 0 10px rgba(33, 150, 243, 0.3),
                0 5px 15px rgba(0,0,0,0.2);
        }
        
        .duration-option.affiliate.selected {
            background: rgba(156, 39, 176, 0.2);
            border-color: var(--affiliate-color);
            box-shadow: 
                inset 0 0 10px rgba(156, 39, 176, 0.3),
                0 5px 15px rgba(0,0,0,0.2);
        }
        
        .duration-days {
            font-weight: 700;
            margin-bottom: 0.5rem;
            position: relative;
            z-index: 1;
        }
        
        .duration-price {
            font-size: 0.9rem;
            color: var(--lighter);
            position: relative;
            z-index: 1;
        }
        
        /* اسلایدر حجم بهبود یافته */
        .slider-container {
            margin: 1.5rem 0;
        }
        
        .slider-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
        }
        
        .slider-value {
            font-weight: 700;
            background: rgba(30,30,50,0.7);
            padding: 0.4rem 0.8rem;
            border-radius: 50px;
            min-width: 100px;
            text-align: center;
            box-shadow: 
                0 3px 10px rgba(0,0,0,0.2),
                inset 2px 2px 5px rgba(255,255,255,0.05);
        }
        
        .slider-value.phone {
            color: var(--phone-color);
            border: 1px solid rgba(76, 175, 80, 0.3);
        }
        
        .slider-value.modem {
            color: var(--modem-color);
            border: 1px solid rgba(33, 150, 243, 0.3);
        }
        
        .slider-value.affiliate {
            color: var(--affiliate-color);
            border: 1px solid rgba(156, 39, 176, 0.3);
        }
        
        .slider-input-container {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1rem;
        }
        
        .slider-input {
            flex: 1;
        }
        
        .volume-input {
            background: rgba(30,30,50,0.7);
            border: 1px solid rgba(110, 69, 226, 0.3);
            color: white;
            padding: 0.8rem 1rem;
            border-radius: var(--radius-sm);
            font-family: inherit;
            font-size: 1rem;
            width: 100px;
            text-align: center;
            transition: var(--transition);
            box-shadow: 
                0 3px 10px rgba(0,0,0,0.2),
                inset 2px 2px 5px rgba(255,255,255,0.05);
        }
        
        .volume-input.phone {
            border-color: rgba(76, 175, 80, 0.3);
        }
        
        .volume-input.modem {
            border-color: rgba(33, 150, 243, 0.3);
        }
        
        .volume-input:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 
                0 0 0 2px rgba(110, 69, 226, 0.3),
                inset 2px 2px 5px rgba(255,255,255,0.05);
        }
        
        .volume-input.phone:focus {
            border-color: var(--phone-color);
            box-shadow: 0 0 0 2px rgba(76, 175, 80, 0.3);
        }
        
        .volume-input.modem:focus {
            border-color: var(--modem-color);
            box-shadow: 0 0 0 2px rgba(33, 150, 243, 0.3);
        }
        
        .volume-unit {
            font-size: 0.9rem;
            color: var(--lighter);
        }
        
        /* اسلایدر سفارشی */
        .slider {
            -webkit-appearance: none;
            width: 100%;
            height: 8px;
            border-radius: 4px;
            background: var(--dark);
            outline: none;
            margin: 1rem 0;
            transition: var(--transition);
            box-shadow: 
                inset 2px 2px 5px rgba(0,0,0,0.5),
                inset -2px -2px 5px rgba(255,255,255,0.05);
        }
        
        .slider:hover {
            opacity: 1;
        }
        
        .slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            background: var(--primary);
            cursor: pointer;
            border: 3px solid white;
            box-shadow: 
                0 4px 10px rgba(0,0,0,0.3),
                0 0 15px rgba(110, 69, 226, 0.5);
            transition: var(--transition);
        }
        
        .slider::-webkit-slider-thumb:hover {
            transform: scale(1.1);
            box-shadow: 
                0 6px 15px rgba(0,0,0,0.4),
                0 0 20px rgba(110, 69, 226, 0.7);
        }
        
        .slider.phone::-webkit-slider-thumb {
            background: var(--phone-color);
            box-shadow: 
                0 4px 10px rgba(0,0,0,0.3),
                0 0 15px rgba(76, 175, 80, 0.5);
        }
        
        .slider.modem::-webkit-slider-thumb {
            background: var(--modem-color);
            box-shadow: 
                0 4px 10px rgba(0,0,0,0.3),
                0 0 15px rgba(33, 150, 243, 0.5);
        }
        
        .slider.affiliate::-webkit-slider-thumb {
            background: var(--affiliate-color);
            box-shadow: 
                0 4px 10px rgba(0,0,0,0.3),
                0 0 15px rgba(156, 39, 176, 0.5);
        }
        
        /* قیمت نهایی بهبود یافته */
        .final-price {
            text-align: center;
            margin: 2rem 0;
            font-size: 1.3rem;
            position: relative;
            animation: fadeIn 0.5s ease;
            background: rgba(30,30,50,0.7);
            padding: 1.5rem;
            border-radius: var(--radius);
            border: 1px solid rgba(110, 69, 226, 0.3);
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.05);
        }
        
        .final-price span {
            font-weight: 800;
            font-size: 1.8rem;
            display: inline-block;
            margin-top: 0.5rem;
            text-shadow: 0 0 10px rgba(110, 69, 226, 0.5);
        }
        
        .final-price.phone span {
            color: var(--phone-color);
            text-shadow: 0 0 10px rgba(76, 175, 80, 0.5);
        }
        
        .final-price.modem span {
            color: var(--modem-color);
            text-shadow: 0 0 10px rgba(33, 150, 243, 0.5);
        }
        
        .final-price.affiliate span {
            color: var(--affiliate-color);
            text-shadow: 0 0 10px rgba(156, 39, 176, 0.5);
        }
        
        /* خلاصه سفارش بهبود یافته */
        .order-summary {
            background: rgba(30,30,50,0.7);
            padding: 1.5rem;
            border-radius: var(--radius-sm);
            margin: 2rem 0;
            border-left: 3px solid var(--primary);
            animation: fadeIn 0.5s ease;
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.05);
        }
        
        .order-summary.phone {
            border-left: 3px solid var(--phone-color);
        }
        
        .order-summary.modem {
            border-left: 3px solid var(--modem-color);
        }
        
        .order-summary.affiliate {
            border-left: 3px solid var(--affiliate-color);
        }
        
        .order-summary p {
            margin-bottom: 0.8rem;
            display: flex;
            justify-content: space-between;
            padding: 0.4rem 0;
            border-bottom: 1px dashed rgba(110, 69, 226, 0.3);
        }
        
        .order-summary .value {
            color: var(--primary);
            font-weight: 600;
        }
        
        .order-summary.phone .value {
            color: var(--phone-color);
        }
        
        .order-summary.modem .value {
            color: var(--modem-color);
        }
        
        .order-summary.affiliate .value {
            color: var(--affiliate-color);
        }
        
        /* فوتر مودال بهبود یافته */
        .modal-footer {
            display: flex;
            justify-content: space-between;
            padding: 1.5rem;
            border-top: 1px solid rgba(110, 69, 226, 0.2);
            gap: 15px;
        }
        
        /* دکمه‌های بهبود یافته */
        .btn {
            padding: 1rem 1.8rem;
            border-radius: 50px;
            font-family: inherit;
            font-weight: 600;
            cursor: pointer;
            border: none;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            justify-content: center;
            flex: 1;
            position: relative;
            overflow: hidden;
            box-shadow: 
                0 5px 15px rgba(0,0,0,0.2),
                inset 2px 2px 5px rgba(255,255,255,0.1),
                inset -2px -2px 5px rgba(0,0,0,0.3);
        }
        
        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,255,255,0.1), transparent);
            z-index: 0;
            opacity: 0;
            transition: var(--transition);
        }
        
        .btn:hover::before {
            opacity: 1;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.1),
                inset -2px -2px 5px rgba(0,0,0,0.3);
        }
        
        .btn:active {
            transform: translateY(1px);
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: white;
            box-shadow: 
                0 8px 20px rgba(110, 69, 226, 0.3),
                inset 2px 2px 5px rgba(255,255,255,0.1),
                inset -2px -2px 5px rgba(0,0,0,0.3);
        }
        
        .btn-phone {
            background: linear-gradient(135deg, var(--phone-color), var(--phone-dark));
            color: white;
            box-shadow: 
                0 8px 20px rgba(76, 175, 80, 0.3),
                inset 2px 2px 5px rgba(255,255,255,0.1),
                inset -2px -2px 5px rgba(0,0,0,0.3);
        }
        
        .btn-modem {
            background: linear-gradient(135deg, var(--modem-color), var(--modem-dark));
            color: white;
            box-shadow: 
                0 8px 20px rgba(33, 150, 243, 0.3),
                inset 2px 2px 5px rgba(255,255,255,0.1),
                inset -2px -2px 5px rgba(0,0,0,0.3);
        }
        
        .btn-affiliate {
            background: linear-gradient(135deg, var(--affiliate-color), var(--affiliate-dark));
            color: white;
            box-shadow: 
                0 8px 20px rgba(156, 39, 176, 0.3),
                inset 2px 2px 5px rgba(255,255,255,0.1),
                inset -2px -2px 5px rgba(0,0,0,0.3);
        }
        
        .btn-secondary {
            background: var(--dark);
            color: var(--light);
            border: 1px solid rgba(110, 69, 226, 0.3);
        }
        
        .btn-secondary:hover {
            background: rgba(110, 69, 226, 0.1);
            border-color: var(--primary);
        }
        
        /* اعلان‌های بهبود یافته */
        .notification {
            position: fixed;
            bottom: 70px;
            right: 50%;
            transform: translateX(50%);
            background: var(--primary);
            color: white;
            padding: 1rem 1.8rem;
            border-radius: 50px;
            z-index: 100;
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                0 0 20px rgba(110, 69, 226, 0.5);
            display: none;
            max-width: 90%;
            text-align: center;
            animation: fadeIn 0.3s ease;
            backdrop-filter: blur(10px);
        }
        
        /* نوار پایینی بهبود یافته */
        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            display: flex;
            justify-content: center;
            background: var(--dark-light);
            padding: 1rem;
            border-top: 1px solid rgba(110, 69, 226, 0.3);
            z-index: 99;
            box-shadow: 
                0 -8px 25px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.05);
            backdrop-filter: blur(10px);
        }
        
        .bottom-nav-btn {
            flex: 1;
            max-width: 220px;
            padding: 1rem;
            border-radius: 50px;
            background: var(--dark);
            color: var(--light);
            border: none;
            font-family: inherit;
            cursor: pointer;
            border: 1px solid rgba(110, 69, 226, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            gap: 8px;
            box-shadow: 
                0 5px 15px rgba(0,0,0,0.2),
                inset 2px 2px 5px rgba(255,255,255,0.05);
        }
        
        .bottom-nav-btn:hover {
            background: rgba(110, 69, 226, 0.1);
            transform: translateY(-3px);
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.05);
        }
        
        #aboutBtn {
            color: var(--secondary);
        }
        
        #downloadBtn {
            color: var(--primary);
        }
        
        /* بخش DNS بهبود یافته */
        .dns-container {
            background: rgba(30,30,50,0.7);
            border-radius: var(--radius);
            padding: 1.5rem;
            margin: 1.5rem 0;
            border: 1px solid rgba(110, 69, 226, 0.3);
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.05);
            animation: fadeIn 0.8s both 0.7s;
        }
        
        .dns-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 1rem;
            background: rgba(20,20,40,0.5);
            border-radius: var(--radius-sm);
            margin-bottom: 1rem;
            border: 1px solid rgba(110, 69, 226, 0.2);
            transition: var(--transition);
        }
        
        .dns-item:hover {
            background: rgba(110, 69, 226, 0.1);
            border-color: var(--primary);
        }
        
        .dns-label {
            font-weight: 600;
            color: var(--secondary);
        }
        
        .dns-value {
            font-family: monospace;
            font-size: 1.1rem;
            color: var(--light);
            direction: ltr;
            margin: 0 1rem;
            flex-grow: 1;
            text-align: center;
        }
        
        .copy-btn {
            background: rgba(110, 69, 226, 0.2);
            color: var(--primary);
            border: 1px solid var(--primary);
            padding: 0.5rem 1rem;
            border-radius: var(--radius-sm);
            cursor: pointer;
            transition: var(--transition);
            font-weight: 600;
        }
        
        .copy-btn:hover {
            background: var(--primary);
            color: white;
            box-shadow: 0 0 15px rgba(110, 69, 226, 0.3);
        }
        
        /* بخش دانلود بهبود یافته */
        .download-items {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin: 1.5rem 0;
            animation: fadeIn 0.8s both 0.7s;
        }
        
        .download-item {
            background: rgba(30,30,50,0.7);
            border-radius: var(--radius);
            padding: 1.5rem;
            border: 1px solid rgba(110, 69, 226, 0.3);
            box-shadow: 
                0 8px 20px rgba(0,0,0,0.3),
                inset 2px 2px 5px rgba(255,255,255,0.05);
            transition: var(--transition);
            display: flex;
            flex-direction: column;
        }
        
        .download-item:hover {
            transform: translateY(-5px);
            box-shadow: 
                0 15px 40px rgba(0,0,0,0.4),
                inset 2px 2px 5px rgba(255,255,255,0.05);
            border-color: var(--primary);
        }
        
        .download-item h3 {
            color: var(--primary);
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .download-item h3 i {
            font-size: 1.2rem;
        }
        
        .download-meta {
            display: flex;
            gap: 1rem;
            margin-bottom: 1rem;
            flex-wrap: wrap;
        }
        
        .meta-item {
            font-size: 0.8rem;
            color: var(--lighter);
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .meta-item i {
            font-size: 0.9rem;
        }
        
        .download-item p {
            margin-bottom: 1.5rem;
            line-height: 1.7;
            flex-grow: 1;
        }
        
        .download-btn {
            background: rgba(110, 69, 226, 0.2);
            color: var(--primary);
            border: 1px solid var(--primary);
            padding: 0.8rem 1.5rem;
            border-radius: 50px;
            text-align: center;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        
        .download-btn:hover {
            background: var(--primary);
            color: white;
            box-shadow: 0 0 20px rgba(110, 69, 226, 0.3);
        }
        
        /* استوری تمام صفحه */
        .story-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--darker);
            z-index: 1001;
            overflow: hidden;
        }
        
        .story-content {
            position: relative;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 2rem;
            text-align: center;
            color: white;
        }
        
        .story-close {
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 2rem;
            cursor: pointer;
            color: var(--accent);
            z-index: 10;
        }
        
        .story-title {
            font-size: 2rem;
            margin-bottom: 2rem;
            color: var(--primary);
            text-shadow: 0 0 15px rgba(110, 69, 226, 0.5);
        }
        
        .story-text {
            font-size: 1.2rem;
            line-height: 1.8;
            max-width: 600px;
            margin-bottom: 2rem;
        }
        
        .story-nav {
            position: absolute;
            top: 50%;
            width: 100%;
            display: flex;
            justify-content: space-between;
            padding: 0 2rem;
            transform: translateY(-50%);
            z-index: 5;
        }
        
        .story-nav-btn {
            background: rgba(255,255,255,0.1);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 1.5rem;
            color: white;
            transition: var(--transition);
            backdrop-filter: blur(5px);
        }
        
        .story-nav-btn:hover {
            background: var(--primary);
            transform: scale(1.1);
        }
        
        /* انیمیشن‌های جدید */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes fadeOut {
            from { opacity: 1; transform: translateY(0); }
            to { opacity: 0; transform: translateY(10px); }
        }
        
        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: var(--primary); }
        }
        
        /* رسپانسیو */
        @media (max-width: 768px) {
            .logo-icon {
                width: 45px;
                height: 45px;
            }
            
            .logo-text {
                font-size: 1.5rem;
            }
            
            .flag-item {
                padding: 1rem 0.8rem;
            }
            
            .flag-item span {
                font-size: 2rem;
            }
            
            .duration-options {
                grid-template-columns: 1fr;
            }
            
            .modal-content {
                max-width: 98%;
                margin: 2% auto;
            }
            
            .bottom-nav-btn {
                padding: 0.8rem;
                font-size: 0.9rem;
            }
            
            .download-items {
                grid-template-columns: 1fr;
            }
            
            .story-title {
                font-size: 1.5rem;
            }
            
            .story-text {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- صفحه لودینگ -->
    <div class="loading-screen" id="loadingScreen">
        <div class="logo-container">
            <div class="logo-text">
                <div class="mr">آقای</div>
                <div class="xero">ایکسرو</div>
            </div>
        </div>
        
        <div class="loading-footer">
            <div class="waiting-container">
                <div class="waiting-text">
                    منتظر باشید
                    <span class="dot">.</span>
                    <span class="dot">.</span>
                    <span class="dot">.</span>
                </div>
                <div class="counter" id="counter">0%</div>
            </div>
            <div class="loading-bar-container">
                <div class="loading-bar" id="loadingBar"></div>
            </div>
        </div>
    </div>
    
    <!-- صفحه اصلی -->
    <div class="main-screen" id="mainScreen">
        <div class="container">
            <header class="app-header">
                <div class="logo">
                    <div class="logo-icon">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <div class="logo-text">XRO VPN</div>
                </div>
            </header>

            <!-- بخش استوری‌ها -->
            <div class="stories-container">
                <div class="story-item" onclick="openStory('you')">
                    <div class="story-circle">
                        <div class="story-icon">
                            <i class="fas fa-user"></i>
                        </div>
                    </div>
                    <div class="story-label">نظرات کاربران</div>
                </div>
                <div class="story-item" onclick="openStory('security')">
                    <div class="story-circle">
                        <div class="story-icon">
                            <i class="fas fa-lock"></i>
                        </div>
                    </div>
                    <div class="story-label">امنیت</div>
                </div>
                <div class="story-item" onclick="openStory('guide')">
                    <div class="story-circle">
                        <div class="story-icon">
                            <i class="fas fa-question"></i>
                        </div>
                    </div>
                    <div class="story-label">راهنمای خرید</div>
                </div>
            </div>

            <!-- کادر اعلانات -->
            <div class="announcement-box">
                <div id="typingText" class="typing-text">آقای ایکسرا حامی آزادی است | در بدترین شرایط خدمات ما پیدار می‌ماند | فروش ماهانه +۱۰هزار کانفیگ شد!</div>
            </div>

            <!-- تب‌های اصلی -->
            <div class="main-tabs">
                <button class="main-tab active" onclick="showMainTab('home')">
                    <i class="fas fa-store"></i>
                    <span>فروشگاه</span>
                </button>
                <button class="main-tab" onclick="showMainTab('dns')">
                    <i class="fas fa-network-wired"></i>
                    <span>DNS</span>
                </button>
                <button class="main-tab" onclick="showMainTab('download')">
                    <i class="fas fa-download"></i>
                    <span>دانلود</span>
                </button>
            </div>
            
            <!-- محتوای تب‌های اصلی -->
            <div id="home-tab" class="main-tab-content active">
                <div class="message">
                    <span class="notice-label">توجه</span>
                    <span>این بخش برای سفارش کانفیگ با شرایط ملی هست</span>
                </div>
                <div class="flag-grid">
                    <!-- بخش جنگی گوشی -->
                    <div class="flag-item phone active" onclick="openPhoneModal('personal')">
                        <span>📱</span>
                        <p>جنگی گوشی</p>
                        <div class="flag-description">
                            سرویس ویژه برای گوشی با حجم نامحدود و اتصال پایدار
                            <div style="margin-top: 0.5rem; font-weight: 600; color: var(--phone-color);">
                                حجم: نامحدود
                            </div>
                        </div>
                        <div class="status-badge phone">ویژه</div>
                    </div>
                    
                    <!-- بخش جنگی مودم -->
                    <div class="flag-item modem active" onclick="openModemModal('personal')">
                        <span>📡</span>
                        <p>جنگی مودم</p>
                        <div class="flag-description">
                            سرویس ویژه برای مودم با حجم انتخابی و اتصال پایدار
                            <div style="margin-top: 0.5rem; font-weight: 600; color: var(--modem-color);">
                                حجم: 1GB تا 1000GB
                            </div>
                        </div>
                        <div class="status-badge modem">ویژه</div>
                    </div>
                </div>
            </div>
            
            <div id="dns-tab" class="main-tab-content">
                <div class="message">
                    <span class="notice-label">توجه</span>
                    <span>این بخش با استفاده از DNS سرعتی، پایدار برای بازی برقرار کنید. کاهش پینگ و جلوگیری از نوسان در بازی‌های آنلاین</span>
                </div>
                
                <!-- بخش DNS بهبود یافته -->
                <div class="dns-container">
                    <div class="dns-item">
                        <span class="dns-label">DNS اول:</span>
                        <span class="dns-value" id="dns1">78.157.42.100</span>
                        <button class="copy-btn" onclick="copyToClipboard('dns1')">کپی</button>
                    </div>
                    <div class="dns-item">
                        <span class="dns-label">DNS دوم:</span>
                        <span class="dns-value" id="dns2">78.157.42.101</span>
                        <button class="copy-btn" onclick="copyToClipboard('dns2')">کپی</button>
                    </div>
                </div>
            </div>
            
            <div id="download-tab" class="main-tab-content">
                <div class="message">
                    <span class="notice-label">توجه</span>
                    <span>این بخش مخصوص دانلود اپلیکیشن هیدیفای برای سیستم شما است</span>
                </div>
                
                <!-- بخش دانلود بهبود یافته -->
                <div class="download-items">
                    <div class="download-item">
                        <h3>
                            <i class="fas fa-mobile-alt"></i>
                            نسخه اندروید
                        </h3>
                        <div class="download-meta">
                            <div class="meta-item"><i class="fas fa-code-branch"></i> نسخه 2.5.1</div>
                            <div class="meta-item"><i class="fas fa-calendar-alt"></i> 1403/02/15</div>
                        </div>
                        <p>نرم‌افزار هیدیفای برای دستگاه‌های اندروید. بهترین انتخاب برای کاربران اندروید با رابط کاربری ساده و امکانات پیشرفته.</p>
                        <a href="https://myket.ir/app/io.github.hid3dclient.hid3d" class="download-btn" target="_blank">
                            دانلود از مایکت
                            <i class="fas fa-download"></i>
                        </a>
                    </div>
                    
                    <div class="download-item">
                        <h3>
                            <i class="fas fa-desktop"></i>
                            نسخه ویندوز
                        </h3>
                        <div class="download-meta">
                            <div class="meta-item"><i class="fas fa-code-branch"></i> نسخه 3.1.0</div>
                            <div class="meta-item"><i class="fas fa-calendar-alt"></i> 1403/01/28</div>
                        </div>
                        <p>نرم‌افزار هیدیفای برای سیستم‌عامل ویندوز. پشتیبانی از ویندوز 7 به بالا با قابلیت‌های مدیریت چند کانفیگ.</p>
                        <a href="https://github.com/hid3dclient/hid3d/releases" class="download-btn" target="_blank">
                            دانلود (62MB)
                            <i class="fas fa-download"></i>
                        </a>
                    </div>
                    
                    <div class="download-item">
                        <h3>
                            <i class="fas fa-mobile"></i>
                            نسخه iOS
                        </h3>
                        <div class="download-meta">
                            <div class="meta-item"><i class="fas fa-code-branch"></i> نسخه 1.8.2</div>
                            <div class="meta-item"><i class="fas fa-calendar-alt"></i> 1402/12/15</div>
                        </div>
                        <p>نرم‌افزار هیدیفای برای دستگاه‌های iOS. بهترین انتخاب برای کاربران آیفون و آیپد با رابط کاربری ساده.</p>
                        <a href="https://apps.apple.com/us/app/hid3d/id6472582787" class="download-btn" target="_blank">
                            دانلود از اپ استور
                            <i class="fas fa-download"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- مودال سفارش جنگی گوشی -->
        <div id="phoneModal" class="modal">
            <div class="modal-content">
                <div class="modal-header phone">
                    <span class="close-modal" onclick="closeModal()">×</span>
                    <h2><span>جنگی گوشی</span> 📱</h2>
                </div>
                <div class="modal-body">
                    <div class="modal-tabs">
                        <div class="modal-tab phone active" onclick="showModalTab('type', 'phone')">نوع سفارش</div>
                        <div class="modal-tab phone" onclick="showModalTab('duration', 'phone')">مدت زمان</div>
                        <div class="modal-tab phone" onclick="showModalTab('final', 'phone')">نهایی</div>
                    </div>
                    
                    <!-- تب نوع سفارش -->
                    <div id="typeTab-phone" class="modal-tab-content active">
                        <div class="duration-options">
                            <div class="duration-option phone" onclick="selectOrderType('phone', 'personal')">
                                <div class="duration-days">شخصی</div>
                                <div class="duration-price">برای استفاده شخصی</div>
                            </div>
                            <div class="duration-option affiliate" onclick="selectOrderType('phone', 'affiliate')">
                                <div class="duration-days">همکاری</div>
                                <div class="duration-price">برای فروش و همکاری</div>
                            </div>
                        </div>
                        
                        <div class="modal-footer">
                            <button class="btn btn-secondary" onclick="closeModal()">
                                انصراف
                            </button>
                            <button class="btn btn-phone" onclick="showModalTab('duration', 'phone')">
                                بعدی
                            </button>
                        </div>
                    </div>
                    
                    <!-- تب مدت زمان -->
                    <div id="durationTab-phone" class="modal-tab-content">
                        <div class="duration-options phone">
                            <div class="duration-option phone" onclick="selectDuration('phone', 30, 'personal')">
                                <div class="duration-days">30 روز</div>
                                <div class="duration-price">
                                    <span id="personal-30-price">310,000 تومان</span>
                                </div>
                            </div>
                            <div class="duration-option phone" onclick="selectDuration('phone', 90, 'personal')">
                                <div class="duration-days">90 روز</div>
                                <div class="duration-price">
                                    <span id="personal-90-price">683,000 تومان</span>
                                </div>
                            </div>
                            <div class="duration-option phone" onclick="selectDuration('phone', 180, 'personal')">
                                <div class="duration-days">180 روز</div>
                                <div class="duration-price">
                                    <span id="personal-180-price">988,000 تومان</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="modal-footer">
                            <button class="btn btn-secondary" onclick="showModalTab('type', 'phone')">
                                قبلی
                            </button>
                            <button class="btn btn-phone" onclick="showModalTab('final', 'phone')">
                                بعدی
                            </button>
                        </div>
                    </div>
                    
                    <!-- تب نهایی -->
                    <div id="finalTab-phone" class="modal-tab-content">
                        <div class="final-price phone">
                            قیمت نهایی: <span id="finalPhonePrice">0</span> تومان
                        </div>
                        <div class="order-summary phone">
                            <p>
                                <span>نوع سرویس:</span>
                                <span class="value">جنگی گوشی</span>
                            </p>
                            <p>
                                <span>حجم:</span>
                                <span class="value">نامحدود</span>
                            </p>
                            <p>
                                <span>مدت:</span>
                                <span class="value" id="finalPhoneDays">0 روز</span>
                            </p>
                            <p>
                                <span>نوع:</span>
                                <span class="value" id="finalPhoneType">شخصی</span>
                            </p>
                        </div>
                        <div class="modal-footer">
                            <button class="btn btn-secondary" onclick="showModalTab('duration', 'phone')">
                                قبلی
                            </button>
                            <button class="btn btn-phone" onclick="submitOrder('phone')">
                                سفارش
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- مودال سفارش جنگی مودم -->
        <div id="modemModal" class="modal">
            <div class="modal-content">
                <div class="modal-header modem">
                    <span class="close-modal" onclick="closeModal()">×</span>
                    <h2><span>جنگی مودم</span> 📡</h2>
                </div>
                <div class="modal-body">
                    <div class="modal-tabs">
                        <div class="modal-tab modem active" onclick="showModalTab('type', 'modem')">نوع سفارش</div>
                        <div class="modal-tab modem" onclick="showModalTab('volume', 'modem')">حجم</div>
                        <div class="modal-tab modem" onclick="showModalTab('days', 'modem')">روز</div>
                        <div class="modal-tab modem" onclick="showModalTab('final', 'modem')">نهایی</div>
                    </div>
                    
                    <!-- تب نوع سفارش -->
                    <div id="typeTab-modem" class="modal-tab-content active">
                        <div class="duration-options">
                            <div class="duration-option modem" onclick="selectOrderType('modem', 'personal')">
                                <div class="duration-days">شخصی</div>
                                <div class="duration-price">برای استفاده شخصی</div>
                            </div>
                            <div class="duration-option affiliate" onclick="selectOrderType('modem', 'affiliate')">
                                <div class="duration-days">همکاری</div>
                                <div class="duration-price">برای فروش و همکاری</div>
                            </div>
                        </div>
                        
                        <div class="modal-footer">
                            <button class="btn btn-secondary" onclick="closeModal()">
                                انصراف
                            </button>
                            <button class="btn btn-modem" onclick="showModalTab('volume', 'modem')">
                                بعدی
                            </button>
                        </div>
                    </div>
                    
                    <!-- تب حجم -->
                    <div id="volumeTab-modem" class="modal-tab-content">
                        <div class="slider-container">
                            <div class="slider-header">
                                <span>حجم مورد نیاز:</span>
                                <span class="slider-value modem" id="volumeValue-modem">1 گیگ</span>
                            </div>
                            <div class="slider-input-container">
                                <input type="range" min="1" max="1000" value="1" class="slider modem" id="volumeSlider-modem" oninput="updateVolume(this.value, 'modem')">
                                <input type="number" min="1" max="1000" value="1" class="volume-input modem" id="volumeInput-modem" oninput="updateVolumeInput(this.value, 'modem')">
                                <span class="volume-unit">گیگابایت</span>
                            </div>
                        </div>
                        
                        <div class="modal-footer">
                            <button class="btn btn-secondary" onclick="showModalTab('type', 'modem')">
                                قبلی
                            </button>
                            <button class="btn btn-modem" onclick="showModalTab('days', 'modem')">
                                بعدی
                            </button>
                        </div>
                    </div>
                    
                    <!-- تب روزها -->
                    <div id="daysTab-modem" class="modal-tab-content">
                        <div class="slider-container">
                            <div class="slider-header">
                                <span>تعداد روز:</span>
                                <span class="slider-value modem" id="daysValue-modem">2 روز</span>
                            </div>
                            <div class="slider-input-container">
                                <input type="range" min="1" max="30" value="2" class="slider modem" id="daysSlider-modem" oninput="updateDays(this.value, 'modem')">
                                <input type="number" min="1" max="30" value="2" class="volume-input modem" id="daysInput-modem" oninput="updateDaysInput(this.value, 'modem')">
                                <span class="volume-unit">روز</span>
                            </div>
                        </div>
                        
                        <div class="modal-footer">
                            <button class="btn btn-secondary" onclick="showModalTab('volume', 'modem')">
                                قبلی
                            </button>
                            <button class="btn btn-modem" onclick="showModalTab('final', 'modem')">
                                بعدی
                            </button>
                        </div>
                    </div>
                    
                    <!-- تب نهایی -->
                    <div id="finalTab-modem" class="modal-tab-content">
                        <div class="final-price modem">
                            قیمت نهایی: <span id="finalModemPrice">0</span> تومان
                        </div>
                        <div class="order-summary modem">
                            <p>
                                <span>نوع سرویس:</span>
                                <span class="value">جنگی مودم</span>
                            </p>
                            <p>
                                <span>حجم:</span>
                                <span class="value" id="finalModemVolume">0 گیگ</span>
                            </p>
                            <p>
                                <span>مدت:</span>
                                <span class="value" id="finalModemDays">0 روز</span>
                            </p>
                            <p>
                                <span>نوع:</span>
                                <span class="value" id="finalModemType">شخصی</span>
                            </p>
                        </div>
                        <div class="modal-footer">
                            <button class="btn btn-secondary" onclick="showModalTab('days', 'modem')">
                                قبلی
                            </button>
                            <button class="btn btn-modem" onclick="submitOrder('modem')">
                                سفارش
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- استوری تمام صفحه -->
        <div id="storyModal" class="story-modal">
            <div class="story-content">
                <span class="story-close" onclick="closeStory()">×</span>
                <h2 class="story-title" id="storyTitle">عنوان استوری</h2>
                <p class="story-text" id="storyText">متن استوری اینجا نمایش داده می‌شود</p>
                <div class="story-nav">
                    <div class="story-nav-btn" onclick="prevStory()">❮</div>
                    <div class="story-nav-btn" onclick="nextStory()">❯</div>
                </div>
            </div>
        </div>
        
        <!-- اعلان -->
        <div class="notification" id="notification">
            این سرویس در حال حاضر غیرفعال می‌باشد
        </div>
        
        <!-- نوار پایینی -->
        <div class="bottom-nav">
            <button class="bottom-nav-btn" id="aboutBtn" onclick="showAbout()">
                <i class="fas fa-info-circle"></i>
                درباره ما
            </button>
            <button class="bottom-nav-btn" id="supportBtn" onclick="showSupport()">
                <i class="fas fa-headset"></i>
                پشتیبانی آنلاین
            </button>
        </div>
    </div>

    <script>
        // تنظیمات اولیه
        let currentOrder = {
            type: '', // 'phone' یا 'modem'
            orderType: 'personal', // 'personal' یا 'affiliate'
            volume: 1,
            days: 1,
            price: 0
        };
        
        // قیمت‌های جنگی گوشی
        const phonePrices = {
            personal: {
                30: 310000,
                90: 683000,
                180: 988000
            },
            affiliate: {
                30: 213000,
                90: 450000,
                180: 690000
            }
        };
        
        // قیمت‌های جنگی مودم
        const modemPrices = {
            personal: {
                perGB: 400,
                perDay: 200
            },
            affiliate: {
                perGB: 170, // 400 - 230
                perDay: 150
            }
        };
        
        // داده‌های استوری
        const stories = {
            you: {
                title: "نظرات کاربران",
                text: "نظرات و تجربیات کاربران XRO VPN. کاربران ما از سرعت و پایداری سرویس‌های ما رضایت کامل دارند."
            },
            security: {
                title: "امنیت پیشرفته",
                text: "ما از آخرین تکنولوژی‌های رمزنگاری برای محافظت از حریم خصوصی شما استفاده می‌کنیم. تمام ارتباطات شما به صورت end-to-end رمزنگاری می‌شوند."
            },
            guide: {
                title: "راهنمای خرید",
                text: "1. نوع سرویس مورد نیاز خود را انتخاب کنید\n2. مدت زمان و حجم مورد نیاز را مشخص کنید\n3. سفارش خود را نهایی کرده و کانفیگ را دریافت کنید"
            }
        };
        
        let currentStoryIndex = 0;
        const storyKeys = Object.keys(stories);
        
        // نمایش تب‌های اصلی
        function showMainTab(tabName) {
            const tabs = document.querySelectorAll('.main-tab');
            const tabContents = document.querySelectorAll('.main-tab-content');
            
            tabs.forEach(tab => tab.classList.remove('active'));
            tabContents.forEach(content => content.classList.remove('active'));
            
            document.getElementById(`${tabName}-tab`).classList.add('active');
            document.querySelector(`.main-tab[onclick="showMainTab('${tabName}')"]`).classList.add('active');
        }
        
        // نمایش اعلان
        function showNotification(message = 'این سرویس در حال حاضر غیرفعال می‌باشد') {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.style.display = 'block';
            
            setTimeout(() => {
                notification.style.display = 'none';
            }, 3000);
        }
        
        // نمایش صفحه درباره ما
        function showAbout() {
            const aboutContent = `
                <div style="background: var(--dark-light); padding: 2rem; border-radius: var(--radius); max-width: 90%; margin: 2rem auto; text-align: center;">
                    <h2 style="color: var(--primary); margin-bottom: 1rem;">درباره XRO VPN</h2>
                    <p style="line-height: 1.8; margin-bottom: 1.5rem;">
                        XRO VPN ارائه دهنده سرویس‌های پرسرعت و پایدار برای کاربران ایرانی است. ما با ارائه سرویس‌های ویژه در شرایط مختلف، همیشه در کنار شما هستیم.
                    </p>
                    <p style="line-height: 1.8;">
                        تیم فنی ما همواره در حال بهبود کیفیت سرویس‌ها و ارائه راهکارهای جدید برای دسترسی آزاد به اینترنت است.
                        <br><br>
                        <strong>ما پشت مردم هستیم و در سخت‌ترین شرایط نیز خدمات ما پایدار خواهد ماند.</strong>
                    </p>
                </div>
            `;
            
            alert(aboutContent);
        }
        
        // نمایش پشتیبانی آنلاین
        function showSupport() {
            showNotification('پشتیبانی آنلاین در نسخه بعدی فعال خواهد شد');
        }
        
        // باز کردن مودال جنگی گوشی
        function openPhoneModal(orderType) {
            currentOrder = {
                type: 'phone',
                orderType: orderType,
                volume: 0,
                days: 0,
                price: 0
            };
            
            // تنظیم قیمت‌ها بر اساس نوع سفارش (شخصی/همکاری)
            updatePhonePrices();
            
            document.getElementById('finalPhoneType').textContent = orderType === 'affiliate' ? 'همکاری' : 'شخصی';
            document.getElementById('phoneModal').style.display = 'block';
            document.body.style.overflow = 'hidden';
            showModalTab('type', 'phone');
        }
        
        // باز کردن مودال جنگی مودم
        function openModemModal(orderType) {
            currentOrder = {
                type: 'modem',
                orderType: orderType,
                volume: 1,
                days: 2,
                price: 0
            };
            
            document.getElementById('finalModemType').textContent = orderType === 'affiliate' ? 'همکاری' : 'شخصی';
            document.getElementById('modemModal').style.display = 'block';
            document.body.style.overflow = 'hidden';
            showModalTab('type', 'modem');
            
            // مقداردهی اولیه مقادیر
            updateVolume(1, 'modem');
            updateDays(2, 'modem');
        }
        
        // به‌روزرسانی قیمت‌های گوشی بر اساس نوع سفارش
        function updatePhonePrices() {
            const prices = currentOrder.orderType === 'affiliate' ? phonePrices.affiliate : phonePrices.personal;
            
            document.getElementById('personal-30-price').textContent = prices[30].toLocaleString('fa-IR') + ' تومان';
            document.getElementById('personal-90-price').textContent = prices[90].toLocaleString('fa-IR') + ' تومان';
            document.getElementById('personal-180-price').textContent = prices[180].toLocaleString('fa-IR') + ' تومان';
        }
        
        // انتخاب نوع سفارش (شخصی/همکاری)
        function selectOrderType(modalType, orderType) {
            currentOrder.orderType = orderType;
            
            // حذف کلاس selected از همه گزینه‌ها
            document.querySelectorAll(`#${modalType}Tab-${modalType} .duration-option`).forEach(option => {
                option.classList.remove('selected');
            });
            
            // اضافه کردن کلاس selected به گزینه انتخاب شده
            event.target.closest('.duration-option').classList.add('selected');
            
            // به‌روزرسانی نوع سفارش در خلاصه
            document.getElementById(`final${modalType.charAt(0).toUpperCase() + modalType.slice(1)}Type`).textContent = 
                orderType === 'affiliate' ? 'همکاری' : 'شخصی';
            
            // اگر گوشی است، قیمت‌ها را به‌روزرسانی کن
            if (modalType === 'phone') {
                updatePhonePrices();
            }
        }
        
        // انتخاب مدت زمان برای جنگی گوشی
        function selectDuration(modalType, days, orderType) {
            currentOrder.days = days;
            currentOrder.orderType = orderType;
            
            const prices = orderType === 'affiliate' ? phonePrices.affiliate : phonePrices.personal;
            currentOrder.price = prices[days];
            
            // حذف کلاس selected از همه گزینه‌ها
            document.querySelectorAll(`#durationTab-${modalType} .duration-option`).forEach(option => {
                option.classList.remove('selected');
            });
            
            // اضافه کردن کلاس selected به گزینه انتخاب شده
            event.target.closest('.duration-option').classList.add('selected');
            
            // به‌روزرسانی خلاصه سفارش
            document.getElementById(`final${modalType.charAt(0).toUpperCase() + modalType.slice(1)}Days`).textContent = `${days} روز`;
            document.getElementById(`final${modalType.charAt(0).toUpperCase() + modalType.slice(1)}Price`).textContent = 
                currentOrder.price.toLocaleString('fa-IR');
        }
        
        // به‌روزرسانی حجم برای جنگی مودم
        function updateVolume(value, modalType) {
            currentOrder.volume = parseInt(value);
            document.getElementById('volumeValue-modem').textContent = `${currentOrder.volume} گیگ`;
            document.getElementById('volumeInput-modem').value = currentOrder.volume;
            document.getElementById('finalModemVolume').textContent = `${currentOrder.volume} گیگ`;
            updateModemPrice();
        }
        
        // به‌روزرسانی دستی حجم برای جنگی مودم
        function updateVolumeInput(value, modalType) {
            let volume = parseInt(value);
            if (isNaN(volume)) volume = 1;
            if (volume < 1) volume = 1;
            if (volume > 1000) volume = 1000;
            
            document.getElementById('volumeSlider-modem').value = volume;
            updateVolume(volume, modalType);
        }
        
        // به‌روزرسانی روزها برای جنگی مودم
        function updateDays(value, modalType) {
            currentOrder.days = parseInt(value);
            document.getElementById('daysValue-modem').textContent = `${currentOrder.days} روز`;
            document.getElementById('daysInput-modem').value = currentOrder.days;
            document.getElementById('finalModemDays').textContent = `${currentOrder.days} روز`;
            updateModemPrice();
        }
        
        // به‌روزرسانی دستی روزها برای جنگی مودم
        function updateDaysInput(value, modalType) {
            let days = parseInt(value);
            if (isNaN(days)) days = 1;
            if (days < 1) days = 1;
            if (days > 30) days = 30;
            
            document.getElementById('daysSlider-modem').value = days;
            updateDays(days, 'modem');
        }
        
        // محاسبه قیمت نهایی جنگی مودم
        function updateModemPrice() {
            const prices = currentOrder.orderType === 'affiliate' ? modemPrices.affiliate : modemPrices.personal;
            const totalPrice = (currentOrder.volume * prices.perGB) + (currentOrder.days * prices.perDay);
            currentOrder.price = totalPrice;
            document.getElementById('finalModemPrice').textContent = totalPrice.toLocaleString('fa-IR');
        }
        
        // نمایش تب‌های مودال با انیمیشن
        function showModalTab(tabName, modalType) {
            const currentActiveTab = document.querySelector(`.modal-tab.${modalType}.active`);
            const currentActiveContent = document.querySelector(`.modal-tab-content.active#${currentActiveTab.getAttribute('onclick').match(/'([^']+)'/)[1]}Tab-${modalType}`);
            
            // انیمیشن fade-out برای تب فعلی
            currentActiveContent.style.animation = 'fadeOut 0.3s ease forwards';
            
            setTimeout(() => {
                // مخفی کردن تب فعلی
                currentActiveTab.classList.remove('active');
                currentActiveContent.classList.remove('active');
                currentActiveContent.style.animation = '';
                
                // نمایش تب جدید
                const newTab = document.querySelector(`.modal-tab.${modalType}[onclick="showModalTab('${tabName}', '${modalType}')"]`);
                const newContent = document.getElementById(`${tabName}Tab-${modalType}`);
                
                newTab.classList.add('active');
                newContent.classList.add('active');
                newContent.style.animation = 'fadeIn 0.3s ease forwards';
            }, 300);
        }
        
        // بستن مودال
        function closeModal() {
            document.getElementById('phoneModal').style.display = 'none';
            document.getElementById('modemModal').style.display = 'none';
            document.body.style.overflow = 'auto';
        }
        
        // ارسال سفارش
        function submitOrder(modalType) {
            let message = '';
            
            if (modalType === 'phone') {
                message = `سفارش جدید XRO VPN (جنگی گوشی):\nمدت: ${currentOrder.days} روز\nحجم: نامحدود\nنوع: ${currentOrder.orderType === 'affiliate' ? 'همکاری' : 'شخصی'}\nقیمت: ${currentOrder.price.toLocaleString('fa-IR')} تومان`;
            } else {
                message = `سفارش جدید XRO VPN (جنگی مودم):\nمدت: ${currentOrder.days} روز\nحجم: ${currentOrder.volume} گیگ\nنوع: ${currentOrder.orderType === 'affiliate' ? 'همکاری' : 'شخصی'}\nقیمت: ${currentOrder.price.toLocaleString('fa-IR')} تومان`;
            }
            
            window.open(`https://t.me/u0v0n?text=${encodeURIComponent(message)}`, '_blank');
            closeModal();
        }
        
        // کپی DNS
        function copyToClipboard(id) {
            const text = document.getElementById(id).textContent;
            navigator.clipboard.writeText(text).then(() => {
                showNotification('DNS با موفقیت کپی شد');
            }).catch(err => {
                console.error('خطا در کپی کردن متن: ', err);
                showNotification('خطا در کپی کردن DNS');
            });
        }
        
        // باز کردن استوری
        function openStory(type) {
            const storyModal = document.getElementById('storyModal');
            const storyTitle = document.getElementById('storyTitle');
            const storyText = document.getElementById('storyText');
            
            currentStoryIndex = storyKeys.indexOf(type);
            const story = stories[type];
            
            storyTitle.textContent = story.title;
            storyText.textContent = story.text;
            
            storyModal.style.display = 'block';
            document.body.style.overflow = 'hidden';
        }
        
        // بستن استوری
        function closeStory() {
            document.getElementById('storyModal').style.display = 'none';
            document.body.style.overflow = 'auto';
        }
        
        // استوری قبلی
        function prevStory() {
            currentStoryIndex = (currentStoryIndex - 1 + storyKeys.length) % storyKeys.length;
            const story = stories[storyKeys[currentStoryIndex]];
            
            document.getElementById('storyTitle').textContent = story.title;
            document.getElementById('storyText').textContent = story.text;
        }
        
        // استوری بعدی
        function nextStory() {
            currentStoryIndex = (currentStoryIndex + 1) % storyKeys.length;
            const story = stories[storyKeys[currentStoryIndex]];
            
            document.getElementById('storyTitle').textContent = story.title;
            document.getElementById('storyText').textContent = story.text;
        }
        
        // بستن با کلید ESC
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                closeModal();
                closeStory();
            }
        });
        
        // شمارنده و تغییر صفحه
        const loadingScreen = document.getElementById('loadingScreen');
        const mainScreen = document.getElementById('mainScreen');
        const loadingBar = document.getElementById('loadingBar');
        const counter = document.getElementById('counter');
        const mrText = document.querySelector('.mr');
        const xeroText = document.querySelector('.xero');
        const loadingFooter = document.querySelector('.loading-footer');
        
        let count = 0;
        const interval = setInterval(() => {
            if (count < 100) {
                count++;
                loadingBar.style.width = `${count}%`;
                counter.textContent = `${count}%`;
                
                const glowIntensity = count/3;
                loadingBar.style.boxShadow = `0 0 ${glowIntensity}px rgba(110, 69, 226, 0.7)`;
            } else {
                clearInterval(interval);
                
                // انیمیشن خروج بخش پایین
                loadingFooter.style.animation = 'fadeOut 0.8s forwards';
                
                // تاخیر قبل از انیمیشن خروج متن
                setTimeout(() => {
                    // انیمیشن خروج متن‌ها به جهت مخالف
                    mrText.style.animation = 'slideOutRight 0.8s forwards';
                    xeroText.style.animation = 'slideOutLeft 0.8s forwards';
                    
                    // نمایش صفحه اصلی پس از اتمام انیمیشن‌ها
                    setTimeout(() => {
                        loadingScreen.style.display = 'none';
                        mainScreen.style.display = 'block';
                        mainScreen.style.opacity = '1';
                        
                        // مقداردهی اولیه تب‌ها
                        showMainTab('home');
                        
                        // متن تایپ شونده
                        const typingText = document.getElementById('typingText');
                        const text = "آقای ایکسرا حامی آزادی است | در بدترین شرایط خدمات ما پیدار می‌ماند | فروش ماهانه +۱۰هزار کانفیگ شد!";
                        let i = 0;
                        
                        function typeWriter() {
                            if (i < text.length) {
                                typingText.textContent += text.charAt(i);
                                i++;
                                setTimeout(typeWriter, 100);
                            } else {
                                setTimeout(() => {
                                    typingText.textContent = '';
                                    i = 0;
                                    typeWriter();
                                }, 3000);
                            }
                        }
                        
                        typeWriter();
                    }, 800);
                }, 300);
            }
        }, 40);
    </script>
</body>
</html>
