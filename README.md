<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Øu••ᵏᵃᵐᵃˡ࿐ - Social Media</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<!-- مكتبة QR Code صحيحة -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Segoe UI',Tahoma,Geneva,Verdana,sans-serif;}
:root{
--primary:#8B5CF6;
--secondary:#06D6A0;
--accent:#EF476F;
--dark:#0F0F0F;
--darker:#070707;
--light:#F8FAFC;
--card-light:#FFFFFF;
--card-dark:#1A1A1A;
--text-light:#2D3748;
--text-dark:#E2E8F0;
--shadow:0 10px 25px rgba(0,0,0,0.1);
}
body{
    background:linear-gradient(135deg,var(--light) 0%,#E2E8F0 100%);
    color:var(--text-light);
    min-height:100vh;
    transition:all 0.4s ease;
    overflow-x:hidden;
}
body.dark-mode{
    background:linear-gradient(135deg,var(--dark) 0%,var(--darker) 100%);
    color:var(--text-dark);
}
.container{
    width:100%;
    max-width:1200px;
    margin:0 auto;
    padding:20px;
}
.header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding:20px 0;
    margin-bottom:40px;
}
.logo{
    font-size:28px;
    font-weight:800;
    background:linear-gradient(135deg,var(--primary),var(--secondary));
    -webkit-background-clip:text;
    -webkit-text-fill-color:transparent;
    text-shadow:0 2px 10px rgba(139,92,246,0.3);
}
.header-buttons{
    display:flex;
    gap:15px;
}
.icon-btn{
    width:50px;
    height:50px;
    border-radius:50%;
    background:var(--card-light);
    border:none;
    display:flex;
    align-items:center;
    justify-content:center;
    cursor:pointer;
    box-shadow:var(--shadow);
    transition:all 0.3s ease;
    color:var(--primary);
    font-size:20px;
}
.dark-mode .icon-btn{
    background:var(--card-dark);
    color:var(--secondary);
}
.icon-btn:hover{
    transform:translateY(-3px);
    box-shadow:0 15px 30px rgba(0,0,0,0.15);
}
.social-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit, minmax(280px, 1fr));
    gap:25px;
    margin-top:30px;
}
.social-card{
    background:var(--card-light);
    border-radius:20px;
    padding:25px 20px;
    text-align:center;
    box-shadow:var(--shadow);
    transition:all 0.3s ease;
    cursor:pointer;
    border:2px solid transparent;
}
.dark-mode .social-card{
    background:var(--card-dark);
    border:2px solid #2D3748;
}
.social-card:hover{
    transform:translateY(-8px);
    box-shadow:0 20px 40px rgba(0,0,0,0.15);
    border-color:var(--primary);
}
.social-icon{
    width:70px;
    height:70px;
    border-radius:50%;
    display:flex;
    align-items:center;
    justify-content:center;
    margin:0 auto 15px;
    font-size:30px;
    color:white;
    box-shadow:0 5px 15px rgba(0,0,0,0.2);
}
.social-name{
    font-weight:600;
    font-size:16px;
    margin-bottom:8px;
}
.social-username{
    color:#64748B;
    font-size:14px;
    direction:ltr;
}
.dark-mode .social-username{
    color:#94A3B8;
}

/* نافذة المشاركة - تم إصلاح z-index */
.share-modal{
    display:none;
    position:fixed;
    top:0;
    left:0;
    width:100vw;
    height:100vh;
    background:rgba(0,0,0,0.9);
    z-index:9999; /* تم زيادة الـ z-index */
    align-items:center;
    justify-content:center;
    overflow:auto;
}
.share-content{
    background:var(--darker);
    border-radius:25px;
    padding:40px;
    text-align:center;
    max-width:400px;
    width:90%;
    height:auto;
    max-height:90vh;
    overflow-y:auto;
    box-shadow:0 25px 50px rgba(0,0,0,0.5);
    border:2px solid var(--primary);
    position:relative;
    z-index:10000;
}
.share-title{
    color:white;
    font-size:24px;
    margin-bottom:25px;
    font-weight:700;
}
.qrcode-container{
    background:white;
    padding:20px;
    border-radius:15px;
    margin:20px 0;
    display:inline-block;
    min-width:200px;
    min-height:200px;
    display:flex;
    align-items:center;
    justify-content:center;
}
#modalQRCode{
    width:200px;
    height:200px;
    display:flex;
    align-items:center;
    justify-content:center;
}
.share-buttons{
    display:flex;
    flex-direction:column;
    gap:15px;
    margin-top:25px;
}
.share-btn{
    padding:15px;
    border:none;
    border-radius:12px;
    font-weight:600;
    cursor:pointer;
    transition:all 0.3s ease;
    display:flex;
    align-items:center;
    justify-content:center;
    gap:8px;
    font-size:16px;
    width:100%;
}
.download-btn{
    background:var(--primary);
    color:white;
}
.copy-btn{
    background:var(--accent);
    color:white;
}
.share-app-btn{
    background:var(--secondary);
    color:white;
}
.share-btn:hover{
    transform:translateY(-3px);
    box-shadow:0 10px 20px rgba(0,0,0,0.3);
}
.close-share{
    position:absolute;
    top:20px;
    left:20px;
    background:none;
    border:none;
    color:white;
    font-size:24px;
    cursor:pointer;
    z-index:10001;
}

/* ألوان وسائل التواصل */
.facebook{background:linear-gradient(135deg,#1877F2,#0D5FBF);}
.instagram{background:linear-gradient(135deg,#E4405F,#C13584);}
.telegram{background:linear-gradient(135deg,#0088CC,#006699);}
.snapchat{background:linear-gradient(135deg,#FFFC00,#FFD700);color:#000 !important;}
.tiktok{background:linear-gradient(135deg,#000000,#25F4EE);}
.youtube{background:linear-gradient(135deg,#FF0000,#CC0000);}
.twitter{background:linear-gradient(135deg,#1DA1F2,#0D8BD9);}
.email{background:linear-gradient(135deg,#EA4335,#D14836);}
.phone{background:linear-gradient(135deg,#34A853,#2E8B57);}
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
<!-- البطاقات -->
<div class="social-card" data-name="فيسبوك" data-link="https://www.facebook.com/share/1BgY11DMQM/" data-icon="facebook">
<div class="social-icon facebook"><i class="fab fa-facebook-f"></i></div>
<div class="social-name">فيسبوك</div>
<div class="social-username">Kamola</div>
</div>
<div class="social-card" data-name="إنستغرام" data-link="https://www.instagram.com/kamola_463" data-icon="instagram">
<div class="social-icon instagram"><i class="fab fa-instagram"></i></div>
<div class="social-name">إنستغرام</div>
<div class="social-username">@kamola_463</div>
</div>
<div class="social-card" data-name="تيليجرام" data-link="https://t.me/ou_kamel" data-icon="telegram">
<div class="social-icon telegram"><i class="fab fa-telegram-plane"></i></div>
<div class="social-name">تيليجرام</div>
<div class="social-username">@ou_kamel</div>
</div>
<div class="social-card" data-name="سناب شات" data-link="https://www.snapchat.com/add/kamola252903" data-icon="snapchat">
<div class="social-icon snapchat"><i class="fab fa-snapchat-ghost"></i></div>
<div class="social-name">سناب شات</div>
<div class="social-username">kamola252903</div>
</div>
<div class="social-card" data-name="تيك توك" data-link="https://www.tiktok.com/@kamola.3017" data-icon="tiktok">
<div class="social-icon tiktok"><i class="fab fa-tiktok"></i></div>
<div class="social-name">تيك توك</div>
<div class="social-username">@kamola.3017</div>
</div>
<div class="social-card" data-name="يوتيوب" data-link="https://www.youtube.com/@kamola3017" data-icon="youtube">
<div class="social-icon youtube"><i class="fab fa-youtube"></i></div>
<div class="social-name">يوتيوب</div>
<div class="social-username">@kamola3017</div>
</div>
<div class="social-card" data-name="تويتر" data-link="https://x.com/3017Kamola44307?t=107y45_c29JA1E-ClTzg_A&s=09" data-icon="twitter">
<div class="social-icon twitter"><i class="fab fa-twitter"></i></div>
<div class="social-name">تويتر</div>
<div class="social-username">@3017Kamola44307</div>
</div>
<div class="social-card" data-name="البريد الإلكتروني" data-link="mailto:magnom3017@gmail.com" data-icon="email">
<div class="social-icon email"><i class="fas fa-envelope"></i></div>
<div class="social-name">البريد الإلكتروني</div>
<div class="social-username">magnom3017@gmail.com</div>
</div>
<div class="social-card" data-name="رقم الهاتف" data-link="tel:+962776274508" data-icon="phone">
<div class="social-icon phone"><i class="fas fa-phone"></i></div>
<div class="social-name">رقم الهاتف</div>
<div class="social-username">+962776274508</div>
</div>
</div>
</div>

<!-- نافذة المشاركة -->
<div class="share-modal" id="shareModal">
<button class="close-share" id="closeShareBtn"><i class="fas fa-times"></i></button>
<div class="share-content">
<h2 class="share-title" id="modalAppName">اسم التطبيق</h2>
<div class="qrcode-container">
<div id="modalQRCode"></div> <!-- تم تغييرها إلى div -->
</div>
<div class="share-buttons">
<button class="share-btn download-btn" id="downloadQRBtn"><i class="fas fa-download"></i> تحميل QR Code</button>
<button class="share-btn copy-btn" id="copyLinkBtn"><i class="fas fa-copy"></i> نسخ الرابط</button>
<button class="share-btn share-app-btn" id="openAppBtn"><i class="fas fa-share"></i> فتح التطبيق</button>
</div>
</div>
</div>

<script>
// ========== 1. الوضع المظلم ==========
const darkModeToggle = document.getElementById('darkModeToggle');
const body = document.body;

darkModeToggle.addEventListener('click', () => {
    body.classList.toggle('dark-mode');
    
    // تبديل الأيقونة
    const icon = darkModeToggle.querySelector('i');
    if (body.classList.contains('dark-mode')) {
        icon.classList.remove('fa-moon');
        icon.classList.add('fa-sun');
    } else {
        icon.classList.remove('fa-sun');
        icon.classList.add('fa-moon');
    }
});

// ========== 2. فتح نافذة المشاركة ==========
const shareModal = document.getElementById('shareModal');
const modalAppName = document.getElementById('modalAppName');
const modalQRCodeElement = document.getElementById('modalQRCode');
const copyLinkBtn = document.getElementById('copyLinkBtn');
const openAppBtn = document.getElementById('openAppBtn');
const closeShareBtn = document.getElementById('closeShareBtn');
const downloadQRBtn = document.getElementById('downloadQRBtn');

let currentQRCode = null;
let currentLink = '';

// فتح النافذة عند النقر على أي بطاقة
document.querySelectorAll('.social-card').forEach(card => {
    card.addEventListener('click', () => {
        const name = card.getAttribute('data-name');
        const link = card.getAttribute('data-link');

        // تحديث النص في النافذة
        modalAppName.textContent = name;
        currentLink = link;
        
        // إنشاء QR Code جديد
        generateQRCode(link);
        
        // إظهار النافذة
        shareModal.style.display = 'flex';
        document.body.style.overflow = 'hidden';
    });
});

// وظيفة إنشاء QR Code
function generateQRCode(url) {
    // مسح QR Code السابق
    modalQRCodeElement.innerHTML = '';
    
    // إنشاء QR Code جديد
    currentQRCode = new QRCode(modalQRCodeElement, {
        text: url,
        width: 200,
        height: 200,
        colorDark: "#000000",
        colorLight: "#ffffff",
        correctLevel: QRCode.CorrectLevel.H
    });
}

// ========== 3. أزرار النافذة المنبثقة ==========

// زر نسخ الرابط
copyLinkBtn.addEventListener('click', () => {
    if (currentLink) {
        navigator.clipboard.writeText(currentLink).then(() => {
            // تغيير النص مؤقتاً للتأكيد
            const originalText = copyLinkBtn.innerHTML;
            copyLinkBtn.innerHTML = '<i class="fas fa-check"></i> تم النسخ!';
            copyLinkBtn.style.background = '#10B981';
            
            setTimeout(() => {
                copyLinkBtn.innerHTML = originalText;
                copyLinkBtn.style.background = '';
            }, 2000);
        });
    }
});

// زر فتح التطبيق
openAppBtn.addEventListener('click', () => {
    if (currentLink) {
        window.open(currentLink, '_blank');
    }
});

// زر تحميل QR Code
downloadQRBtn.addEventListener('click', function() {
    if (currentQRCode) {
        const canvas = modalQRCodeElement.querySelector('canvas');
        if (canvas) {
            const link = document.createElement('a');
            link.download = `QR-${modalAppName.textContent}.png`;
            link.href = canvas.toDataURL('image/png');
            link.click();
        }
    }
});

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

// ========== 4. زر المشاركة في الهيدر ==========
const shareBtn = document.getElementById('shareBtn');
shareBtn.addEventListener('click', () => {
    // مشاركة رابط الموقع الحالي
    if (navigator.share) {
        navigator.share({
            title: 'Øu••ᵏᵃᵐᵃˡ࿐ - وسائل التواصل',
            text: 'تعرف على روابط وسائل التواصل الخاصة بي',
            url: window.location.href
        });
    } else {
        // نسخ الرابط إذا لم يدعم المتصفح المشاركة
        navigator.clipboard.writeText(window.location.href).then(() => {
            alert('تم نسخ رابط الموقع إلى الحافظة');
        });
    }
});
</script>
</body>
</html>
