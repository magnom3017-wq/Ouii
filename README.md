<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>واجهة حسابات التواصل الاجتماعي</title>
<style>
  :root {
    --primary-color: #0066cc;
    --error-color: #ff4d4d;
    --shadow: 0 3px 6px rgba(0,0,0,0.16);
    --transition: all 0.3s ease;
  }
  
  body {
    font-family: 'Arial', sans-serif;
    background: #f0f0f0;
    margin: 20px;
    line-height: 1.6;
  }
  
  .social-container {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    justify-content: center;
    max-width: 800px;
    margin: 0 auto;
  }
  
  .icon-wrapper {
    position: relative;
  }
  
  .icon {
    width: 64px;
    height: 64px;
    border-radius: 50%;
    background: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: var(--shadow);
    cursor: pointer;
    transition: var(--transition);
    border: none;
    outline: none;
  }
  
  .icon:hover,
  .icon:focus {
    transform: scale(1.12);
  }
  
  .icon img {
    width: 32px;
    height: 32px;
  }
  
  /* Tooltip window */
  .tooltip {
    visibility: hidden;
    opacity: 0;
    width: 220px;
    background-color: #fff;
    border-radius: 8px;
    border: 1px solid #ccc;
    padding: 12px;
    position: absolute;
    top: 80px;
    right: 0;
    box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    z-index: 10;
    font-size: 14px;
    color: #333;
    line-height: 1.4;
    transition: var(--transition);
  }
  
  .icon-wrapper:hover .tooltip,
  .icon-wrapper:focus-within .tooltip {
    visibility: visible;
    opacity: 1;
  }
  
  .tooltip .link {
    margin-top: 8px;
    display: block;
    color: var(--primary-color);
    text-decoration: underline;
    word-wrap: break-word;
  }
  
  .copy-button {
    margin-top: 8px;
    padding: 6px 10px;
    background-color: var(--primary-color);
    color: #fff;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 13px;
    transition: var(--transition);
  }
  
  .copy-button:hover,
  .copy-button:focus {
    background-color: #004a99;
    outline: none;
  }
  
  .error-message {
    background-color: var(--error-color);
    color: #fff;
    padding: 8px;
    border-radius: 6px;
    font-weight: bold;
    text-align: center;
  }
  
  /* Toast notification */
  .toast {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background-color: #333;
    color: white;
    padding: 12px 20px;
    border-radius: 4px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    z-index: 1000;
    opacity: 0;
    transform: translateY(20px);
    transition: var(--transition);
  }
  
  .toast.show {
    opacity: 1;
    transform: translateY(0);
  }
  
  /* Responsive adjustments */
  @media (max-width: 600px) {
    .social-container {
      gap: 8px;
    }
    
    .icon {
      width: 56px;
      height: 56px;
    }
    
    .icon img {
      width: 28px;
      height: 28px;
    }
    
    .tooltip {
      width: 200px;
      top: 70px;
    }
  }
</style>
</head>
<body>

<div class="social-container">

  <!-- فيسبوك -->
  <div class="icon-wrapper" tabindex="0" aria-label="فيسبوك">
    <a href="https://www.facebook.com/share/1BgY11DMQM/" target="_blank" rel="noopener noreferrer" class="icon" aria-describedby="facebook-tooltip">
      <img src="https://cdn-icons-png.flaticon.com/512/733/733547.png" alt="فيسبوك" />
    </a>
    <div class="tooltip" id="facebook-tooltip" role="tooltip">
      رابط فيسبوك: <a href="https://www.facebook.com/share/1BgY11DMQM/" target="_blank" class="link">https://www.facebook.com/share/1BgY11DMQM/</a>
      <button class="copy-button" onclick="copyToClipboard('https://www.facebook.com/share/1BgY11DMQM/')">نسخ الرابط</button>
    </div>
  </div>

  <!-- إنستغرام -->
  <div class="icon-wrapper" tabindex="0" aria-label="إنستغرام">
    <a href="https://www.instagram.com/kamola_463" target="_blank" rel="noopener noreferrer" class="icon" aria-describedby="instagram-tooltip">
      <img src="https://cdn-icons-png.flaticon.com/512/2111/2111463.png" alt="إنستغرام" />
    </a>
    <div class="tooltip" id="instagram-tooltip" role="tooltip">
      رابط إنستغرام: <a href="https://www.instagram.com/kamola_463" target="_blank" class="link">https://www.instagram.com/kamola_463</a>
      <button class="copy-button" onclick="copyToClipboard('https://www.instagram.com/kamola_463')">نسخ الرابط</button>
    </div>
  </div>

  <!-- تيليجرام -->
  <div class="icon-wrapper" tabindex="0" aria-label="تيليجرام">
    <a href="https://t.me/ou_kamel" target="_blank" rel="noopener noreferrer" class="icon" aria-describedby="telegram-tooltip">
      <img src="https://cdn-icons-png.flaticon.com/512/2111/2111646.png" alt="تيليجرام" />
    </a>
    <div class="tooltip" id="telegram-tooltip" role="tooltip">
      رابط تيليجرام: <a href="https://t.me/ou_kamel" target="_blank" class="link">https://t.me/ou_kamel</a>
      <button class="copy-button" onclick="copyToClipboard('https://t.me/ou_kamel')">نسخ الرابط</button>
    </div>
  </div>

  <!-- سناب شات -->
  <div class="icon-wrapper" tabindex="0" aria-label="سناب شات">
    <a href="https://www.snapchat.com/add/kamola252903" target="_blank" rel="noopener noreferrer" class="icon" aria-describedby="snapchat-tooltip">
      <img src="https://cdn-icons-png.flaticon.com/512/733/733585.png" alt="سناب شات" />
    </a>
    <div class="tooltip" id="snapchat-tooltip" role="tooltip">
      رابط سناب شات: <a href="https://www.snapchat.com/add/kamola252903" target="_blank" class="link">https://www.snapchat.com/add/kamola252903</a>
      <button class="copy-button" onclick="copyToClipboard('https://www.snapchat.com/add/kamola252903')">نسخ الرابط</button>
    </div>
  </div>

  <!-- تيك توك -->
  <div class="icon-wrapper" tabindex="0" aria-label="تيك توك">
    <a href="https://www.tiktok.com/@kamola.3017" target="_blank" rel="noopener noreferrer" class="icon" aria-describedby="tiktok-tooltip">
      <img src="https://cdn-icons-png.flaticon.com/512/3046/3046124.png" alt="تيك توك" />
    </a>
    <div class="tooltip" id="tiktok-tooltip" role="tooltip">
      رابط تيك توك: <a href="https://www.tiktok.com/@kamola.3017" target="_blank" class="link">https://www.tiktok.com/@kamola.3017</a>
      <button class="copy-button" onclick="copyToClipboard('https://www.tiktok.com/@kamola.3017')">نسخ الرابط</button>
    </div>
  </div>

  <!-- يوتيوب -->
  <div class="icon-wrapper" tabindex="0" aria-label="يوتيوب">
    <a href="https://www.youtube.com/@kamola3017" target="_blank" rel="noopener noreferrer" class="icon" aria-describedby="youtube-tooltip">
      <img src="https://cdn-icons-png.flaticon.com/512/1384/1384060.png" alt="يوتيوب" />
    </a>
    <div class="tooltip" id="youtube-tooltip" role="tooltip">
      رابط يوتيوب: <a href="https://www.youtube.com/@kamola3017" target="_blank" class="link">https://www.youtube.com/@kamola3017</a>
      <button class="copy-button" onclick="copyToClipboard('https://www.youtube.com/@kamola3017')">نسخ الرابط</button>
    </div>
  </div>

  <!-- تويتر - رسالة لا يوجد حساب -->
  <div class="icon-wrapper" tabindex="0" aria-label="تويتر">
    <div class="icon" style="background:#ff4d4d; cursor: default;" aria-describedby="twitter-tooltip">
      <img src="https://cdn-icons-png.flaticon.com/512/733/733579.png" alt="تويتر" />
    </div>
    <div class="tooltip error-message" id="twitter-tooltip" role="alert" style="width: 180px; text-align:center;">
      لا يوجد حساب تويتر
    </div>
  </div>

  <!-- البريد الإلكتروني -->
  <div class="icon-wrapper" tabindex="0" aria-label="البريد الإلكتروني">
    <button class="icon" onclick="copyToClipboard('magnom3017@gmail.com')" aria-label="نسخ البريد الإلكتروني" aria-describedby="email-tooltip">
      <img src="https://cdn-icons-png.flaticon.com/512/561/561188.png" alt="البريد الإلكتروني" />
    </button>
    <div class="tooltip" id="email-tooltip" role="tooltip">
      البريد الإلكتروني: <span class="link">magnom3017@gmail.com</span>
      <button class="copy-button" onclick="copyToClipboard('magnom3017@gmail.com')">نسخ البريد</button>
    </div>
  </div>

  <!-- رقم الهاتف -->
  <div class="icon-wrapper" tabindex="0" aria-label="رقم الهاتف">
    <button class="icon" onclick="copyToClipboard('+962776274508')" aria-label="نسخ رقم الهاتف" aria-describedby="phone-tooltip">
      <img src="https://cdn-icons-png.flaticon.com/512/15/15874.png" alt="رقم الهاتف" />
    </button>
    <div class="tooltip" id="phone-tooltip" role="tooltip">
      رقم الهاتف: <span class="link">+962776274508</span>
      <button class="copy-button" onclick="copyToClipboard('+962776274508')">نسخ الرقم</button>
      <a href="tel:+962776274508" class="link" style="display:block; margin-top:8px; color:#0066cc;">اتصال مباشر</a>
    </div>
  </div>

</div>

<!-- Toast notification -->
<div class="toast" id="toast"></div>

<script>
  function copyToClipboard(text) {
    navigator.clipboard.writeText(text).then(function() {
      showToast('تم نسخ الرابط: ' + text);
    }, function(err) {
      showToast('فشل النسخ! حاول مجدداً.');
    });
  }
  
  function showToast(message) {
    const toast = document.getElementById('toast');
    toast.textContent = message;
    toast.classList.add('show');
    
    setTimeout(() => {
      toast.classList.remove('show');
    }, 3000);
  }
</script>

</body>
</html>
