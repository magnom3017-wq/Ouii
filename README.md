<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Øu••ᵏᵃᵐᵃˡ࿐ - Social Media</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
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
        }

        body {
            background: linear-gradient(135deg, var(--light) 0%, #E2E8F0 100%);
            color: var(--text-light);
            min-height: 100vh;
            transition: all 0.4s ease;
        }

        body.dark-mode {
            background: linear-gradient(135deg, var(--dark) 0%, var(--darker) 100%);
            color: var(--text-dark);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* الهيدر */
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
            text-shadow: 0 2px 10px rgba(139, 92, 246, 0.3);
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
        }

        .dark-mode .icon-btn {
            background: var(--card-dark);
            color: var(--secondary);
        }

        .icon-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }

        /* شبكة الحسابات */
        .social-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }

        .social-card {
            background: var(--card-light);
            border-radius: 20px;
            padding: 25px 20px;
            text-align: center;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            cursor: pointer;
            border: 2px solid transparent;
        }

        .dark-mode .social-card {
            background: var(--card-dark);
            border: 2px solid #2D3748;
        }

        .social-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
            border-color: var(--primary);
        }

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
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .social-name {
            font-weight: 600;
            font-size: 16px;
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

        /* نافذة المشاركة */
        .share-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.9);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .share-content {
            background: var(--darker);
            border-radius: 25px;
            padding: 40px;
            text-align: center;
            max-width: 400px;
            width: 90%;
            box-shadow: 0 25px 50px rgba(0,0,0,0.5);
            border: 2px solid var(--primary);
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
        }

        .qrcode-placeholder {
            width: 200px;
            height: 200px;
            background: linear-gradient(45deg, #E2E8F0, #CBD5E0);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #64748B;
            font-weight: 600;
        }

        .share-buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
            margin-top: 25px;
        }

        .share-btn {
            flex: 1;
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
        }

        .download-btn {
            background: var(--primary);
            color: white;
        }

        .copy-btn {
            background: var(--accent);
            color: white;
        }

        .share-app-btn {
            background: var(--secondary);
            color: white;
        }

        .share-btn:hover {
            transform: translateY(-3px);
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
        }

        /* ألوان الأيقونات */
        .facebook { background: linear-gradient(135deg, #1877F2, #0D5FBF); }
        .instagram { background: linear-gradient(135deg, #E4405F, #C13584); }
        .telegram { background: linear-gradient(135deg, #0088CC, #006699); }
        .snapchat { background: linear-gradient(135deg, #FFFC00, #FFD700); color: #000 !important; }
        .tiktok { background: linear-gradient(135deg, #000000, #25F4EE); }
        .youtube { background: linear-gradient(135deg, #FF0000, #CC0000); }
        .twitter { background: linear-gradient(135deg, #1DA1F2, #0D8BD9); }
        .email { background: linear-gradient(135deg, #EA4335, #D14836); }
        .phone { background: linear-gradient(135deg, #34A853, #2E8B57); }

        @media (max-width: 768px) {
            .social-grid {
                grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
                gap: 15px;
            }
            
            .social-card {
                padding: 20px 15px;
            }
            
            .social-icon {
                width: 60px;
                height: 60px;
                font-size: 25px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- الهيدر -->
        <div class="header">
            <div class="logo">Øu••ᵏᵃᵐᵃˡ࿐</div>
            <div class="header-buttons">
                <button class="icon-btn" id="darkModeToggle">
                    <i class="fas fa-moon"></i>
                </button>
                <button class="icon-btn" id="shareBtn">
                    <i class="fas fa-share-alt"></i>
                </button>
            </div>
        </div>

        <!-- شبكة الحسابات -->
        <div class="social-grid">
            <!-- فيسبوك -->
            <div class="social-card" onclick="openLink('https://www.facebook.com/share/1BgY11DMQM/')">
                <div class="social-icon facebook">
                    <i class="fab fa-facebook-f"></i>
                </div>
                <div class="social-name">فيسبوك</div>
                <div class="social-username">Kamola</div>
            </div>

            <!-- إنستغرام -->
            <div class="social-card" onclick="openLink('https://www.instagram.com/kamola_463')">
                <div class="social-icon instagram">
                    <i class="fab fa-instagram"></i>
                </div>
                <div class="social-name">إنستغرام</div>
                <div class="social-username">@kamola_463</div>
            </div>

            <!-- تيليجرام -->
            <div class="social-card" onclick="openLink('https://t.me/ou_kamel')">
                <div class="social-icon telegram">
                    <i class="fab fa-telegram-plane"></i>
                </div>
                <div class="social-name">تيليجرام</div>
                <div class="social-username">@ou_kamel</div>
            </div>

            <!-- سناب شات -->
            <div class="social-card" onclick="openLink('https://www.snapchat.com/add/kamola252903')">
                <div class="social-icon snapchat">
                    <i class="fab fa-snapchat-ghost"></i>
                </div>
                <div class="social-name">سناب شات</div>
                <div class="social-username">kamola252903</div>
            </div>

            <!-- تيك توك -->
            <div class="social-card" onclick="openLink('https://www.tiktok.com/@kamola.3017')">
                <div class="social-icon tiktok">
                    <i class="fab fa-tiktok"></i>
                </div>
                <div class="social-name">تيك توك</div>
                <div class="social-username">@kamola.3017</div>
            </div>

            <!-- يوتيوب -->
            <div class="social-card" onclick="openLink('https://www.youtube.com/@kamola3017')">
                <div class="social-icon youtube">
                    <i class="fab fa-youtube"></i>
                </div>
                <div class="social-name">يوتيوب</div>
                <div class="social-username">@kamola3017</div>
            </div>

            <!-- تويتر -->
            <div class="social-card" onclick="showMessage('لا يوجد حساب تويتر حالياً')">
                <div class="social-icon twitter">
                    <i class="fab fa-twitter"></i>
                </div>
                <div class="social-name">تويتر</div>
                <div class="social-username">غير متوفر</div>
            </div>

            <!-- البريد الإلكتروني -->
            <div class="social-card" onclick="copyToClipboard('magnom3017@gmail.com', 'البريد الإلكتروني')">
                <div class="social-icon email">
                    <i class="fas fa-envelope"></i>
                </div>
                <div class="social-name">البريد الإلكتروني</div>
                <div class="social-username">magnom3017@gmail.com</div>
            </div>

            <!-- رقم الهاتف -->
            <div class="social-card" onclick="copyToClipboard('+962776274508', 'رقم الهاتف')">
                <div class="social-icon phone">
                    <i class="fas fa-phone"></i>
                </div>
                <div class="social-name">رقم الهاتف</div>
                <div class="social-username">+962776274508</div>
            </div>
        </div>
    </div>

    <!-- نافذة المشاركة -->
    <div class="share-modal" id="shareModal">
        <button class="close-share" onclick="closeShareModal()">
            <i class="fas fa-times"></i>
        </button>
        <div class="share-content">
            <h2 class="share-title">مشاركة الموقع</h2>
            <div class="qrcode-container">
                <div class="qrcode-placeholder">
                    QR Code
                </div>
            </div>
            <div class="share-buttons">
                <button class="share-btn download-btn" onclick="downloadQR()">
                    <i class="fas fa-download"></i> تحميل
                </button>
                <button class="share-btn copy-btn" onclick="copyLink()">
                    <i class="fas fa-copy"></i> نسخ
                </button>
                <button class="share-btn share-app-btn" onclick="shareToApps()">
                    <i class="fas fa-share"></i> مشاركة
                </button>
            </div>
        </div>
    </div>

    <script>
        // الوضع المظلم
        const darkModeToggle = document.getElementById('darkModeToggle');
        const body = document.body;

        darkModeToggle.addEventListener('click', () => {
            body.classList.toggle('dark-mode');
            darkModeToggle.innerHTML = body.classList.contains('dark-mode') 
                ? '<i class="fas fa-sun"></i>' 
                : '<i class="fas fa-moon"></i>';
        });

        // نافذة المشاركة
        const shareModal = document.getElementById('shareModal');
        const shareBtn = document.getElementById('shareBtn');

        shareBtn.addEventListener('click', () => {
            shareModal.style.display = 'flex';
        });

        function closeShareModal() {
            shareModal.style.display = 'none';
        }

        // وظائف أخرى
        function openLink(url) {
            window.open(url, '_blank');
        }

        function showMessage(message) {
            alert(message);
        }

        function copyToClipboard(text, type) {
            navigator.clipboard.writeText(text).then(() => {
                alert(`تم نسخ ${type}: ${text}`);
            });
        }

        function downloadQR() {
            alert('سيتم تحميل صورة QR Code');
            // هنا يمكن إضافة كود لتحميل الصورة فعلياً
        }

        function copyLink() {
            const currentUrl = window.location.href;
            navigator.clipboard.writeText(currentUrl).then(() => {
                alert('تم نسخ رابط الموقع: ' + currentUrl);
            });
        }

        function shareToApps() {
            if (navigator.share) {
                navigator.share({
                    title: 'Øu••ᵏᵃᵐᵃˡ࿐ - Social Media',
                    url: window.location.href
                });
            } else {
                alert('ميزة المشاركة غير مدعومة في هذا المتصفح');
            }
        }

        // إغلاق نافذة المشاركة بالنقر خارجها
        window.addEventListener('click', (e) => {
            if (e.target === shareModal) {
                closeShareModal();
            }
        });
    </script>
</body>
</html>
