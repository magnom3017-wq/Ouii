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
            --shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        
        body {
            background: linear-gradient(135deg, var(--light) 0%, #E2E8F0 100%);
            color: var(--text-light);
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        body.dark-mode {
            background: linear-gradient(135deg, var(--dark) 0%, var(--darker) 100%);
            color: var(--text-dark);
        }
        
        .container {
            width: 100%;
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            margin-bottom: 40px;
        }
        
        .logo {
            font-size: 28px;
            font-weight: 800;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
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
            transition: transform 0.3s ease;
            color: var(--primary);
            font-size: 20px;
        }
        
        .dark-mode .icon-btn {
            background: var(--card-dark);
            color: var(--secondary);
        }
        
        .icon-btn:hover {
            transform: translateY(-5px);
        }
        
        /* ✅ تصميم شبكة بطاقات 2-2-2-2-1 */
        .social-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 25px;
            margin-top: 20px;
        }
        
        /* البطاقات الأولى: 2 بطاقات */
        .social-grid .social-card:nth-child(-n+2) {
            grid-column: span 2;
        }
        
        /* البطاقات الثانية: 2 بطاقات */
        .social-grid .social-card:nth-child(n+3):nth-child(-n+4) {
            grid-column: span 2;
        }
        
        /* البطاقات الثالثة: 2 بطاقات */
        .social-grid .social-card:nth-child(n+5):nth-child(-n+6) {
            grid-column: span 2;
        }
        
        /* البطاقات الرابعة: 2 بطاقات */
        .social-grid .social-card:nth-child(n+7):nth-child(-n+8) {
            grid-column: span 2;
        }
        
        /* البطاقة الأخيرة: بطاقة واحدة واسعة */
        .social-grid .social-card:nth-child(9) {
            grid-column: 1 / -1;
            max-width: 50%;
            margin: 0 auto;
        }
        
        /* تصميم متجاوب */
        @media (max-width: 1200px) {
            .social-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .social-grid .social-card {
                grid-column: span 1 !important;
            }
            
            .social-grid .social-card:nth-child(9) {
                max-width: 100%;
                grid-column: span 2 !important;
            }
        }
        
        @media (max-width: 768px) {
            .social-grid {
                grid-template-columns: 1fr;
            }
            
            .social-grid .social-card:nth-child(9) {
                grid-column: span 1 !important;
            }
        }
        
        /* ✅ تصميم البطاقات ثلاثية الأبعاد ملونة */
        .social-card {
            background: linear-gradient(135deg, 
                rgba(255, 255, 255, 0.95) 0%,
                rgba(255, 255, 255, 0.85) 100%);
            border-radius: 25px;
            padding: 35px 30px;
            text-align: center;
            box-shadow: 
                0 20px 40px rgba(0,0,0,0.15),
                0 8px 20px rgba(0,0,0,0.08),
                inset 0 1px 0 rgba(255,255,255,0.5);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
            border: 3px solid transparent;
            position: relative;
            overflow: hidden;
            transform-style: preserve-3d;
            perspective: 1000px;
            animation: float 8s ease-in-out infinite;
            backdrop-filter: blur(10px);
            transform: translateZ(0);
        }
        
        .dark-mode .social-card {
            background: linear-gradient(135deg, 
                rgba(30, 30, 40, 0.95) 0%,
                rgba(20, 20, 30, 0.85) 100%);
            border: 3px solid rgba(255,255,255,0.1);
        }
        
        /* ✅ تأثيرات ثلاثية الأبعاد للبطاقات */
        .social-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(90deg, 
                transparent,
                rgba(255,255,255,0.8),
                transparent);
            z-index: 2;
            transform: translateY(-5px);
            transition: transform 0.5s ease;
        }
        
        .social-card:hover::before {
            transform: translateY(0);
        }
        
        .social-card:hover {
            transform: 
                translateY(-25px) 
                rotateX(8deg) 
                rotateY(8deg) 
                scale(1.05)
                translateZ(20px);
            box-shadow: 
                0 35px 70px rgba(0,0,0,0.25),
                0 0 40px rgba(139, 92, 246, 0.4),
                inset 0 2px 0 rgba(255,255,255,0.6);
        }
        
        /* ✅ حركة الطفو المختلفة لكل مجموعة */
        .social-card:nth-child(odd) {
            animation: float 8s ease-in-out infinite;
        }
        
        .social-card:nth-child(even) {
            animation: float 9s ease-in-out infinite 0.5s;
        }
        
        .social-card:nth-child(9) {
            animation: float 10s ease-in-out infinite 1s;
        }
        
        @keyframes float {
            0%, 100% { 
                transform: 
                    translateY(0) 
                    rotateX(0) 
                    rotateY(0)
                    translateZ(0); 
            }
            33% { 
                transform: 
                    translateY(-20px) 
                    rotateX(2deg) 
                    rotateY(3deg)
                    translateZ(10px); 
            }
            66% { 
                transform: 
                    translateY(10px) 
                    rotateX(-1deg) 
                    rotateY(-2deg)
                    translateZ(5px); 
            }
        }
        
        /* ✅ الأيقونات ثلاثية الأبعاد */
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
                0 15px 30px rgba(0,0,0,0.25),
                inset 0 5px 15px rgba(255,255,255,0.3),
                0 0 0 5px rgba(255,255,255,0.1);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            transform-style: preserve-3d;
            transform: translateZ(30px) rotateY(0);
            overflow: hidden;
        }
        
        .social-card:hover .social-icon {
            transform: 
                translateZ(60px) 
                scale(1.15) 
                rotateY(360deg);
            box-shadow: 
                0 25px 50px rgba(0,0,0,0.35),
                inset 0 8px 25px rgba(255,255,255,0.4),
                0 0 0 8px rgba(255,255,255,0.2);
        }
        
        .social-icon::before {
            content: '';
            position: absolute;
            top: -10px;
            left: -10px;
            right: -10px;
            bottom: -10px;
            background: linear-gradient(45deg, 
                transparent 30%,
                rgba(255,255,255,0.3) 50%,
                transparent 70%);
            transform: translateX(-100%) rotate(45deg);
            transition: transform 0.6s ease;
        }
        
        .social-card:hover .social-icon::before {
            transform: translateX(100%) rotate(45deg);
        }
        
        .social-icon i {
            text-shadow: 
                0 3px 8px rgba(0,0,0,0.4),
                0 0 20px rgba(255,255,255,0.2);
            position: relative;
            z-index: 1;
        }
        
        .social-name {
            font-weight: 800;
            font-size: 22px;
            margin-bottom: 12px;
            position: relative;
            z-index: 2;
            text-shadow: 0 3px 10px rgba(0,0,0,0.15);
            transform: translateZ(20px);
            background: linear-gradient(135deg, 
                rgba(255,255,255,0.9), 
                rgba(255,255,255,0.7));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            padding: 5px 0;
        }
        
        .dark-mode .social-name {
            background: linear-gradient(135deg, 
                rgba(255,255,255,0.95), 
                rgba(200,200,255,0.8));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .social-username {
            color: #64748B;
            font-size: 15px;
            direction: ltr;
            background: linear-gradient(135deg, 
                rgba(255,255,255,0.2), 
                rgba(255,255,255,0.1));
            padding: 10px 20px;
            border-radius: 50px;
            display: inline-block;
            margin-top: 8px;
            transform: translateZ(15px);
            border: 1px solid rgba(255,255,255,0.2);
            backdrop-filter: blur(5px);
            transition: all 0.3s ease;
        }
        
        .social-card:hover .social-username {
            transform: translateZ(25px) scale(1.05);
            background: linear-gradient(135deg, 
                rgba(255,255,255,0.3), 
                rgba(255,255,255,0.2));
            color: var(--primary);
        }
        
        .dark-mode .social-username {
            color: #94A3B8;
            background: linear-gradient(135deg, 
                rgba(255,255,255,0.1), 
                rgba(255,255,255,0.05));
        }
        
        /* ✅ ألوان وسائل التواصل ثلاثية الأبعاد */
        .facebook { 
            background: linear-gradient(135deg, 
                #1877F2 0%, 
                #0D5FBF 50%,
                #1877F2 100%); 
        }
        
        .instagram { 
            background: linear-gradient(135deg, 
                #E4405F 0%, 
                #C13584 30%, 
                #833AB4 60%,
                #5851DB 90%); 
        }
        
        .telegram { 
            background: linear-gradient(135deg, 
                #0088CC 0%, 
                #006699 50%,
                #0088CC 100%); 
        }
        
        .snapchat { 
            background: linear-gradient(135deg, 
                #FFFC00 0%, 
                #FFD700 50%,
                #FFFC00 100%); 
        }
        
        .tiktok { 
            background: linear-gradient(135deg, 
                #000000 0%, 
                #25F4EE 50%,
                #FE2C55 100%); 
        }
        
        .youtube { 
            background: linear-gradient(135deg, 
                #FF0000 0%, 
                #CC0000 50%,
                #FF0000 100%); 
        }
        
        .twitter { 
            background: linear-gradient(135deg, 
                #1DA1F2 0%, 
                #0D8BD9 50%,
                #1DA1F2 100%); 
        }
        
        .email { 
            background: linear-gradient(135deg, 
                #EA4335 0%, 
                #D14836 50%,
                #EA4335 100%); 
        }
        
        .phone { 
            background: linear-gradient(135deg, 
                #34A853 0%, 
                #2E8B57 50%,
                #34A853 100%); 
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
        
        <!-- ✅ البطاقات مرتبة 2-2-2-2-1 -->
        <div class="social-grid">
            <!-- المجموعة الأولى: بطاقتين -->
            <div class="social-card" data-name="فيسبوك" data-link="https://www.facebook.com/share/1BgY11DMQM/" data-icon="facebook" data-type="social">
                <div class="social-icon facebook"><i class="fab fa-facebook-f"></i></div>
                <div class="social-name">فيسبوك</div>
                <div class="social-username">Kamola</div>
            </div>
            
            <div class="social-card" data-name="إنستغرام" data-link="https://www.instagram.com/kamola_463" data-icon="instagram" data-type="social">
                <div class="social-icon instagram"><i class="fab fa-instagram"></i></div>
                <div class="social-name">إنستغرام</div>
                <div class="social-username">@kamola_463</div>
            </div>
            
            <!-- المجموعة الثانية: بطاقتين -->
            <div class="social-card" data-name="تيليجرام" data-link="https://t.me/ou_kamel" data-icon="telegram" data-type="social">
                <div class="social-icon telegram"><i class="fab fa-telegram-plane"></i></div>
                <div class="social-name">تيليجرام</div>
                <div class="social-username">@ou_kamel</div>
            </div>
            
            <div class="social-card" data-name="سناب شات" data-link="https://www.snapchat.com/add/kamola252903" data-icon="snapchat" data-type="social">
                <div class="social-icon snapchat"><i class="fab fa-snapchat-ghost"></i></div>
                <div class="social-name">سناب شات</div>
                <div class="social-username">kamola252903</div>
            </div>
            
            <!-- المجموعة الثالثة: بطاقتين -->
            <div class="social-card" data-name="تيك توك" data-link="https://www.tiktok.com/@kamola.3017" data-icon="tiktok" data-type="social">
                <div class="social-icon tiktok"><i class="fab fa-tiktok"></i></div>
                <div class="social-name">تيك توك</div>
                <div class="social-username">@kamola.3017</div>
            </div>
            
            <div class="social-card" data-name="يوتيوب" data-link="https://www.youtube.com/@kamola3017" data-icon="youtube" data-type="social">
                <div class="social-icon youtube"><i class="fab fa-youtube"></i></div>
                <div class="social-name">يوتيوب</div>
                <div class="social-username">@kamola3017</div>
            </div>
            
            <!-- المجموعة الرابعة: بطاقتين -->
            <div class="social-card" data-name="تويتر" data-link="https://x.com/3017Kamola44307?t=107y45_c29JA1E-ClTzg_A&s=09" data-icon="twitter" data-type="social">
                <div class="social-icon twitter"><i class="fab fa-twitter"></i></div>
                <div class="social-name">تويتر</div>
                <div class="social-username">@3017Kamola44307</div>
            </div>
            
            <div class="social-card" data-name="البريد الإلكتروني" data-link="mailto:magnom3017@gmail.com" data-icon="email" data-type="email">
                <div class="social-icon email"><i class="fas fa-envelope"></i></div>
                <div class="social-name">البريد الإلكتروني</div>
                <div class="social-username">magnom3017@gmail.com</div>
            </div>
            
            <!-- المجموعة الخامسة: بطاقة واحدة واسعة -->
            <div class="social-card" data-name="رقم الهاتف" data-link="tel:+962776274508" data-icon="phone" data-type="phone">
                <div class="social-icon phone"><i class="fas fa-phone"></i></div>
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
            <div id="modalContent"></div>
        </div>
    </div>
    
    <div class="notification" id="notification"></div>
    
    <style>
        /* النافذة المنبثقة */
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
            backdrop-filter: blur(10px);
        }
        
        .share-content {
            background: linear-gradient(135deg, 
                rgba(20, 20, 40, 0.95), 
                rgba(30, 30, 60, 0.95));
            border-radius: 30px;
            padding: 50px;
            text-align: center;
            max-width: 500px;
            width: 90%;
            box-shadow: 
                0 35px 70px rgba(0,0,0,0.6),
                0 0 0 2px rgba(139, 92, 246, 0.4),
                inset 0 1px 0 rgba(255,255,255,0.1);
            border: 3px solid var(--primary);
            position: relative;
            animation: modalAppear 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            transform-style: preserve-3d;
            perspective: 1000px;
        }
        
        @keyframes modalAppear {
            0% { 
                transform: 
                    scale(0.8) 
                    translateY(100px) 
                    rotateX(-30deg); 
                opacity: 0; 
            }
            100% { 
                transform: 
                    scale(1) 
                    translateY(0) 
                    rotateX(0); 
                opacity: 1; 
            }
        }
        
        .share-title {
            color: white;
            font-size: 32px;
            margin-bottom: 30px;
            font-weight: 800;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 5px 15px rgba(0,0,0,0.3);
            transform: translateZ(30px);
        }
        
        .qr-container {
            background: white;
            padding: 25px;
            border-radius: 20px;
            margin: 30px auto;
            display: inline-block;
            box-shadow: 
                0 20px 40px rgba(0,0,0,0.3),
                inset 0 1px 0 rgba(255,255,255,0.5);
            animation: pulse 3s infinite;
            transform-style: preserve-3d;
            transform: translateZ(20px);
            border: 3px solid rgba(139, 92, 246, 0.3);
        }
        
        @keyframes pulse {
            0%, 100% { 
                transform: 
                    translateZ(20px) 
                    scale(1); 
                box-shadow: 
                    0 20px 40px rgba(0,0,0,0.3);
            }
            50% { 
                transform: 
                    translateZ(30px) 
                    scale(1.05); 
                box-shadow: 
                    0 25px 50px rgba(139, 92, 246, 0.4);
            }
        }
        
        #modalQRCode {
            width: 220px;
            height: 220px;
            position: relative;
        }
        
        .action-buttons {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-top: 30px;
            transform: translateZ(20px);
        }
        
        .action-buttons.three-columns {
            grid-template-columns: repeat(3, 1fr);
        }
        
        .action-btn {
            padding: 18px;
            border: none;
            border-radius: 15px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            font-size: 17px;
            color: white;
            box-shadow: 0 8px 25px rgba(0,0,0,0.25);
            transform: translateZ(0);
            position: relative;
            overflow: hidden;
            letter-spacing: 0.5px;
        }
        
        .action-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255,255,255,0.2), 
                transparent);
            transition: left 0.6s ease;
        }
        
        .action-btn:hover::before {
            left: 100%;
        }
        
        .action-btn:hover {
            transform: translateY(-8px) translateZ(10px) scale(1.05);
            box-shadow: 0 15px 35px rgba(0,0,0,0.4);
        }
        
        .action-btn i {
            font-size: 20px;
            text-shadow: 0 2px 5px rgba(0,0,0,0.3);
        }
        
        .download-btn { 
            background: linear-gradient(135deg, var(--primary), #7c3aed); 
        }
        .copy-btn { 
            background: linear-gradient(135deg, var(--accent), #d12e5a); 
        }
        .call-btn { 
            background: linear-gradient(135deg, #34A853, #2E8B57); 
        }
        .email-btn { 
            background: linear-gradient(135deg, #EA4335, #D14836); 
        }
        .open-btn { 
            background: linear-gradient(135deg, var(--secondary), #05b887); 
        }
        
        .close-share {
            position: absolute;
            top: 25px;
            left: 25px;
            background: linear-gradient(135deg, var(--accent), #d12e5a);
            border: none;
            color: white;
            font-size: 22px;
            cursor: pointer;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 8px 25px rgba(0,0,0,0.4);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            z-index: 10;
            transform: translateZ(0);
        }
        
        .close-share:hover {
            transform: rotate(180deg) scale(1.1);
            box-shadow: 0 12px 30px rgba(209, 46, 90, 0.6);
        }
        
        /* إشعارات ثلاثية الأبعاد */
        .notification {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 20px 30px;
            border-radius: 15px;
            box-shadow: 
                0 15px 40px rgba(0,0,0,0.4),
                inset 0 1px 0 rgba(255,255,255,0.3);
            z-index: 10000;
            transform: 
                translateY(150px) 
                translateZ(0);
            transition: transform 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255,255,255,0.2);
            max-width: 350px;
            text-align: center;
            font-weight: 600;
            font-size: 16px;
        }
        
        .notification.show {
            transform: 
                translateY(0) 
                translateZ(20px);
        }
        
        .notification::before {
            content: '✓';
            position: absolute;
            left: 20px;
            top: 50%;
            transform: translateY(-50%);
            background: rgba(255,255,255,0.2);
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }
    </style>
    
    <script>
        const darkModeToggle = document.getElementById('darkModeToggle');
        const body = document.body;
        
        darkModeToggle.addEventListener('click', () => {
            body.classList.toggle('dark-mode');
            const icon = darkModeToggle.querySelector('i');
            if (body.classList.contains('dark-mode')) {
                icon.classList.replace('fa-moon', 'fa-sun');
                icon.style.transform = 'rotate(360deg)';
                setTimeout(() => {
                    icon.style.transform = 'rotate(0deg)';
                }, 400);
            } else {
                icon.classList.replace('fa-sun', 'fa-moon');
                icon.style.transform = 'rotate(360deg)';
                setTimeout(() => {
                    icon.style.transform = 'rotate(0deg)';
                }, 400);
            }
        });
        
        const shareModal = document.getElementById('shareModal');
        const modalAppName = document.getElementById('modalAppName');
        const modalContent = document.getElementById('modalContent');
        const closeShareBtn = document.getElementById('closeShareBtn');
        const notification = document.getElementById('notification');
        
        let currentQRCode = null;
        
        document.querySelectorAll('.social-card').forEach(card => {
            card.addEventListener('click', () => {
                const name = card.getAttribute('data-name');
                const link = card.getAttribute('data-link');
                const type = card.getAttribute('data-type');
                const iconClass = card.querySelector('.social-icon i').className;
                
                modalAppName.textContent = name;
                setupModalContent(type, link, name, iconClass);
                shareModal.style.display = 'flex';
                
                // تأثير اهتزاز للبطاقة
                card.style.animation = 'none';
                setTimeout(() => {
                    card.style.animation = '';
                }, 10);
            });
        });
        
        function setupModalContent(type, link, name, iconClass) {
            modalContent.innerHTML = '';
            
            if (type === 'phone') {
                const phoneNumber = link.replace('tel:', '');
                const phoneInfo = document.createElement('div');
                phoneInfo.className = 'social-username';
                phoneInfo.style.color = 'white';
                phoneInfo.style.margin = '25px 0 35px';
                phoneInfo.style.fontSize = '24px';
                phoneInfo.style.fontWeight = 'bold';
                phoneInfo.style.background = 'linear-gradient(135deg, rgba(52, 168, 83, 0.2), rgba(46, 139, 87, 0.2))';
                phoneInfo.style.padding = '15px 30px';
                phoneInfo.style.borderRadius = '15px';
                phoneInfo.style.border = '2px solid rgba(52, 168, 83, 0.3)';
                phoneInfo.textContent = phoneNumber;
                modalContent.appendChild(phoneInfo);
                
                const buttonsDiv = document.createElement('div');
                buttonsDiv.className = 'action-buttons';
                
                const callBtn = document.createElement('button');
                callBtn.className = 'action-btn call-btn';
                callBtn.innerHTML = '<i class="fas fa-phone-alt"></i> اتصال';
                callBtn.onclick = () => {
                    window.location.href = link;
                    shareModal.style.display = 'none';
                };
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'action-btn copy-btn';
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> نسخ الرقم';
                copyBtn.onclick = () => {
                    navigator.clipboard.writeText(phoneNumber).then(() => {
                        showNotification('تم نسخ الرقم بنجاح ✓');
                        shareModal.style.display = 'none';
                    });
                };
                
                buttonsDiv.appendChild(callBtn);
                buttonsDiv.appendChild(copyBtn);
                modalContent.appendChild(buttonsDiv);
                
            } else if (type === 'email') {
                const email = link.replace('mailto:', '');
                const emailInfo = document.createElement('div');
                emailInfo.className = 'social-username';
                emailInfo.style.color = 'white';
                emailInfo.style.margin = '25px 0 35px';
                emailInfo.style.fontSize = '22px';
                emailInfo.style.fontWeight = 'bold';
                emailInfo.style.background = 'linear-gradient(135deg, rgba(234, 67, 53, 0.2), rgba(209, 72, 54, 0.2))';
                emailInfo.style.padding = '15px 30px';
                emailInfo.style.borderRadius = '15px';
                emailInfo.style.border = '2px solid rgba(234, 67, 53, 0.3)';
                emailInfo.style.wordBreak = 'break-all';
                emailInfo.textContent = email;
                modalContent.appendChild(emailInfo);
                
                const buttonsDiv = document.createElement('div');
                buttonsDiv.className = 'action-buttons';
                
                const emailBtn = document.createElement('button');
                emailBtn.className = 'action-btn email-btn';
                emailBtn.innerHTML = '<i class="fas fa-paper-plane"></i> إرسال بريد';
                emailBtn.onclick = () => {
                    window.location.href = link;
                    shareModal.style.display = 'none';
                };
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'action-btn copy-btn';
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> نسخ البريد';
                copyBtn.onclick = () => {
                    navigator.clipboard.writeText(email).then(() => {
                        showNotification('تم نسخ البريد بنجاح ✓');
                        shareModal.style.display = 'none';
                    });
                };
                
                buttonsDiv.appendChild(emailBtn);
                buttonsDiv.appendChild(copyBtn);
                modalContent.appendChild(buttonsDiv);
                
            } else {
                const qrContainer = document.createElement('div');
                qrContainer.className = 'qr-container';
                const qrCodeDiv = document.createElement('div');
                qrCodeDiv.id = 'modalQRCode';
                qrContainer.appendChild(qrCodeDiv);
                modalContent.appendChild(qrContainer);
                
                setTimeout(() => {
                    qrCodeDiv.innerHTML = '';
                    currentQRCode = new QRCode(qrCodeDiv, {
                        text: link,
                        width: 220,
                        height: 220,
                        colorDark: "#000000",
                        colorLight: "#ffffff",
                        correctLevel: QRCode.CorrectLevel.H
                    });
                    
                    setTimeout(() => {
                        const canvas = qrCodeDiv.querySelector('canvas');
                        if (canvas) {
                            const appIcon = document.createElement('div');
                            appIcon.style.position = 'absolute';
                            appIcon.style.top = '50%';
                            appIcon.style.left = '50%';
                            appIcon.style.transform = 'translate(-50%, -50%)';
                            appIcon.style.width = '50px';
                            appIcon.style.height = '50px';
                            appIcon.style.background = 'white';
                            appIcon.style.borderRadius = '12px';
                            appIcon.style.display = 'flex';
                            appIcon.style.alignItems = 'center';
                            appIcon.style.justifyContent = 'center';
                            appIcon.style.fontSize = '24px';
                            appIcon.style.boxShadow = '0 5px 15px rgba(0,0,0,0.2)';
                            appIcon.style.border = '3px solid white';
                            appIcon.style.zIndex = '10';
                            
                            const iconElement = document.createElement('i');
                            iconElement.className = iconClass;
                            if (iconClass.includes('facebook')) iconElement.style.color = '#1877F2';
                            else if (iconClass.includes('instagram')) iconElement.style.color = '#E4405F';
                            else if (iconClass.includes('telegram')) iconElement.style.color = '#0088CC';
                            else if (iconClass.includes('snapchat')) iconElement.style.color = '#FFFC00';
                            else if (iconClass.includes('tiktok')) iconElement.style.color = '#000000';
                            else if (iconClass.includes('youtube')) iconElement.style.color = '#FF0000';
                            else if (iconClass.includes('twitter')) iconElement.style.color = '#1DA1F2';
                            
                            appIcon.appendChild(iconElement);
                            qrCodeDiv.appendChild(appIcon);
                        }
                    }, 300);
                }, 100);
                
                const buttonsDiv = document.createElement('div');
                buttonsDiv.className = 'action-buttons three-columns';
                
                const downloadBtn = document.createElement('button');
                downloadBtn.className = 'action-btn download-btn';
                downloadBtn.innerHTML = '<i class="fas fa-download"></i> تحميل';
                downloadBtn.onclick = () => {
                    setTimeout(() => {
                        const canvas = qrCodeDiv.querySelector('canvas');
                        if (canvas) {
                            const linkEl = document.createElement('a');
                            linkEl.download = `qrcode-${name}.png`;
                            linkEl.href = canvas.toDataURL('image/png', 1.0);
                            document.body.appendChild(linkEl);
                            linkEl.click();
                            document.body.removeChild(linkEl);
                            showNotification('تم تحميل QR Code بنجاح ✓');
                        }
                    }, 500);
                };
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'action-btn copy-btn';
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> نسخ';
                copyBtn.onclick = () => {
                    navigator.clipboard.writeText(link).then(() => {
                        showNotification('تم نسخ الرابط بنجاح ✓');
                    });
                };
                
                const openBtn = document.createElement('button');
                openBtn.className = 'action-btn open-btn';
                openBtn.innerHTML = '<i class="fas fa-external-link-alt"></i> فتح';
                openBtn.onclick = () => {
                    window.open(link, '_blank');
                    shareModal.style.display = 'none';
                };
                
                buttonsDiv.appendChild(downloadBtn);
                buttonsDiv.appendChild(copyBtn);
                buttonsDiv.appendChild(openBtn);
                modalContent.appendChild(buttonsDiv);
            }
        }
        
        closeShareBtn.addEventListener('click', () => {
            shareModal.style.display = 'none';
        });
        
        window.addEventListener('click', (e) => {
            if (e.target === shareModal) {
                shareModal.style.display = 'none';
            }
        });
        
        document.getElementById('shareBtn').addEventListener('click', () => {
            if (navigator.share) {
                navigator.share({
                    title: 'Øu••ᵏᵃᵐᵃˡ࿐ - وسائل التواصل',
                    text: 'تابعني على وسائل التواصل الاجتماعي',
                    url: window.location.href
                });
            } else {
                navigator.clipboard.writeText(window.location.href).then(() => {
                    showNotification('تم نسخ رابط الموقع بنجاح ✓');
                });
            }
        });
        
        function showNotification(message) {
            notification.textContent = message;
            notification.classList.add('show');
            
            // تأثير اهتزاز خفيف
            notification.style.animation = 'none';
            setTimeout(() => {
                notification.style.animation = 'pulse 0.5s';
            }, 10);
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }
        
        // إضافة تأثيرات إضافية عند التحميل
        window.addEventListener('load', () => {
            document.querySelectorAll('.social-card').forEach((card, index) => {
                card.style.animationDelay = `${index * 0.1}s`;
            });
            
            // تأثير ظهور تدريجي للبطاقات
            setTimeout(() => {
                document.querySelectorAll('.social-card').forEach(card => {
                    card.style.opacity = '1';
                    card.style.transform = 'translateY(0)';
                });
            }, 100);
        });
    </script>
</body>
</html>
