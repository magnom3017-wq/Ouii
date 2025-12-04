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
            max-width: 1200px;
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
        
        /* شبكة البطاقات - صفين */
        .social-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 25px;
            margin-top: 20px;
        }
        
        @media (max-width: 768px) {
            .social-grid {
                grid-template-columns: 1fr;
            }
        }
        
        /* تصميم البطاقات ثلاثية الأبعاد */
        .social-card {
            background: var(--card-light);
            border-radius: 20px;
            padding: 30px 25px;
            text-align: center;
            box-shadow: 
                0 15px 35px rgba(0,0,0,0.1),
                0 5px 15px rgba(0,0,0,0.05);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
            border: 2px solid transparent;
            position: relative;
            overflow: hidden;
            transform-style: preserve-3d;
            perspective: 1000px;
            animation: float 6s ease-in-out infinite;
        }
        
        /* حركة الطفو المختلفة لكل بطاقة */
        .social-card:nth-child(odd) {
            animation-delay: 0s;
        }
        
        .social-card:nth-child(even) {
            animation-delay: 0.5s;
        }
        
        @keyframes float {
            0%, 100% { 
                transform: translateY(0) rotateX(0) rotateY(0); 
            }
            50% { 
                transform: translateY(-15px) rotateX(5deg) rotateY(5deg); 
            }
        }
        
        .dark-mode .social-card {
            background: var(--card-dark);
        }
        
        .social-card:hover {
            transform: translateY(-20px) rotateX(10deg) rotateY(10deg) scale(1.05);
            box-shadow: 
                0 25px 50px rgba(0,0,0,0.2),
                0 0 30px rgba(139, 92, 246, 0.3);
            border-color: var(--primary);
        }
        
        /* الأيقونات ثلاثية الأبعاد */
        .social-icon {
            width: 80px;
            height: 80px;
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 35px;
            color: white;
            box-shadow: 
                0 10px 20px rgba(0,0,0,0.2),
                inset 0 3px 10px rgba(255,255,255,0.3);
            transition: all 0.4s ease;
            position: relative;
            transform-style: preserve-3d;
            transform: translateZ(20px);
        }
        
        .social-card:hover .social-icon {
            transform: translateZ(40px) scale(1.2) rotateY(180deg);
            box-shadow: 
                0 15px 30px rgba(0,0,0,0.3),
                inset 0 5px 15px rgba(255,255,255,0.4);
        }
        
        .social-icon i {
            text-shadow: 0 2px 5px rgba(0,0,0,0.3);
        }
        
        .social-name {
            font-weight: 700;
            font-size: 20px;
            margin-bottom: 10px;
            position: relative;
            z-index: 2;
            text-shadow: 0 2px 5px rgba(0,0,0,0.1);
            transform: translateZ(10px);
        }
        
        .social-username {
            color: #64748B;
            font-size: 14px;
            direction: ltr;
            background: rgba(0,0,0,0.05);
            padding: 6px 15px;
            border-radius: 20px;
            display: inline-block;
            margin-top: 5px;
            transform: translateZ(5px);
        }
        
        .dark-mode .social-username {
            color: #94A3B8;
            background: rgba(255,255,255,0.1);
        }
        
        /* ألوان وسائل التواصل */
        .facebook { background: linear-gradient(135deg, #1877F2, #0D5FBF); }
        .instagram { background: linear-gradient(135deg, #E4405F, #C13584); }
        .telegram { background: linear-gradient(135deg, #0088CC, #006699); }
        .snapchat { background: linear-gradient(135deg, #FFFC00, #FFD700); }
        .tiktok { background: linear-gradient(135deg, #000000, #25F4EE); }
        .youtube { background: linear-gradient(135deg, #FF0000, #CC0000); }
        .twitter { background: linear-gradient(135deg, #1DA1F2, #0D8BD9); }
        .email { background: linear-gradient(135deg, #EA4335, #D14836); }
        .phone { background: linear-gradient(135deg, #34A853, #2E8B57); }
        
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
        }
        
        .share-content {
            background: linear-gradient(135deg, 
                rgba(20, 20, 40, 0.95), 
                rgba(30, 30, 60, 0.95));
            border-radius: 25px;
            padding: 40px;
            text-align: center;
            max-width: 450px;
            width: 90%;
            box-shadow: 
                0 25px 50px rgba(0,0,0,0.5),
                0 0 0 1px rgba(139, 92, 246, 0.3);
            border: 2px solid var(--primary);
            position: relative;
            animation: modalAppear 0.5s ease-out;
        }
        
        @keyframes modalAppear {
            0% { transform: scale(0.8) translateY(50px); opacity: 0; }
            100% { transform: scale(1) translateY(0); opacity: 1; }
        }
        
        .share-title {
            color: white;
            font-size: 28px;
            margin-bottom: 25px;
            font-weight: 700;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .qr-container {
            background: white;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
            display: inline-block;
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.03); }
        }
        
        #modalQRCode {
            width: 200px;
            height: 200px;
        }
        
        .action-buttons {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin-top: 25px;
        }
        
        .action-btn {
            padding: 15px;
            border: none;
            border-radius: 12px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            font-size: 16px;
            color: white;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .action-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.3);
        }
        
        .download-btn { background: linear-gradient(135deg, var(--primary), #7c3aed); }
        .copy-btn { background: linear-gradient(135deg, var(--accent), #d12e5a); }
        .call-btn { background: linear-gradient(135deg, #34A853, #2E8B57); }
        .email-btn { background: linear-gradient(135deg, #EA4335, #D14836); }
        .open-btn { background: linear-gradient(135deg, var(--secondary), #05b887); }
        
        .close-share {
            position: absolute;
            top: 20px;
            left: 20px;
            background: linear-gradient(135deg, var(--accent), #d12e5a);
            border: none;
            color: white;
            font-size: 20px;
            cursor: pointer;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            transition: transform 0.3s ease;
        }
        
        .close-share:hover {
            transform: rotate(90deg);
        }
        
        /* إشعارات */
        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 15px 25px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            z-index: 10000;
            transform: translateY(100px);
            transition: transform 0.3s ease;
        }
        
        .notification.show {
            transform: translateY(0);
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
                <div class="social-icon email"><i class="fas fa-envelope"></i></div>
                <div class="social-name">البريد الإلكتروني</div>
                <div class="social-username">magnom3017@gmail.com</div>
            </div>
            
            <!-- رقم الهاتف -->
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
            <div id="modalContent">
                <!-- المحتوى سيتم إضافته ديناميكياً -->
            </div>
        </div>
    </div>
    
    <!-- إشعارات -->
    <div class="notification" id="notification"></div>
    
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
        const modalContent = document.getElementById('modalContent');
        const closeShareBtn = document.getElementById('closeShareBtn');
        const notification = document.getElementById('notification');
        
        let currentQRCode = null;
        
        // فتح النافذة عند النقر على البطاقات
        document.querySelectorAll('.social-card').forEach(card => {
            card.addEventListener('click', () => {
                const name = card.getAttribute('data-name');
                const link = card.getAttribute('data-link');
                const type = card.getAttribute('data-type');
                const iconClass = card.querySelector('.social-icon i').className;
                
                modalAppName.textContent = name;
                
                // إعداد المحتوى حسب النوع
                setupModalContent(type, link, name, iconClass);
                
                shareModal.style.display = 'flex';
            });
        });
        
        function setupModalContent(type, link, name, iconClass) {
            modalContent.innerHTML = '';
            
            if (type === 'phone') {
                // واجهة الهاتف
                const phoneNumber = link.replace('tel:', '');
                
                const phoneInfo = document.createElement('div');
                phoneInfo.className = 'social-username';
                phoneInfo.style.color = 'white';
                phoneInfo.style.margin = '20px 0';
                phoneInfo.style.fontSize = '20px';
                phoneInfo.style.fontWeight = 'bold';
                phoneInfo.textContent = phoneNumber;
                modalContent.appendChild(phoneInfo);
                
                const buttonsDiv = document.createElement('div');
                buttonsDiv.className = 'action-buttons';
                
                const callBtn = document.createElement('button');
                callBtn.className = 'action-btn call-btn';
                callBtn.innerHTML = '<i class="fas fa-phone"></i> اتصال';
                callBtn.onclick = () => window.location.href = link;
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'action-btn copy-btn';
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> نسخ الرقم';
                copyBtn.onclick = () => {
                    navigator.clipboard.writeText(phoneNumber).then(() => {
                        showNotification('تم نسخ الرقم بنجاح');
                    });
                };
                
                buttonsDiv.appendChild(callBtn);
                buttonsDiv.appendChild(copyBtn);
                modalContent.appendChild(buttonsDiv);
                
            } else if (type === 'email') {
                // واجهة البريد الإلكتروني
                const email = link.replace('mailto:', '');
                
                const emailInfo = document.createElement('div');
                emailInfo.className = 'social-username';
                emailInfo.style.color = 'white';
                emailInfo.style.margin = '20px 0';
                emailInfo.style.fontSize = '20px';
                emailInfo.style.fontWeight = 'bold';
                emailInfo.textContent = email;
                modalContent.appendChild(emailInfo);
                
                const buttonsDiv = document.createElement('div');
                buttonsDiv.className = 'action-buttons';
                
                const emailBtn = document.createElement('button');
                emailBtn.className = 'action-btn email-btn';
                emailBtn.innerHTML = '<i class="fas fa-paper-plane"></i> إرسال بريد';
                emailBtn.onclick = () => window.location.href = link;
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'action-btn copy-btn';
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> نسخ البريد';
                copyBtn.onclick = () => {
                    navigator.clipboard.writeText(email).then(() => {
                        showNotification('تم نسخ البريد بنجاح');
                    });
                };
                
                buttonsDiv.appendChild(emailBtn);
                buttonsDiv.appendChild(copyBtn);
                modalContent.appendChild(buttonsDiv);
                
            } else {
                // واجهة وسائل التواصل
                const qrContainer = document.createElement('div');
                qrContainer.className = 'qr-container';
                
                const qrCodeDiv = document.createElement('div');
                qrCodeDiv.id = 'modalQRCode';
                qrContainer.appendChild(qrCodeDiv);
                modalContent.appendChild(qrContainer);
                
                // إنشاء QR Code مع أيقونة التطبيق
                setTimeout(() => {
                    qrCodeDiv.innerHTML = '';
                    currentQRCode = new QRCode(qrCodeDiv, {
                        text: link,
                        width: 200,
                        height: 200,
                        colorDark: "#000000",
                        colorLight: "#ffffff"
                    });
                    
                    // إضافة أيقونة التطبيق في الوسط
                    const appIcon = document.createElement('div');
                    appIcon.style.position = 'absolute';
                    appIcon.style.top = '50%';
                    appIcon.style.left = '50%';
                    appIcon.style.transform = 'translate(-50%, -50%)';
                    appIcon.style.width = '40px';
                    appIcon.style.height = '40px';
                    appIcon.style.background = 'white';
                    appIcon.style.borderRadius = '8px';
                    appIcon.style.display = 'flex';
                    appIcon.style.alignItems = 'center';
                    appIcon.style.justifyContent = 'center';
                    appIcon.style.fontSize = '20px';
                    
                    const iconElement = document.createElement('i');
                    iconElement.className = iconClass;
                    
                    // تحديد لون الأيقونة حسب النوع
                    if (iconClass.includes('facebook')) iconElement.style.color = '#1877F2';
                    else if (iconClass.includes('instagram')) iconElement.style.color = '#E4405F';
                    else if (iconClass.includes('telegram')) iconElement.style.color = '#0088CC';
                    else if (iconClass.includes('snapchat')) iconElement.style.color = '#FFFC00';
                    else if (iconClass.includes('tiktok')) iconElement.style.color = '#000000';
                    else if (iconClass.includes('youtube')) iconElement.style.color = '#FF0000';
                    else if (iconClass.includes('twitter')) iconElement.style.color = '#1DA1F2';
                    
                    appIcon.appendChild(iconElement);
                    qrCodeDiv.appendChild(appIcon);
                }, 100);
                
                const buttonsDiv = document.createElement('div');
                buttonsDiv.className = 'action-buttons';
                
                const downloadBtn = document.createElement('button');
                downloadBtn.className = 'action-btn download-btn';
                downloadBtn.innerHTML = '<i class="fas fa-download"></i> تحميل';
                downloadBtn.onclick = () => {
                    setTimeout(() => {
                        const canvas = qrCodeDiv.querySelector('canvas');
                        if (canvas) {
                            const linkEl = document.createElement('a');
                            linkEl.download = `qrcode-${name}.png`;
                            linkEl.href = canvas.toDataURL();
                            linkEl.click();
                            showNotification('تم تحميل QR Code');
                        }
                    }, 500);
                };
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'action-btn copy-btn';
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> نسخ الرابط';
                copyBtn.onclick = () => {
                    navigator.clipboard.writeText(link).then(() => {
                        showNotification('تم نسخ الرابط بنجاح');
                    });
                };
                
                const openBtn = document.createElement('button');
                openBtn.className = 'action-btn open-btn';
                openBtn.innerHTML = '<i class="fas fa-external-link-alt"></i> فتح التطبيق';
                openBtn.onclick = () => window.open(link, '_blank');
                
                buttonsDiv.appendChild(downloadBtn);
                buttonsDiv.appendChild(copyBtn);
                buttonsDiv.appendChild(openBtn);
                
                modalContent.appendChild(buttonsDiv);
            }
        }
        
        // إغلاق النافذة
        closeShareBtn.addEventListener('click', () => {
            shareModal.style.display = 'none';
        });
        
        window.addEventListener('click', (e) => {
            if (e.target === shareModal) {
                shareModal.style.display = 'none';
            }
        });
        
        // زر المشاركة في الهيدر
        document.getElementById('shareBtn').addEventListener('click', () => {
            if (navigator.share) {
                navigator.share({
                    title: 'Øu••ᵏᵃᵐᵃˡ࿐ - وسائل التواصل',
                    text: 'تابعني على وسائل التواصل',
                    url: window.location.href
                });
            } else {
                navigator.clipboard.writeText(window.location.href).then(() => {
                    showNotification('تم نسخ رابط الموقع');
                });
            }
        });
        
        // وظيفة الإشعارات
        function showNotification(message) {
            notification.textContent = message;
            notification.classList.add('show');
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }
        
        // تأثيرات ثلاثية الأبعاد للبطاقات
        document.addEventListener('mousemove', (e) => {
            const cards = document.querySelectorAll('.social-card');
            cards.forEach(card => {
                const rect = card.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                
                const centerX = rect.width / 2;
                const centerY = rect.height / 2;
                
                const rotateY = (x - centerX) / 20;
                const rotateX = (centerY - y) / 20;
                
                card.style.transform = `
                    perspective(1000px) 
                    rotateX(${rotateX}deg) 
                    rotateY(${rotateY}deg)
                    translateY(${Math.sin(Date.now() / 1000) * 5}px)
                `;
            });
        });
    </script>
</body>
</html>
