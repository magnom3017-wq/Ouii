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
            font-family: 'Poppins', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&display=swap');
        
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
            --shadow: 0 20px 40px rgba(0,0,0,0.15);
            
            /* ألوان التدرجات للبطاقات */
            --gradient-facebook: linear-gradient(135deg, #1877F2, #0D5FBF, #0A49B0);
            --gradient-instagram: linear-gradient(135deg, #E4405F, #C13584, #833AB4, #5851DB, #405DE6);
            --gradient-telegram: linear-gradient(135deg, #0088CC, #006699, #005580);
            --gradient-snapchat: linear-gradient(135deg, #FFFC00, #FFD700, #FFC400);
            --gradient-tiktok: linear-gradient(135deg, #000000, #25F4EE, #FE2C55);
            --gradient-youtube: linear-gradient(135deg, #FF0000, #CC0000, #990000);
            --gradient-twitter: linear-gradient(135deg, #1DA1F2, #0D8BD9, #0A7BC8);
            --gradient-email: linear-gradient(135deg, #EA4335, #D14836, #FBBC05);
            --gradient-phone: linear-gradient(135deg, #34A853, #2E8B57, #0D652D);
        }
        
        body {
            background: linear-gradient(45deg, 
                #0f0c29, #302b63, #24243e);
            color: var(--text-light);
            min-height: 100vh;
            transition: all 0.4s ease;
            overflow-x: hidden;
            position: relative;
        }
        
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 80%, rgba(120, 119, 198, 0.3) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255, 119, 198, 0.3) 0%, transparent 50%),
                radial-gradient(circle at 40% 40%, rgba(120, 219, 255, 0.3) 0%, transparent 50%);
            z-index: -2;
            animation: backgroundMove 20s infinite alternate;
        }
        
        @keyframes backgroundMove {
            0% { transform: translate(0, 0) scale(1); }
            100% { transform: translate(-50px, -50px) scale(1.1); }
        }
        
        body.dark-mode {
            background: linear-gradient(45deg, 
                #000000, #0a0a0a, #1a1a1a);
        }
        
        .container {
            width: 100%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }
        
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 30px 0;
            margin-bottom: 50px;
            position: relative;
        }
        
        .logo {
            font-size: 42px;
            font-weight: 900;
            background: linear-gradient(135deg, #00dbde, #fc00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 30px rgba(0, 219, 222, 0.5);
            animation: logoGlow 3s infinite alternate, float 6s ease-in-out infinite;
            position: relative;
            padding: 10px 20px;
            border-radius: 20px;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        @keyframes logoGlow {
            0% { filter: drop-shadow(0 0 10px rgba(0, 219, 222, 0.5)); }
            100% { filter: drop-shadow(0 0 30px rgba(252, 0, 255, 0.8)); }
        }
        
        .header-buttons {
            display: flex;
            gap: 20px;
        }
        
        .icon-btn {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(135deg, rgba(255,255,255,0.1), rgba(255,255,255,0.05));
            border: 1px solid rgba(255,255,255,0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            color: white;
            font-size: 24px;
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(10px);
        }
        
        .icon-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: 0.5s;
        }
        
        .icon-btn:hover::before {
            left: 100%;
        }
        
        .icon-btn:hover {
            transform: translateY(-10px) scale(1.1);
            box-shadow: 0 20px 40px rgba(0,0,0,0.4);
        }
        
        /* شبكة البطاقات - صفين افقيين */
        .social-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr); /* صفين افقيين */
            gap: 30px;
            margin-top: 30px;
            perspective: 1000px;
        }
        
        /* تصميم البطاقات ثلاثية الأبعاد */
        .social-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 25px;
            padding: 40px 30px;
            text-align: center;
            box-shadow: 
                0 20px 40px rgba(0,0,0,0.2),
                inset 0 1px 0 rgba(255,255,255,0.1);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
            border: 1px solid rgba(255,255,255,0.1);
            position: relative;
            overflow: hidden;
            min-height: 320px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            transform-style: preserve-3d;
            animation: waveFloat 8s ease-in-out infinite;
            backdrop-filter: blur(10px);
        }
        
        /* حركة الموجة المختلفة لكل بطاقة */
        .social-card:nth-child(1) { animation-delay: 0s; }
        .social-card:nth-child(2) { animation-delay: 0.5s; }
        .social-card:nth-child(3) { animation-delay: 1s; }
        .social-card:nth-child(4) { animation-delay: 1.5s; }
        .social-card:nth-child(5) { animation-delay: 2s; }
        .social-card:nth-child(6) { animation-delay: 2.5s; }
        .social-card:nth-child(7) { animation-delay: 3s; }
        .social-card:nth-child(8) { animation-delay: 3.5s; }
        .social-card:nth-child(9) { animation-delay: 4s; }
        
        @keyframes waveFloat {
            0%, 100% { 
                transform: translateY(0) rotateX(0) rotateY(0); 
            }
            25% { 
                transform: translateY(-20px) rotateX(5deg) rotateY(5deg); 
            }
            50% { 
                transform: translateY(-10px) rotateX(-5deg) rotateY(-5deg); 
            }
            75% { 
                transform: translateY(-15px) rotateX(3deg) rotateY(-3deg); 
            }
        }
        
        /* تأثيرات خلفية البطاقات */
        .social-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(
                from 0deg,
                transparent,
                rgba(255,255,255,0.1),
                transparent
            );
            animation: rotate 10s linear infinite;
        }
        
        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* خلفية داخلية للبطاقات */
        .social-card::after {
            content: '';
            position: absolute;
            inset: 5px;
            background: inherit;
            border-radius: 20px;
            z-index: -1;
        }
        
        /* تطبيق التدرجات الخاصة لكل بطاقة */
        .facebook-card { background: var(--gradient-facebook); }
        .instagram-card { background: var(--gradient-instagram); }
        .telegram-card { background: var(--gradient-telegram); }
        .snapchat-card { background: var(--gradient-snapchat); }
        .tiktok-card { background: var(--gradient-tiktok); }
        .youtube-card { background: var(--gradient-youtube); }
        .twitter-card { background: var(--gradient-twitter); }
        .email-card { background: var(--gradient-email); }
        .phone-card { background: var(--gradient-phone); }
        
        /* تأثير المرور */
        .social-card:hover {
            transform: translateY(-30px) scale(1.08) rotateX(10deg) rotateY(10deg);
            box-shadow: 
                0 40px 80px rgba(0,0,0,0.4),
                0 0 60px rgba(255,255,255,0.2),
                inset 0 1px 0 rgba(255,255,255,0.2);
            z-index: 100;
        }
        
        /* الأيقونات ثلاثية الأبعاد */
        .social-icon {
            width: 100px;
            height: 100px;
            border-radius: 25px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 25px;
            font-size: 45px;
            color: white;
            box-shadow: 
                0 15px 35px rgba(0,0,0,0.3),
                inset 0 5px 15px rgba(255,255,255,0.1);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            z-index: 2;
            border: 2px solid rgba(255,255,255,0.2);
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(5px);
            transform-style: preserve-3d;
        }
        
        .social-card:hover .social-icon {
            transform: scale(1.3) rotateY(360deg);
            box-shadow: 
                0 25px 50px rgba(0,0,0,0.4),
                0 0 40px rgba(255,255,255,0.3);
        }
        
        .social-icon i {
            filter: drop-shadow(0 5px 10px rgba(0,0,0,0.3));
            text-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }
        
        /* النصوص */
        .social-name {
            font-weight: 800;
            font-size: 24px;
            margin-bottom: 10px;
            color: white;
            text-shadow: 0 2px 10px rgba(0,0,0,0.5);
            position: relative;
            z-index: 2;
            letter-spacing: 1px;
        }
        
        .social-username {
            color: rgba(255,255,255,0.9);
            font-size: 16px;
            direction: ltr;
            text-shadow: 0 1px 5px rgba(0,0,0,0.3);
            position: relative;
            z-index: 2;
            background: rgba(0,0,0,0.3);
            padding: 8px 20px;
            border-radius: 50px;
            display: inline-block;
            margin-top: 10px;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        /* النافذة المنبثقة الجديدة */
        .share-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(0,0,0,0.95);
            z-index: 9999;
            align-items: center;
            justify-content: center;
            overflow: auto;
            backdrop-filter: blur(10px);
        }
        
        .share-content {
            background: linear-gradient(135deg, 
                rgba(20, 20, 40, 0.95), 
                rgba(30, 30, 60, 0.95));
            border-radius: 30px;
            padding: 50px;
            text-align: center;
            max-width: 450px;
            width: 90%;
            height: auto;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 
                0 30px 60px rgba(0,0,0,0.5),
                0 0 0 1px rgba(255,255,255,0.1);
            border: 2px solid transparent;
            position: relative;
            z-index: 10000;
            animation: modalAppear 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            backdrop-filter: blur(20px);
            transform-style: preserve-3d;
            transform: perspective(1000px) rotateY(0deg);
        }
        
        .share-content::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, 
                #ff0000, #ff9900, #ffff00, #00ff00, 
                #00ffff, #0000ff, #9900ff, #ff00ff);
            border-radius: 32px;
            z-index: -1;
            animation: borderRotate 5s linear infinite;
            filter: blur(10px);
        }
        
        @keyframes borderRotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        @keyframes modalAppear {
            0% { transform: perspective(1000px) rotateY(90deg) scale(0.5); opacity: 0; }
            100% { transform: perspective(1000px) rotateY(0deg) scale(1); opacity: 1; }
        }
        
        .share-title {
            color: white;
            font-size: 32px;
            margin-bottom: 30px;
            font-weight: 800;
            text-shadow: 0 2px 20px rgba(0,0,0,0.5);
            background: linear-gradient(135deg, #00dbde, #fc00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        /* تصميم QR Code ثلاثي الأبعاد */
        .qr-container-3d {
            background: linear-gradient(135deg, 
                rgba(255,255,255,0.1), 
                rgba(255,255,255,0.05));
            padding: 30px;
            border-radius: 20px;
            margin: 30px 0;
            display: inline-block;
            position: relative;
            transform-style: preserve-3d;
            transform: perspective(500px) rotateX(10deg);
            animation: qrFloat 4s ease-in-out infinite;
            box-shadow: 
                0 20px 40px rgba(0,0,0,0.3),
                inset 0 1px 0 rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        @keyframes qrFloat {
            0%, 100% { transform: perspective(500px) rotateX(10deg) translateY(0); }
            50% { transform: perspective(500px) rotateX(10deg) translateY(-10px); }
        }
        
        .qr-header {
            position: absolute;
            top: -40px;
            left: 50%;
            transform: translateX(-50%);
            background: linear-gradient(135deg, #00dbde, #fc00ff);
            padding: 10px 30px;
            border-radius: 50px;
            color: white;
            font-weight: 600;
            font-size: 18px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
            z-index: 10;
        }
        
        #modalQRCode {
            width: 220px;
            height: 220px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            z-index: 2;
        }
        
        /* تصميم خاص للهاتف والبريد */
        .simple-buttons {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-top: 30px;
        }
        
        .action-btn {
            padding: 20px;
            border: none;
            border-radius: 15px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 10px;
            font-size: 18px;
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.1);
            color: white;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }
        
        .action-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: 0.5s;
        }
        
        .action-btn:hover::before {
            left: 100%;
        }
        
        .call-btn {
            background: linear-gradient(135deg, #34A853, #2E8B57);
        }
        
        .copy-btn-simple {
            background: linear-gradient(135deg, #EF476F, #D12E5A);
        }
        
        .email-btn-simple {
            background: linear-gradient(135deg, #EA4335, #D14836);
        }
        
        .action-btn:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }
        
        .action-btn i {
            font-size: 28px;
            filter: drop-shadow(0 2px 5px rgba(0,0,0,0.3));
        }
        
        .close-share {
            position: absolute;
            top: 25px;
            left: 25px;
            background: linear-gradient(135deg, #EF476F, #D12E5A);
            border: none;
            color: white;
            font-size: 24px;
            cursor: pointer;
            z-index: 10001;
            transition: all 0.3s ease;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 10px 20px rgba(0,0,0,0.3);
        }
        
        .close-share:hover {
            transform: rotate(180deg) scale(1.1);
            box-shadow: 0 15px 30px rgba(0,0,0,0.4);
        }
        
        /* تصميم متجاوب */
        @media (max-width: 768px) {
            .social-grid {
                grid-template-columns: 1fr;
                gap: 20px;
            }
            
            .logo {
                font-size: 28px;
            }
            
            .social-icon {
                width: 80px;
                height: 80px;
                font-size: 35px;
            }
            
            .social-card {
                padding: 30px 20px;
                min-height: 280px;
            }
            
            .simple-buttons {
                grid-template-columns: 1fr;
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
            <div class="social-card facebook-card" data-name="فيسبوك" data-link="https://www.facebook.com/share/1BgY11DMQM/" data-icon="facebook" data-type="social">
                <div class="social-icon"><i class="fab fa-facebook-f"></i></div>
                <div class="social-name">فيسبوك</div>
                <div class="social-username">Kamola</div>
            </div>
            
            <!-- إنستغرام -->
            <div class="social-card instagram-card" data-name="إنستغرام" data-link="https://www.instagram.com/kamola_463" data-icon="instagram" data-type="social">
                <div class="social-icon"><i class="fab fa-instagram"></i></div>
                <div class="social-name">إنستغرام</div>
                <div class="social-username">@kamola_463</div>
            </div>
            
            <!-- تيليجرام -->
            <div class="social-card telegram-card" data-name="تيليجرام" data-link="https://t.me/ou_kamel" data-icon="telegram" data-type="social">
                <div class="social-icon"><i class="fab fa-telegram-plane"></i></div>
                <div class="social-name">تيليجرام</div>
                <div class="social-username">@ou_kamel</div>
            </div>
            
            <!-- سناب شات -->
            <div class="social-card snapchat-card" data-name="سناب شات" data-link="https://www.snapchat.com/add/kamola252903" data-icon="snapchat" data-type="social">
                <div class="social-icon"><i class="fab fa-snapchat-ghost"></i></div>
                <div class="social-name">سناب شات</div>
                <div class="social-username">kamola252903</div>
            </div>
            
            <!-- تيك توك -->
            <div class="social-card tiktok-card" data-name="تيك توك" data-link="https://www.tiktok.com/@kamola.3017" data-icon="tiktok" data-type="social">
                <div class="social-icon"><i class="fab fa-tiktok"></i></div>
                <div class="social-name">تيك توك</div>
                <div class="social-username">@kamola.3017</div>
            </div>
            
            <!-- يوتيوب -->
            <div class="social-card youtube-card" data-name="يوتيوب" data-link="https://www.youtube.com/@kamola3017" data-icon="youtube" data-type="social">
                <div class="social-icon"><i class="fab fa-youtube"></i></div>
                <div class="social-name">يوتيوب</div>
                <div class="social-username">@kamola3017</div>
            </div>
            
            <!-- تويتر -->
            <div class="social-card twitter-card" data-name="تويتر" data-link="https://x.com/3017Kamola44307?t=107y45_c29JA1E-ClTzg_A&s=09" data-icon="twitter" data-type="social">
                <div class="social-icon"><i class="fab fa-twitter"></i></div>
                <div class="social-name">تويتر</div>
                <div class="social-username">@3017Kamola44307</div>
            </div>
            
            <!-- البريد الإلكتروني -->
            <div class="social-card email-card" data-name="البريد الإلكتروني" data-link="mailto:magnom3017@gmail.com" data-icon="email" data-type="email">
                <div class="social-icon"><i class="fas fa-envelope"></i></div>
                <div class="social-name">البريد الإلكتروني</div>
                <div class="social-username">magnom3017@gmail.com</div>
            </div>
            
            <!-- رقم الهاتف -->
            <div class="social-card phone-card" data-name="رقم الهاتف" data-link="tel:+962776274508" data-icon="phone" data-type="phone">
                <div class="social-icon"><i class="fas fa-phone"></i></div>
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
            <div id="qrContainer">
                <!-- محتوى QR Code أو الأزرار سيتم إضافته ديناميكياً -->
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
        const qrContainer = document.getElementById('qrContainer');
        const closeShareBtn = document.getElementById('closeShareBtn');
        
        let currentQRCode = null;
        let currentLink = '';
        let currentType = '';
        let currentName = '';
        
        // إضافة تأثيرات للبطاقات عند التحميل
        document.addEventListener('DOMContentLoaded', () => {
            const cards = document.querySelectorAll('.social-card');
            cards.forEach((card, index) => {
                // تأخير لكل بطاقة لتأثير تسلسلي
                card.style.animationDelay = `${index * 0.2}s`;
                
                // إضافة تأثيرات CSS عند التحميل
                card.style.opacity = '0';
                card.style.transform = 'translateY(50px) scale(0.8)';
                
                setTimeout(() => {
                    card.style.transition = 'all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275)';
                    card.style.opacity = '1';
                    card.style.transform = 'translateY(0) scale(1)';
                }, index * 100);
            });
        });
        
        // فتح النافذة عند النقر على البطاقات
        document.querySelectorAll('.social-card').forEach(card => {
            card.addEventListener('click', () => {
                const name = card.getAttribute('data-name');
                const link = card.getAttribute('data-link');
                const type = card.getAttribute('data-type');
                const iconClass = card.querySelector('.social-icon i').className;
                
                modalAppName.textContent = name;
                currentLink = link;
                currentType = type;
                currentName = name;
                
                // إعداد واجهة النافذة حسب النوع
                setupModal(type, link, name, iconClass);
                
                shareModal.style.display = 'flex';
                document.body.style.overflow = 'hidden';
                
                // تأثير ظهور النافذة
                const shareContent = document.querySelector('.share-content');
                shareContent.style.animation = 'none';
                setTimeout(() => {
                    shareContent.style.animation = 'modalAppear 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275)';
                }, 10);
            });
        });
        
        function setupModal(type, link, name, iconClass) {
            // مسح المحتوى السابق
            qrContainer.innerHTML = '';
            
            if (type === 'phone') {
                // واجهة الهاتف: زر اتصال وزر نسخ فقط
                const buttonsDiv = document.createElement('div');
                buttonsDiv.className = 'simple-buttons';
                
                const callBtn = document.createElement('button');
                callBtn.className = 'action-btn call-btn';
                callBtn.innerHTML = `
                    <i class="fas fa-phone"></i>
                    <span>اتصال</span>
                    <small>${link.replace('tel:', '')}</small>
                `;
                callBtn.onclick = () => window.open(link, '_self');
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'action-btn copy-btn-simple';
                copyBtn.innerHTML = `
                    <i class="fas fa-copy"></i>
                    <span>نسخ الرقم</span>
                `;
                copyBtn.onclick = () => {
                    const phoneNumber = link.replace('tel:', '');
                    navigator.clipboard.writeText(phoneNumber).then(() => {
                        showNotification('تم نسخ الرقم بنجاح!');
                    });
                };
                
                buttonsDiv.appendChild(callBtn);
                buttonsDiv.appendChild(copyBtn);
                qrContainer.appendChild(buttonsDiv);
                
            } else if (type === 'email') {
                // واجهة البريد الإلكتروني: زر إرسال وزر نسخ فقط
                const buttonsDiv = document.createElement('div');
                buttonsDiv.className = 'simple-buttons';
                
                const emailBtn = document.createElement('button');
                emailBtn.className = 'action-btn email-btn-simple';
                emailBtn.innerHTML = `
                    <i class="fas fa-paper-plane"></i>
                    <span>إرسال بريد</span>
                    <small>${link.replace('mailto:', '')}</small>
                `;
                emailBtn.onclick = () => window.open(link, '_self');
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'action-btn copy-btn-simple';
                copyBtn.innerHTML = `
                    <i class="fas fa-copy"></i>
                    <span>نسخ البريد</span>
                `;
                copyBtn.onclick = () => {
                    const email = link.replace('mailto:', '');
                    navigator.clipboard.writeText(email).then(() => {
                        showNotification('تم نسخ البريد الإلكتروني بنجاح!');
                    });
                };
                
                buttonsDiv.appendChild(emailBtn);
                buttonsDiv.appendChild(copyBtn);
                qrContainer.appendChild(buttonsDiv);
                
            } else {
                // واجهة وسائل التواصل: QR Code ثلاثي الأبعاد مع صورة التطبيق
                const qrWrapper = document.createElement('div');
                qrWrapper.className = 'qr-container-3d';
                
                const qrHeader = document.createElement('div');
                qrHeader.className = 'qr-header';
                qrHeader.textContent = name;
                qrWrapper.appendChild(qrHeader);
                
                const qrCodeDiv = document.createElement('div');
                qrCodeDiv.id = 'modalQRCode';
                qrWrapper.appendChild(qrCodeDiv);
                
                // إنشاء QR Code
                setTimeout(() => {
                    qrCodeDiv.innerHTML = '';
                    currentQRCode = new QRCode(qrCodeDiv, {
                        text: link,
                        width: 200,
                        height: 200,
                        colorDark: "#000000",
                        colorLight: "#ffffff",
                        correctLevel: QRCode.CorrectLevel.H
                    });
                    
                    // إضافة أيقونة التطبيق فوق QR Code
                    const appIcon = document.createElement('div');
                    appIcon.style.position = 'absolute';
                    appIcon.style.top = '50%';
                    appIcon.style.left = '50%';
                    appIcon.style.transform = 'translate(-50%, -50%)';
                    appIcon.style.width = '50px';
                    appIcon.style.height = '50px';
                    appIcon.style.background = 'rgba(255,255,255,0.9)';
                    appIcon.style.borderRadius = '10px';
                    appIcon.style.display = 'flex';
                    appIcon.style.alignItems = 'center';
                    appIcon.style.justifyContent = 'center';
                    appIcon.style.fontSize = '25px';
                    appIcon.style.zIndex = '10';
                    appIcon.style.boxShadow = '0 5px 15px rgba(0,0,0,0.3)';
                    
                    const iconElement = document.createElement('i');
                    iconElement.className = iconClass;
                    appIcon.appendChild(iconElement);
                    
                    qrCodeDiv.appendChild(appIcon);
                }, 100);
                
                qrContainer.appendChild(qrWrapper);
                
                // أزرار الإجراءات
                const buttonsDiv = document.createElement('div');
                buttonsDiv.className = 'simple-buttons';
                buttonsDiv.style.marginTop = '30px';
                
                const downloadBtn = document.createElement('button');
                downloadBtn.className = 'action-btn call-btn';
                downloadBtn.innerHTML = `
                    <i class="fas fa-download"></i>
                    <span>تحميل QR</span>
                `;
                downloadBtn.onclick = () => {
                    if (currentQRCode) {
                        setTimeout(() => {
                            const canvas = qrCodeDiv.querySelector('canvas');
                            if (canvas) {
                                const linkElement = document.createElement('a');
                                linkElement.download = `QR-${name}.png`;
                                linkElement.href = canvas.toDataURL();
                                linkElement.click();
                                showNotification('تم تحميل QR Code بنجاح!');
                            }
                        }, 500);
                    }
                };
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'action-btn copy-btn-simple';
                copyBtn.innerHTML = `
                    <i class="fas fa-copy"></i>
                    <span>نسخ الرابط</span>
                `;
                copyBtn.onclick = () => {
                    navigator.clipboard.writeText(link).then(() => {
                        showNotification('تم نسخ الرابط بنجاح!');
                    });
                };
                
                const openBtn = document.createElement('button');
                openBtn.className = 'action-btn email-btn-simple';
                openBtn.innerHTML = `
                    <i class="fas fa-external-link-alt"></i>
                    <span>فتح التطبيق</span>
                `;
                openBtn.onclick = () => window.open(link, '_blank');
                
                buttonsDiv.appendChild(downloadBtn);
                buttonsDiv.appendChild(copyBtn);
                buttonsDiv.appendChild(openBtn);
                qrContainer.appendChild(buttonsDiv);
            }
        }
        
        // زر إغلاق النافذة
        closeShareBtn.addEventListener('click', () => {
            const shareContent = document.querySelector('.share-content');
            shareContent.style.animation = 'modalAppear 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275) reverse';
            
            setTimeout(() => {
                shareModal.style.display = 'none';
                document.body.style.overflow = '';
            }, 500);
        });
        
        // إغلاق النافذة عند النقر خارجها
        window.addEventListener('click', (e) => {
            if (e.target === shareModal) {
                const shareContent = document.querySelector('.share-content');
                shareContent.style.animation = 'modalAppear 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275) reverse';
                
                setTimeout(() => {
                    shareModal.style.display = 'none';
                    document.body.style.overflow = '';
                }, 500);
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
                    showNotification('تم نسخ رابط الموقع إلى الحافظة');
                });
            }
        });
        
        // وظيفة لعرض الإشعارات
        function showNotification(message) {
            const notification = document.createElement('div');
            notification.style.position = 'fixed';
            notification.style.bottom = '20px';
            notification.style.right = '20px';
            notification.style.background = 'linear-gradient(135deg, #00dbde, #fc00ff)';
            notification.style.color = 'white';
            notification.style.padding = '15px 25px';
            notification.style.borderRadius = '10px';
            notification.style.zIndex = '10000';
            notification.style.boxShadow = '0 10px 30px rgba(0,0,0,0.3)';
            notification.style.transform = 'translateY(100px)';
            notification.style.opacity = '0';
            notification.style.transition = 'all 0.3s ease';
            notification.textContent = message;
            
            document.body.appendChild(notification);
            
            setTimeout(() => {
                notification.style.transform = 'translateY(0)';
                notification.style.opacity = '1';
            }, 10);
            
            setTimeout(() => {
                notification.style.transform = 'translateY(100px)';
                notification.style.opacity = '0';
                setTimeout(() => {
                    document.body.removeChild(notification);
                }, 300);
            }, 3000);
        }
        
        // تأثيرات إضافية للصفحة
        document.addEventListener('mousemove', (e) => {
            const cards = document.querySelectorAll('.social-card');
            cards.forEach(card => {
                const rect = card.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                
                const centerX = rect.width / 2;
                const centerY = rect.height / 2;
                
                const rotateY = (x - centerX) / 25;
                const rotateX = (centerY - y) / 25;
                
                card.style.transform = `
                    perspective(1000px) 
                    rotateX(${rotateX}deg) 
                    rotateY(${rotateY}deg)
                    translateY(${Math.sin(Date.now() / 1000 + Array.from(cards).indexOf(card)) * 10}px)
                `;
            });
        });
    </script>
</body>
</html>
