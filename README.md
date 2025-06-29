<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>کانفیگ VIP | ایکسرو</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #6c5ce7;
            --secondary: #a29bfe;
            --accent: #00cec9;
            --dark: #0a0a12;
            --darker: #06060b;
            --text: #ffffff;
            --text-muted: #b8b8b8;
            --gold: #FFD700;
            --telegram: #0088cc;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Yekan', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            -webkit-tap-highlight-color: transparent;
            user-select: none;
            -webkit-user-select: none;
        }
        
        body {
            background-color: var(--dark);
            color: var(--text);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background-image: 
                linear-gradient(135deg, #0a0a12, #000000);
            overflow-x: hidden;
            position: relative;
        }
        
        /* صفحه اصلی */
        .main-container {
            width: 100%;
            max-width: 420px;
            height: 100vh;
            max-height: 850px;
            background: rgba(10, 10, 18, 0.9);
            border-radius: 20px;
            box-shadow: 
                0 0 30px rgba(0, 0, 0, 0.7);
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            display: flex;
            flex-direction: column;
        }
        
        /* هدر ثابت */
        .fixed-header {
            padding: 20px;
            background: linear-gradient(90deg, var(--accent), var(--primary));
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .app-title {
            font-size: 22px;
            font-weight: 800;
            color: white;
            letter-spacing: 1px;
        }
        
        .submit-ad-btn {
            padding: 10px 15px;
            border-radius: 8px;
            font-weight: 600;
            background: rgba(0, 0, 0, 0.3);
            color: white;
            border: none;
            cursor: pointer;
            transition: all 0.2s ease;
            font-size: 14px;
            display: flex;
            align-items: center;
            gap: 6px;
        }
        
        .submit-ad-btn:active {
            transform: scale(0.95);
        }
        
        /* محتوای قابل اسکرول */
        .scroll-content {
            flex: 1;
            overflow-y: auto;
            padding: 20px;
            display: flex;
            flex-direction: column;
            gap: 20px;
            -webkit-overflow-scrolling: touch;
        }
        
        /* بخش اسپانسر */
        .sponsor-card {
            background: rgba(0, 0, 0, 0.4);
            border-radius: 15px;
            padding: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 
                inset 0 0 15px rgba(0, 0, 0, 0.4);
        }
        
        .sponsor-title {
            font-size: 18px;
            font-weight: 700;
            color: var(--accent);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .sponsor-description {
            color: var(--text-muted);
            font-size: 14px;
            line-height: 1.6;
        }
        
        /* بخش کانفیگ */
        .config-section {
            background: rgba(0, 0, 0, 0.4);
            border-radius: 15px;
            padding: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 
                inset 0 0 15px rgba(0, 0, 0, 0.4);
        }
        
        .config-title {
            font-size: 18px;
            font-weight: 700;
            color: var(--accent);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .config-box {
            background: rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 255, 255, 0.15);
            border-radius: 12px;
            padding: 15px;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            line-height: 1.6;
            color: var(--accent);
            margin-bottom: 15px;
            text-align: center;
        }
        
        .config-content {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }
        
        .config-line {
            display: flex;
            justify-content: space-between;
            padding: 8px 0;
            border-bottom: 1px dashed rgba(255, 255, 255, 0.1);
        }
        
        .config-label {
            color: var(--text-muted);
        }
        
        .config-value {
            color: var(--accent);
            font-weight: 600;
        }
        
        .gold-text {
            color: var(--gold);
            font-weight: 700;
        }
        
        .action-buttons {
            display: flex;
            gap: 10px;
        }
        
        .action-btn {
            flex: 1;
            padding: 12px;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            border: none;
            font-size: 14px;
        }
        
        .action-btn:active {
            transform: scale(0.96);
        }
        
        .copy-btn {
            background: linear-gradient(135deg, var(--accent), #00b4b4);
            color: white;
        }
        
        .join-btn {
            background: linear-gradient(135deg, var(--telegram), #006699);
            color: white;
        }
        
        /* پنجره مودال */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.9);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.3s ease;
        }
        
        .modal-overlay.active {
            opacity: 1;
            pointer-events: all;
        }
        
        .modal-container {
            background: rgba(15, 15, 26, 0.95);
            border-radius: 20px;
            width: 90%;
            max-width: 400px;
            padding: 25px;
            box-shadow: 
                0 10px 30px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .modal-title {
            font-size: 20px;
            font-weight: 700;
            color: var(--accent);
        }
        
        .close-modal {
            background: none;
            border: none;
            color: var(--text-muted);
            font-size: 22px;
            cursor: pointer;
        }
        
        .modal-body {
            margin-bottom: 20px;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-label {
            display: block;
            margin-bottom: 8px;
            color: var(--text-muted);
            font-size: 14px;
        }
        
        .form-input {
            width: 100%;
            padding: 12px 15px;
            border-radius: 8px;
            background: rgba(0, 0, 0, 0.4);
            border: 1px solid rgba(255, 255, 255, 0.1);
            color: var(--text);
            font-size: 14px;
        }
        
        .form-input:focus {
            outline: none;
            border-color: var(--accent);
        }
        
        .submit-btn {
            width: 100%;
            padding: 14px;
            border-radius: 8px;
            background: linear-gradient(135deg, var(--primary), #5d4ae0);
            color: white;
            border: none;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s ease;
            margin-top: 10px;
        }
        
        .submit-btn:active {
            transform: scale(0.98);
        }
        
        /* نوتیفیکیشن */
        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            left: 20px;
            padding: 15px;
            border-radius: 12px;
            background: rgba(10, 10, 18, 0.95);
            color: white;
            box-shadow: 
                0 5px 20px rgba(0, 0, 0, 0.3);
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            display: flex;
            align-items: center;
            gap: 12px;
            z-index: 1000;
            border-left: 4px solid var(--accent);
            max-width: 400px;
            margin: 0 auto;
        }
        
        .notification.show {
            transform: translateY(0);
            opacity: 1;
        }
        
        /* اسکرول بار */
        ::-webkit-scrollbar {
            width: 5px;
        }
        
        ::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
        }
        
        ::-webkit-scrollbar-thumb {
            background: var(--primary);
            border-radius: 10px;
        }
        
        ::-webkit-scrollbar-thumb:hover {
            background: var(--secondary);
        }
        
        /* رسپانسیو */
        @media (max-width: 480px) {
            .main-container {
                border-radius: 0;
                max-height: none;
            }
            
            .action-buttons {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <div class="main-container">
        <!-- هدر ثابت -->
        <div class="fixed-header">
            <div class="app-title">ایکسرو</div>
            <button class="submit-ad-btn" id="openModalBtn">
                <i class="fas fa-ad"></i> ثبت تبلیغ
            </button>
        </div>
        
        <!-- محتوای قابل اسکرول -->
        <div class="scroll-content">
            <!-- بخش اسپانسر 1 -->
            <div class="sponsor-card">
                <div class="sponsor-title">
                    <i class="fas fa-question-circle"></i> چرا تبلیغات!؟
                </div>
                <div class="sponsor-description">
                    توجه داشته باشید سرویس اسپانسری بسته به زمان بندی حداقل ۲۴ و حداکثر ۷۲ ساعت کار می‌کند.
                </div>
            </div>
            
            <!-- بخش اسپانسر 2 (برای حالت تستی) -->
            <div class="sponsor-card">
                <div class="sponsor-title">
                    <i class="fas fa-info-circle"></i> وضعیت تستی
                </div>
                <div class="sponsor-description">
                    این بخش در حال تست می‌باشد و ممکن است تغییرات بیشتری داشته باشد.
                </div>
            </div>
            
            <!-- بخش کانفیگ VIP -->
            <div class="config-section">
                <div class="config-title">
                    <i class="fas fa-crown"></i> کانال اسپانسری
                </div>
                <div class="config-box">
                    <div class="config-content">
                        <div class="config-line">
                            <span class="config-label">نام کانال:</span>
                            <span class="config-value gold-text">زیروکسی</span>
                        </div>
                        <div class="config-line">
                            <span class="config-label">آیدی کانال:</span>
                            <span class="config-value">@xerox</span>
                        </div>
                        <div class="config-line">
                            <span class="config-label">دسته بندی:</span>
                            <span class="config-value">فروش گیف کارت</span>
                        </div>
                        <div class="config-line">
                            <span class="config-label">اعتبار:</span>
                            <span class="config-value">72 ساعت</span>
                        </div>
                    </div>
                </div>
                <div class="action-buttons">
                    <button class="action-btn copy-btn" onclick="copyConfig()">
                        <i class="far fa-copy"></i> کپی کانفیگ
                    </button>
                    <button class="action-btn join-btn" onclick="joinChannel()">
                        <i class="fab fa-telegram"></i> عضویت در کانال
                    </button>
                </div>
            </div>
        </div>
    </div>
    
    <!-- پنجره مودال ثبت تبلیغ -->
    <div class="modal-overlay" id="modalOverlay">
        <div class="modal-container">
            <div class="modal-header">
                <div class="modal-title">ثبت درخواست تبلیغ</div>
                <button class="close-modal" id="closeModalBtn">&times;</button>
            </div>
            <div class="modal-body">
                <div class="form-group">
                    <label class="form-label">نام کانال یا کسب‌وکار</label>
                    <input type="text" class="form-input" placeholder="مثال: ایکسرو" required>
                </div>
                <div class="form-group">
                    <label class="form-label">آیدی تلگرام</label>
                    <input type="text" class="form-input" placeholder="مثال: @xerox" required>
                </div>
                <div class="form-group">
                    <label class="form-label">توضیحات تبلیغ</label>
                    <textarea class="form-input" rows="3" placeholder="توضیحات درباره کانال یا خدمات شما" required></textarea>
                </div>
            </div>
            <button class="submit-btn" onclick="submitAd()">
                <i class="fas fa-paper-plane"></i> ارسال درخواست
            </button>
        </div>
    </div>
    
    <!-- اسکریپت‌ها -->
    <script>
        // جلوگیری از کپی متن
        document.addEventListener('copy', function(e) {
            e.preventDefault();
        });
        
        // کنترل مودال
        const modalOverlay = document.getElementById('modalOverlay');
        const openModalBtn = document.getElementById('openModalBtn');
        const closeModalBtn = document.getElementById('closeModalBtn');
        
        openModalBtn.addEventListener('click', () => {
            modalOverlay.classList.add('active');
            document.body.style.overflow = 'hidden';
        });
        
        closeModalBtn.addEventListener('click', () => {
            modalOverlay.classList.remove('active');
            document.body.style.overflow = '';
        });
        
        modalOverlay.addEventListener('click', (e) => {
            if (e.target === modalOverlay) {
                modalOverlay.classList.remove('active');
                document.body.style.overflow = '';
            }
        });
        
        // کپی کردن کانفیگ
        function copyConfig() {
            const configText = `نام کانال: زیروکسی\nآیدی کانال: @xerox\nدسته بندی: فروش گیف کارت\nاعتبار: 72 ساعت`;
            navigator.clipboard.writeText(configText).then(() => {
                showNotification('کانفیگ تبلیغاتی کپی شد!');
            }).catch(err => {
                console.error('خطا در کپی کردن: ', err);
            });
        }
        
        // عضویت در کانال تلگرام
        function joinChannel() {
            window.location.href = 'tg://resolve?domain=xerox';
        }
        
        // ثبت تبلیغ
        function submitAd() {
            showNotification('سیستم ثبت تبلیغ فعلا غیرفعال است');
            modalOverlay.classList.remove('active');
            document.body.style.overflow = '';
        }
        
        // نمایش نوتیفیکیشن
        function showNotification(message) {
            const notif = document.createElement('div');
            notif.className = 'notification';
            notif.innerHTML = `
                <i class="fas fa-info-circle"></i>
                ${message}
            `;
            document.body.appendChild(notif);
            
            setTimeout(() => {
                notif.classList.add('show');
            }, 10);
            
            setTimeout(() => {
                notif.classList.remove('show');
                setTimeout(() => {
                    document.body.removeChild(notif);
                }, 300);
            }, 3000);
        }
        
        // جلوگیری از زوم ناخواسته در موبایل
        document.addEventListener('touchmove', function (event) {
            if (event.scale !== 1) { event.preventDefault(); }
        }, { passive: false });
    </script>
</body>
</html>
