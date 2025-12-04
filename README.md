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
            transition: transform 0.2s ease;
            color: var(--primary);
            font-size: 20px;
        }
        
        .dark-mode .icon-btn {
            background: var(--card-dark);
            color: var(--secondary);
        }
        
        .icon-btn:hover {
            transform: translateY(-3px);
        }
        
        /* شبكة البطاقات - صفين */
        .social-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-top: 20px;
        }
        
        @media (max-width: 768px) {
            .social-grid {
                grid-template-columns: 1fr;
            }
        }
        
        /* تصميم البطاقات المبسط */
        .social-card {
            background: var(--card-light);
            border-radius: 15px;
            padding: 25px 20px;
            text-align: center;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            cursor: pointer;
            border: 2px solid transparent;
            position: relative;
            overflow: hidden;
        }
        
        .dark-mode .social-card {
            background: var(--card-dark);
        }
        
        .social-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
            border-color: var(--primary);
        }
        
        /* الأيقونات */
        .social-icon {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 15px;
            font-size: 30px;
            color: white;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }
        
        .social-card:hover .social-icon {
            transform: scale(1.1);
        }
        
        .social-name {
            font-weight: 600;
            font-size: 18px;
            margin-bottom: 8px;
        }
        
        .social-username {
            color: #64748B;
            font-size: 14px;
            direction: ltr;
        }
        
        .dark-mode .social-username {
            color: #94A3B8;
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
        
        /* النافذة المنبثقة المبسطة */
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
        }
        
        .share-content {
            background: var(--darker);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            max-width: 400px;
            width: 90%;
            box-shadow: 0 20px 40px rgba(0,0,0,0.5);
            border: 2px solid var(--primary);
            position: relative;
        }
        
        .share-title {
            color: white;
            font-size: 24px;
            margin-bottom: 20px;
            font-weight: 700;
        }
        
        .qr-container {
            background: white;
            padding: 15px;
            border-radius: 10px;
            margin: 20px 0;
            display: inline-block;
        }
        
        #modalQRCode {
            width: 200px;
            height: 200px;
        }
        
        .action-buttons {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin-top: 20px;
        }
        
        .action-btn {
            padding: 12px;
            border: none;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            font-size: 14px;
            color: white;
        }
        
        .download-btn { background: var(--primary); }
        .copy-btn { background: var(--accent); }
        .call-btn { background: #34A853; }
        .email-btn { background: #EA4335; }
        
        .action-btn:hover {
            transform: translateY(-2px);
        }
        
        .close-share {
            position: absolute;
            top: 15px;
            left: 15px;
            background: none;
            border: none;
            color: white;
            font-size: 20px;
            cursor: pointer;
        }
        
        /* إشعارات بسيطة */
        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: var(--primary);
            color: white;
            padding: 10px 20px;
            border-radius: 8px;
            box-shadow: var(--shadow);
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
        <div class="share-content">
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
                
                modalAppName.textContent = name;
                
                // إعداد المحتوى حسب النوع
                setupModalContent(type, link, name);
                
                shareModal.style.display = 'flex';
            });
        });
        
        function setupModalContent(type, link, name) {
            modalContent.innerHTML = '';
            
            if (type === 'phone') {
                // واجهة الهاتف
                const phoneNumber = link.replace('tel:', '');
                
                const phoneInfo = document.createElement('div');
                phoneInfo.className = 'social-username';
                phoneInfo.style.color = 'white';
                phoneInfo.style.margin = '20px 0';
                phoneInfo.style.fontSize = '18px';
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
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> نسخ';
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
                emailInfo.style.fontSize = '18px';
                emailInfo.textContent = email;
                modalContent.appendChild(emailInfo);
                
                const buttonsDiv = document.createElement('div');
                buttonsDiv.className = 'action-buttons';
                
                const emailBtn = document.createElement('button');
                emailBtn.className = 'action-btn email-btn';
                emailBtn.innerHTML = '<i class="fas fa-envelope"></i> إرسال';
                emailBtn.onclick = () => window.location.href = link;
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'action-btn copy-btn';
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> نسخ';
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
                
                // إنشاء QR Code
                if (currentQRCode) {
                    currentQRCode.clear();
                }
                
                currentQRCode = new QRCode(qrCodeDiv, {
                    text: link,
                    width: 200,
                    height: 200,
                    colorDark: "#000000",
                    colorLight: "#ffffff"
                });
                
                const buttonsDiv = document.createElement('div');
                buttonsDiv.className = 'action-buttons';
                
                const downloadBtn = document.createElement('button');
                downloadBtn.className = 'action-btn download-btn';
                downloadBtn.innerHTML = '<i class="fas fa-download"></i> تحميل';
                downloadBtn.onclick = () => {
                    const canvas = qrCodeDiv.querySelector('canvas');
                    if (canvas) {
                        const linkEl = document.createElement('a');
                        linkEl.download = `qrcode-${name}.png`;
                        linkEl.href = canvas.toDataURL();
                        linkEl.click();
                        showNotification('تم تحميل QR Code');
                    }
                };
                
                const copyBtn = document.createElement('button');
                copyBtn.className = 'action-btn copy-btn';
                copyBtn.innerHTML = '<i class="fas fa-copy"></i> نسخ';
                copyBtn.onclick = () => {
                    navigator.clipboard.writeText(link).then(() => {
                        showNotification('تم نسخ الرابط بنجاح');
                    });
                };
                
                const openBtn = document.createElement('button');
                openBtn.className = 'action-btn';
                openBtn.innerHTML = '<i class="fas fa-external-link-alt"></i> فتح';
                openBtn.style.background = 'var(--secondary)';
                openBtn.onclick = () => window.open(link, '_blank');
                
                buttonsDiv.appendChild(downloadBtn);
                buttonsDiv.appendChild(copyBtn);
                
                if (type === 'social') {
                    const socialBtn = document.createElement('button');
                    socialBtn.className = 'action-btn';
                    socialBtn.innerHTML = '<i class="fas fa-share"></i> مشاركة';
                    socialBtn.style.background = '#FF9800';
                    socialBtn.onclick = () => {
                        if (navigator.share) {
                            navigator.share({
                                title: name,
                                text: `تابعني على ${name}`,
                                url: link
                            });
                        }
                    };
                    buttonsDiv.appendChild(socialBtn);
                } else {
                    buttonsDiv.appendChild(openBtn);
                }
                
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
        
        // تحسين الأداء: إزالة تأثيرات الماوس الثقيلة
        document.addEventListener('DOMContentLoaded', () => {
            // تم إزالة جميع التأثيرات الثقيلة
            console.log('الموقع محسّن للأداء ✓');
        });
    </script>
</body>
</html>
