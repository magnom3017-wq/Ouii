<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Øu••ᵏᵃᵐᵃˡ࿐ - Social Media</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #8B5CF6;
            --secondary: #06D6A0;
            --accent: #EF476F;
            --dark: #0F0F0F;
            --darker: #070707;
            --light: #F8FAFC;
            --card-light: #FFFFFF;
            --card-dark: #1A1A1A;
            --text-light: #2D3748;
            --text-dark: #E2E8F0;
            --shadow: 0 10px 25px rgba(0,0,0,0.1);
            --gradient-1: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --gradient-2: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            --gradient-3: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
            --gradient-4: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
            --gradient-5: linear-gradient(135deg, #fa709a 0%, #fee140 100%);
            --gradient-6: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
            --gradient-7: linear-gradient(135deg, #d299c2 0%, #fef9d7 100%);
            --gradient-8: linear-gradient(135deg, #89f7fe 0%, #66a6ff 100%);
            --gradient-9: linear-gradient(135deg, #f6d365 0%, #fda085 100%);
        }
        
        body {
            background: linear-gradient(135deg, var(--light) 0%, #E2E8F0 100%);
            color: var(--text-light);
            min-height: 100vh;
            transition: all 0.4s ease;
            overflow-x: hidden;
        }
        
        body.dark-mode {
            background: linear-gradient(135deg, var(--dark) 0%, var(--darker) 100%);
            color: var(--text-dark);
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            margin-bottom: 30px;
            border-bottom: 2px solid rgba(139, 92, 246, 0.1);
        }
        
        .logo {
            font-size: 32px;
            font-weight: 800;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 2px 10px rgba(139, 92, 246, 0.3);
            animation: logoGlow 3s infinite alternate;
        }
        
        @keyframes logoGlow {
            0% { filter: drop-shadow(0 0 5px rgba(139, 92, 246, 0.5)); }
            100% { filter: drop-shadow(0 0 15px rgba(139, 92, 246, 0.8)); }
        }
        
        .header-buttons {
            display: flex;
            gap: 15px;
        }
        
        .icon-btn {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--card-light);
            border: none;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            color: var(--primary);
            font-size: 20px;
            position: relative;
            overflow: hidden;
        }
        
        .icon-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: 0.5s;
        }
        
        .icon-btn:hover::before {
            left: 100%;
        }
        
        .dark-mode .icon-btn {
            background: var(--card-dark);
            color: var(--secondary);
        }
        
        .icon-btn:hover {
            transform: translateY(-5px) rotate(5deg);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
        }
        
        /* شبكة البطاقات المحدثة - صفين */
        .social-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr); /* صفين */
            gap: 20px;
            margin-top: 20px;
        }
        
        /* تصميم البطاقات المميزة */
        .social-card {
            background: var(--card-light);
            border-radius: 20px;
            padding: 25px 20px;
            text-align: center;
            box-shadow: var(--shadow);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
            border: 2px solid transparent;
            position: relative;
            overflow: hidden;
            min-height: 220px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        
        /* تأثيرات خلفية البطاقات */
        .social-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 1px, transparent 1px);
            background-size: 20px 20px;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        
        .social-card:hover::before {
            opacity: 1;
        }
        
        .social-card:nth-child(1) {
            background: var(--gradient-1);
            animation: float 6s ease-in-out infinite;
        }
        
        .social-card:nth-child(2) {
            background: var(--gradient-2);
            animation: float 6s ease-in-out infinite 0.5s;
        }
        
        .social-card:nth-child(3) {
            background: var(--gradient-3);
            animation: float 6s ease-in-out infinite 1s;
        }
        
        .social-card:nth-child(4) {
            background: var(--gradient-4);
            animation: float 6s ease-in-out infinite 1.5s;
        }
        
        .social-card:nth-child(5) {
            background: var(--gradient-5);
            animation: float 6s ease-in-out infinite 2s;
        }
        
        .social-card:nth-child(6) {
            background: var(--gradient-6);
            animation: float 6s ease-in-out infinite 2.5s;
        }
        
        .social-card:nth-child(7) {
            background: var(--gradient-7);
            animation: float 6s ease-in-out infinite 3s;
        }
        
        .social-card:nth-child(8) {
            background: var(--gradient-8);
            animation: float 6s ease-in-out infinite 3.5s;
        }
        
        .social-card:nth-child(9) {
            background: var(--gradient-9);
            animation: float 6s ease-in-out infinite 4s;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0); }
            50% { transform: translateY(-10px) rotate(1deg); }
        }
        
        .dark-mode .social-card {
            border: 2px solid rgba(255,255,255,0.1);
        }
        
        .social-card:hover {
            transform: translateY(-15px) scale(1.05);
            box-shadow: 0 25px 50px rgba(0,0,0,0.25);
            border-color: rgba(255,255,255,0.3);
            z-index: 10;
        }
        
        /* الأيقونات المميزة */
        .social-icon {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 15px;
            font-size: 35px;
            color: white;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
            transition: all 0.4s ease;
            position: relative;
            z-index: 2;
            border: 3px solid rgba(255,255,255,0.3);
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
        }
        
        .social-card:hover .social-icon {
            transform: scale(1.2) rotate(360deg);
            box-shadow: 0 15px 30px rgba(0,0,0,0.3);
        }
        
        .social-icon i {
            filter: drop-shadow(0 2px 5px rgba(0,0,0,0.3));
        }
        
        .social-name {
            font-weight: 700;
            font-size: 18px;
            margin-bottom: 5px;
            color: white;
            text-shadow: 0 2px 5px rgba(0,0,0,0.3);
            position: relative;
            z-index: 2;
        }
        
        .social-username {
            color: rgba(255,255,255,0.9);
            font-size: 14px;
            direction: ltr;
            text-shadow: 0 1px 3px rgba(0,0,0,0.3);
            position: relative;
            z-index: 2;
            background: rgba(0,0,0,0.2);
            padding: 3px 10px;
            border-radius: 20px;
            display: inline-block;
            margin-top: 5px;
        }
        
        /* نافذة المشاركة */
        .share-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(0,0,0,0.9);
            z-index: 9999;
            align-items: center;
            justify-content: center;
            overflow: auto;
        }
        
        .share-content {
            background: var(--darker);
            border-radius: 25px;
            padding: 40px;
            text-align: center;
            max-width: 400px;
            width: 90%;
            height: auto;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 0 25px 50px rgba(0,0,0,0.5);
            border: 2px solid var(--primary);
            position: relative;
            z-index: 10000;
            animation: modalAppear 0.5s ease-out;
        }
        
        @keyframes modalAppear {
            0% { transform: scale(0.8) translateY(50px); opacity: 0; }
            100% { transform: scale(1) translateY(0); opacity: 1; }
        }
        
        .share-title {
            color: white;
            font-size: 24px;
            margin-bottom: 25px;
            font-weight: 700;
        }
        
        .qrcode-container {
            background: white;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
            display: inline-block;
            min-width: 200px;
            min-height: 200px;
            display: flex;
            align-items: center;
            justify-content: center;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.03); }
        }
        
        #modalQRCode {
            width: 200px;
            height: 200px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .share-buttons {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-top: 25px;
        }
        
        .share-btn {
            padding: 15px;
            border: none;
            border-radius: 12px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            font-size: 16px;
            width: 100%;
            position: relative;
            overflow: hidden;
        }
        
        .share-btn::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 5px;
            height: 5px;
            background: rgba(255, 255, 255, 0.5);
            opacity: 0;
            border-radius: 100%;
            transform: scale(1, 1) translate(-50%);
            transform-origin: 50% 50%;
        }
        
        .share-btn:focus:not(:active)::after {
            animation: ripple 1s ease-out;
        }
        
        @keyframes ripple {
            0% { transform: scale(0, 0); opacity: 0.5; }
            100% { transform: scale(20, 20); opacity: 0; }
        }
        
        .download-btn {
            background: linear-gradient(135deg, var(--primary), #7c3aed);
            color: white;
        }
        
        .copy-btn {
            background: linear-gradient(135deg, var(--accent), #d12e5a);
            color: white;
        }
        
        .share-app-btn {
            background: linear-gradient(135deg, var(--secondary), #05b887);
            color: white;
        }
        
        .phone-btn {
            background: linear-gradient(135deg, #34A853, #2E8B57);
            color: white;
        }
        
        .email-btn {
            background: linear-gradient(135deg, #EA4335, #D14836);
            color: white;
        }
        
        .share-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.3);
        }
        
        .close-share {
            position: absolute;
            top: 20px;
            left: 20px;
            background: none;
            border: none;
            color: white;
            font-size: 24px;
            cursor: pointer;
            z-index: 10001;
            transition: transform 0.3s ease;
        }
        
        .close-share:hover {
            transform: rotate(90deg);
        }
        
        /* تصميم خاص للهاتف والبريد الإلكتروني */
        .phone-modal .share-buttons,
        .email-modal .share-buttons {
            grid-template-columns: 1fr 1fr;
            display: grid;
            gap: 15px;
        }
        
        .phone-modal .qrcode-container,
        .email-modal .qrcode-container {
            display: none;
        }
        
        /* ألوان وسائل التواصل */
        .facebook { background: linear-gradient(135deg, #1877F2, #0D5FBF); }
        .instagram { background: linear-gradient(135deg, #E4405F, #C13584, #F77737); }
        .telegram { background: linear-gradient(135deg, #0088CC, #006699); }
        .snapchat { background: linear-gradient(135deg, #FFFC00, #FFD700); }
        .tiktok { background: linear-gradient(135deg, #000000, #25F4EE, #FE2C55); }
        .youtube { background: linear-gradient(135deg, #FF0000, #CC0000); }
        .twitter { background: linear-gradient(135deg, #1DA1F2, #0D8BD9); }
        .email-card { background: linear-gradient(135deg, #EA4335, #D14836, #FBBC05); }
        .phone-card { background: linear-gradient(135deg, #34A853, #2E8B57, #0D652D); }
        
        /* التأثيرات النصية */
        .social-card .highlight {
            display: inline-block;
            position: relative;
            color: white;
            font-weight: bold;
            padding: 0 5px;
        }
        
        .social-card .highlight::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            width: 100%;
            height: 2px;
            background: white;
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }
        
        .social-card:hover .highlight::after {
            transform: scaleX(1);
        }
        
        /* تأثيرات إضافية للبطاقات */
        .social-card .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }
        
        /* تصميم متجاوب */
        @media (max-width: 768px) {
            .social-grid {
                grid-template-columns: 1fr; /* عمود واحد على الهواتف */
                gap: 15px;
            }
            
            .logo {
                font-size: 24px;
            }
            
            .social-icon {
                width: 70px;
                height: 70px;
                font-size: 30px;
            }
            
            .social-card {
                padding: 20px 15px;
                min-height: 200px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="logo">Øu••ᵏᵃᵐᵃˡ࿐</div>
            <div class="header-buttons">
                <button class="icon-btn" id="darkModeToggle"><i class="fas fa-moon"></i></button>
                <button class="icon-btn" id="shareBtn"><i class="fas fa-share-alt"></i></button>
            </div>
        </div>
        
        <div class="social-grid">
            <!-- فيسبوك -->
            <div class="social-card" data-name="فيسبوك" data-link="https://www.facebook.com/share/1BgY11DMQM/" data-icon="facebook" data-type="social">
                <div class="social-icon facebook"><i class="fab fa-facebook-f"></i></div>
                <div class="social-name">فيسبوك</div>
                <div class="social-username">Kamola</div>
            </div>
            
            <!-- إنستغرام -->
            <div class="social-card" data-name="إنستغرام" data-link="https://www.instagram.com/kamola_463" data-icon="instagram" data-type="social">
                <div class="social-icon instagram"><i class="fab fa-instagram"></i></div>
                <div class="social-name">إنستغرام</div>
                <div class="social-username">@kamola_463</div>
            </div>
            
            <!-- تيليجرام -->
            <div class="social-card" data-name="تيليجرام" data-link="https://t.me/ou_kamel" data-icon="telegram" data-type="social">
                <div class="social-icon telegram"><i class="fab fa-telegram-plane"></i></div>
                <div class="social-name">تيليجرام</div>
                <div class="social-username">@ou_kamel</div>
            </div>
            
            <!-- سناب شات -->
            <div class="social-card" data-name="سناب شات" data-link="https://www.snapchat.com/add/kamola252903" data-icon="snapchat" data-type="social">
                <div class="social-icon snapchat"><i class="fab fa-snapchat-ghost"></i></div>
                <div class="social-name">سناب شات</div>
                <div class="social-username">kamola252903</div>
            </div>
            
            <!-- تيك توك -->
            <div class="social-card" data-name="تيك توك" data-link="https://www.tiktok.com/@kamola.3017" data-icon="tiktok" data-type="social">
                <div class="social-icon tiktok"><i class="fab fa-tiktok"></i></div>
                <div class="social-name">تيك توك</div>
                <div class="social-username">@kamola.3017</div>
            </div>
            
            <!-- يوتيوب -->
            <div class="social-card" data-name="يوتيوب" data-link="https://www.youtube.com/@kamola3017" data-icon="youtube" data-type="social">
                <div class="social-icon youtube"><i class="fab fa-youtube"></i></div>
                <div class="social-name">يوتيوب</div>
                <div class="social-username">@kamola3017</div>
            </div>
            
            <!-- تويتر -->
            <div class="social-card" data-name="تويتر" data-link="https://x.com/3017Kamola44307?t=107y45_c29JA1E-ClTzg_A&s=09" data-icon="twitter" data-type="social">
                <div class="social-icon twitter"><i class="fab fa-twitter"></i></div>
                <div class="social-name">تويتر</div>
                <div class="social-username">@3017Kamola44307</div>
            </div>
            
            <!-- البريد الإلكتروني -->
            <div class="social-card" data-name="البريد الإلكتروني" data-link="mailto:magnom3017@gmail.com" data-icon="email" data-type="email">
                <div class="social-icon email-card"><i class="fas fa-envelope"></i></div>
                <div class="social-name">البريد الإلكتروني</div>
                <div class="social-username">magnom3017@gmail.com</div>
            </div>
            
            <!-- رقم الهاتف -->
            <div class="social-card" data-name="رقم الهاتف" data-link="tel:+962776274508" data-icon="phone" data-type="phone">
                <div class="social-icon phone-card"><i class="fas fa-phone"></i></div>
                <div class="social-name">رقم الهاتف</div>
                <div class="social-username">+962 776 274508</div>
            </div>
        </div>
    </div>
    
    <!-- نافذة المشاركة -->
    <div class="share-modal" id="shareModal">
        <button class="close-share" id="closeShareBtn"><i class="fas fa-times"></i></button>
        <div class="share-content" id="shareContent">
            <h2 class="share-title" id="modalAppName">اسم التطبيق</h2>
            <div class="qrcode-container" id="qrContainer">
                <div id="modalQRCode"></div>
            </div>
            <div class="share-buttons" id="actionButtons">
                <!-- الأزرار ستضاف ديناميكياً -->
            </div>
        </div>
    </div>
    
    <script>
        // الوضع المظلم
        const darkModeToggle = document.getElementById('darkModeToggle');
        const body = document.body;
        
        darkModeToggle.addEventListener('click', () => {
            body.classList.toggle('dark-mode');
            const icon = darkModeToggle.querySelector('i');
            if (body.classList.contains('dark-mode')) {
                icon.classList.replace('fa-moon', 'fa-sun');
            } else {
                icon.classList.replace('fa-sun', 'fa-moon');
            }
        });
        
        // نافذة المشاركة
        const shareModal = document.getElementById('shareModal');
        const modalAppName = document.getElementById('modalAppName');
        const modalQRCodeElement = document.getElementById('modalQRCode');
        const shareContent = document.getElementById('shareContent');
        const qrContainer = document.getElementById('qrContainer');
        const actionButtons = document.getElementById('actionButtons');
        const closeShareBtn = document.getElementById('closeShareBtn');
        
        let currentQRCode = null;
        let currentLink = '';
        let currentType = '';
        
        // فتح النافذة عند النقر على البطاقات
        document.querySelectorAll('.social-card').forEach(card => {
            card.addEventListener('click', () => {
                const name = card.getAttribute('data-name');
                const link = card.getAttribute('data-link');
                const type = card.getAttribute('data-type');
                
                modalAppName.textContent = name;
                currentLink = link;
                currentType = type;
                
                // إعداد واجهة النافذة حسب النوع
                setupModal(type, link, name);
                
                shareModal.style.display = 'flex';
                document.body.style.overflow = 'hidden';
            });
        });
        
        function setupModal(type, link, name) {
            // مسح الأزرار السابقة
            actionButtons.innerHTML = '';
            
            if (type === 'phone') {
                // واجهة الهاتف: زر اتصال وزر نسخ فقط
                qrContainer.style.display = 'none';
                
                const callBtn = document.createElement('button');
                callBtn.className = 'share-btn phone-btn';
                callBtn.innerHTML = '<i class="fas fa-phone"></i> اتصال';
                callBtn.onclick = () => window.open(link, '_self');
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'share-btn copy-btn';
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> نسخ الرقم';
                copyBtn.onclick = () => {
                    const phoneNumber = link.replace('tel:', '');
                    navigator.clipboard.writeText(phoneNumber).then(() => {
                        alert('تم نسخ الرقم: ' + phoneNumber);
                    });
                };
                
                actionButtons.appendChild(callBtn);
                actionButtons.appendChild(copyBtn);
                
            } else if (type === 'email') {
                // واجهة البريد الإلكتروني: زر إرسال وزر نسخ فقط
                qrContainer.style.display = 'none';
                
                const emailBtn = document.createElement('button');
                emailBtn.className = 'share-btn email-btn';
                emailBtn.innerHTML = '<i class="fas fa-paper-plane"></i> إرسال بريد';
                emailBtn.onclick = () => window.open(link, '_self');
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'share-btn copy-btn';
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> نسخ البريد';
                copyBtn.onclick = () => {
                    const email = link.replace('mailto:', '');
                    navigator.clipboard.writeText(email).then(() => {
                        alert('تم نسخ البريد: ' + email);
                    });
                };
                
                actionButtons.appendChild(emailBtn);
                actionButtons.appendChild(copyBtn);
                
            } else {
                // واجهة وسائل التواصل: QR Code وأزرار كاملة
                qrContainer.style.display = 'inline-block';
                
                // إنشاء QR Code
                modalQRCodeElement.innerHTML = '';
                currentQRCode = new QRCode(modalQRCodeElement, {
                    text: link,
                    width: 200,
                    height: 200,
                    colorDark: "#000000",
                    colorLight: "#ffffff",
                    correctLevel: QRCode.CorrectLevel.H
                });
                
                // أزرار وسائل التواصل
                const downloadBtn = document.createElement('button');
                downloadBtn.className = 'share-btn download-btn';
                downloadBtn.innerHTML = '<i class="fas fa-download"></i> تحميل QR Code';
                downloadBtn.onclick = () => {
                    if (currentQRCode) {
                        const canvas = modalQRCodeElement.querySelector('canvas');
                        if (canvas) {
                            const linkElement = document.createElement('a');
                            linkElement.download = `QR-${name}.png`;
                            linkElement.href = canvas.toDataURL();
                            linkElement.click();
                        }
                    }
                };
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'share-btn copy-btn';
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> نسخ الرابط';
                copyBtn.onclick = () => {
                    navigator.clipboard.writeText(link).then(() => {
                        alert('تم نسخ الرابط: ' + link);
                    });
                };
                
                const openBtn = document.createElement('button');
                openBtn.className = 'share-btn share-app-btn';
                openBtn.innerHTML = '<i class="fas fa-external-link-alt"></i> فتح التطبيق';
                openBtn.onclick = () => window.open(link, '_blank');
                
                actionButtons.appendChild(downloadBtn);
                actionButtons.appendChild(copyBtn);
                actionButtons.appendChild(openBtn);
            }
        }
        
        // زر إغلاق النافذة
        closeShareBtn.addEventListener('click', () => {
            shareModal.style.display = 'none';
            document.body.style.overflow = '';
        });
        
        // إغلاق النافذة عند النقر خارجها
        window.addEventListener('click', (e) => {
            if (e.target === shareModal) {
                shareModal.style.display = 'none';
                document.body.style.overflow = '';
            }
        });
        
        // زر المشاركة في الهيدر
        document.getElementById('shareBtn').addEventListener('click', () => {
            if (navigator.share) {
                navigator.share({
                    title: 'Øu••ᵏᵃᵐᵃˡ࿐ - وسائل التواصل',
                    text: 'تعرف على روابط وسائل التواصل الخاصة بي',
                    url: window.location.href
                });
            } else {
                navigator.clipboard.writeText(window.location.href).then(() => {
                    alert('تم نسخ رابط الموقع إلى الحافظة');
                });
            }
        });
        
        // تأثيرات إضافية للبطاقات عند التحميل
        document.addEventListener('DOMContentLoaded', () => {
            const cards = document.querySelectorAll('.social-card');
            cards.forEach((card, index) => {
                card.style.animationDelay = `${index * 0.1}s`;
            });
        });
    </script>
</body>
</html>
