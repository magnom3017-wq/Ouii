# Ouii
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>مكتبتي</title>
<!-- خط جديد للاسم -->
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@700&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet"/>
<style>
  body {
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: #ffffff;
    color: #0d3b66;
  }
  header, nav {
    background-color: #e6f0ff;
  }
  header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 15px;
    position: sticky;
    top: 0;
    z-index: 1000;
  }
  header .title {
    font-family: 'Cairo', sans-serif;
    font-size: 26px;
    cursor: pointer;
  }
  header .buttons {
    display: flex;
    gap: 15px;
  }
  button.icon-btn {
    background: none;
    border: none;
    color: #0d3b66;
    font-size: 22px;
    cursor: pointer;
  }
  button.icon-btn:hover {
    color: #1c5fad;
  }

  /* Sidebar */
  aside.sidebar {
    position: fixed;
    right: -300px;
    top: 0;
    width: 300px;
    height: 100%;
    background-color: #f0f4ff;
    overflow-y: auto;
    transition: right 0.3s ease-in-out;
    padding: 20px;
    box-sizing: border-box;
    z-index: 1500;
  }
  aside.sidebar.open {
    right: 0;
  }
  aside.sidebar h2 {
    margin-top: 30px;
  }
  aside.sidebar ul {
    list-style: none;
    padding: 0;
  }
  aside.sidebar ul li {
    margin: 15px 0;
    cursor: pointer;
    color: #0d3b66;
  }
  aside.sidebar ul li:hover {
    color: #1c5fad;
  }
  .close-btn {
    position: absolute;
    top: 10px;
    left: 10px;
    background: none;
    border: none;
    font-size: 22px;
    cursor: pointer;
    color: #0d3b66;
  }
  .close-btn:hover {
    color: #1c5fad;
  }

  main {
    padding: 15px;
    min-height: 80vh;
  }
  .banner {
    background: url('https://images.unsplash.com/photo-1524995997946-a1c2e315a42f?auto=format&fit=crop&w=800&q=80') center/cover no-repeat;
    height: 180px;
    border-radius: 10px;
    margin-bottom: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: bold;
    font-size: 20px;
    color: white;
    text-shadow: 0 0 5px black;
  }
  .section {
    margin-bottom: 25px;
  }
  .section-header {
    font-weight: bold;
    font-size: 18px;
    margin-bottom: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .section-header button {
    background: none;
    border: none;
    color: #1c5fad;
    cursor: pointer;
    font-size: 14px;
  }
  .horizontal-scroll {
    display: flex;
    overflow-x: auto;
    gap: 15px;
    padding-bottom: 10px;
  }
  .book-card {
    background-color: #e6f0ff;
    border-radius: 8px;
    width: 120px;
    flex-shrink: 0;
    cursor: pointer;
    text-align: center;
  }
  .book-card img {
    width: 100%;
    height: 160px;
    object-fit: cover;
    border-radius: 8px 8px 0 0;
  }
  .book-info {
    padding: 10px;
  }
  .book-title {
    font-family: 'Cairo', sans-serif;
    font-size: 14px;
    font-weight: bold;
    margin-bottom: 6px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  .book-author {
    font-size: 12px;
    opacity: 0.7;
  }
  .read-btn {
    margin-top: 5px;
    background-color: #1c5fad;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 4px 6px;
    font-size: 12px;
    cursor: pointer;
  }
  .read-btn:hover {
    background-color: #0d3b66;
  }
  nav.bottom-nav {
    position: fixed;
    bottom: 0;
    width: 100%;
    background: #e6f0ff;
    display: flex;
    justify-content: space-around;
    padding: 8px 0;
    box-shadow: 0 -2px 5px rgba(0,0,0,0.1);
    z-index: 1000;
  }
  nav.bottom-nav button {
    background: none;
    border: none;
    color: #0d3b66;
    font-size: 24px;
    cursor: pointer;
  }
  nav.bottom-nav button.active {
    color: #1c5fad;
  }
  .horizontal-scroll::-webkit-scrollbar {
    height: 6px;
  }
  .horizontal-scroll::-webkit-scrollbar-thumb {
    background: #1c5fad;
    border-radius: 3px;
  }

  /* واجهات ثانوية (Profile، Settings ...) */
  .overlay {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.4);
    z-index: 2000;
  }
  .overlay.open {
    display: block;
  }
  .modal {
    background: #ffffff;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 90%;
    max-width: 400px;
    border-radius: 10px;
    padding: 20px;
    box-sizing: border-box;
    z-index: 2100;
    box-shadow: 0 0 10px rgba(0,0,0,0.3);
  }
  .modal h2 {
    margin-top: 30px;
  }
</style>
</head>
<body>

<header>
  <div class="buttons">
    <button class="icon-btn" id="menuBtn" title="عرض القائمة"><span class="material-icons">menu</span></button>
    <button class="icon-btn" id="searchBtn" title="بحث"><span class="material-icons">search</span></button>
  </div>
  <div class="title" onclick="goHome()">مكتبتي</div>
  <div class="buttons">
    <button class="icon-btn" id="notificationsBtn" title="الإشعارات"><span class="material-icons">notifications</span></button>
    <button class="icon-btn" id="accountBtn" title="حسابي"><span class="material-icons">account_circle</span></button>
  </div>
</header>

<aside class="sidebar" id="sidebar">
  <button class="close-btn" onclick="closeSidebar()">✖</button>
  <h2>القائمة</h2>
  <ul>
    <li onclick="openModal('profileModal')">حسابي</li>
    <li onclick="openModal('settingsModal')">الإعدادات</li>
    <li onclick="toggleDarkMode()">الوضع الداكن/الفاتح</li>
    <li onclick="shareApp()">مشاركة التطبيق</li>
    <li onclick="contactUs()">تواصل معنا</li>
    <li onclick="aboutApp()">عن التطبيق</li>
  </ul>
</aside>

<main>
  <div class="banner" tabindex="0">
    "اقرأ لتتغير حياتك"
  </div>

  <section class="section">
    <div class="section-header">
      <span>أقسام الكتب</span>
      <button onclick="seeAllSections()">عرض المزيد</button>
    </div>
    <div class="horizontal-scroll" id="categoriesScroll">
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=علوم" alt="علوم"/>
        <div class="book-info"><div class="book-title">علوم</div></div>
        <button class="read-btn" onclick="readBook('book-science.pdf')">قراءة</button>
      </div>
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=أدب" alt="أدب"/>
        <div class="book-info"><div class="book-title">أدب</div></div>
        <button class="read-btn" onclick="readBook('book-literature.pdf')">قراءة</button>
      </div>
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=تاريخ" alt="تاريخ"/>
        <div class="book-info"><div class="book-title">تاريخ</div></div>
        <button class="read-btn" onclick="readBook('book-history.pdf')">قراءة</button>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="section-header">
      <span>كتب شائعة اليوم</span>
      <button onclick="seeMorePopular()">عرض المزيد</button>
    </div>
    <div class="horizontal-scroll" id="popularBooksScroll">
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=كتاب1" alt="كتاب 1"/>
        <div class="book-info"><div class="book-title">كتاب 1</div><div class="book-author">مؤلف 1</div></div>
        <button class="read-btn" onclick="readBook('book1.pdf')">قراءة</button>
      </div>
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=كتاب2" alt="كتاب 2"/>
        <div class="book-info"><div class="book-title">كتاب 2</div><div class="book-author">مؤلف 2</div></div>
        <button class="read-btn" onclick="readBook('book2.pdf')">قراءة</button>
      </div>
    </div>
  </section>
</main>

<nav class="bottom-nav">
  <button id="navHome" class="active" title="الرئيسية"><span class="material-icons">home</span></button>
  <button id="navCategories" title="الأقسام"><span class="material-icons">category</span></button>
  <button id="navFavorites" title="المفضلة"><span class="material-icons">favorite</span></button>
  <button id="navNotifications" title="الإشعارات"><span class="material-icons">notifications</span></button>
  <button id="navProfile" title="حسابي"><span class="material-icons">person</span></button>
</nav>

<!-- النوافذ المنبثقة للواجهات الثانوية -->
<div class="overlay" id="overlay"></div>

<div class="modal" id="profileModal">
  <button class="close-btn" onclick="closeModal('profileModal')">✖</button>
  <h2>حسابي</h2>
  <p>تفاصيل الحساب هنا...</p>
</div>

<div class="modal" id="settingsModal">
  <button class="close-btn" onclick="closeModal('settingsModal')">✖</button>
  <h2>الإعدادات</h2>
  <p>خيارات الإعدادات هنا...</p>
</div>

<script>
  const sidebar = document.getElementById('sidebar');
  const menuBtn = document.getElementById('menuBtn');
  const overlay = document.getElementById('overlay');

  menuBtn.addEventListener('click', () => { sidebar.classList.toggle('open'); });

  function closeSidebar() {
    sidebar.classList.remove('open');
  }

  function openModal(modalId) {
    document.getElementById(modalId).style.display = 'block';
    overlay.classList.add('open');
  }

  function closeModal(modalId) {
    document.getElementById(modalId).style.display = 'none';
    overlay.classList.remove('open');
  }

  overlay.addEventListener('click', () => {
    document.querySelectorAll('.modal').forEach(m => m.style.display='none');
    overlay.classList.remove('open');
  });

  // وظائف حقيقية للأزرار
  function goHome() { window.location.href = 'index.html'; }
  function toggleDarkMode() { alert('الوضع الداكن/الفاتح سيتم لاحقاً'); }
  function shareApp() { alert('مشاركة التطبيق: رابط + QR'); }
  function contactUs() { window.location.href = 'contact.html'; }
  function aboutApp() { window.location.href = 'about.html'; }
  function seeAllSections() { window.location.href = 'sections.html'; }
  function seeMorePopular() { window.location.href = 'popular.html'; }

  function readBook(file) { window.open(file, '_blank'); }

  // شريط التنقل السفلي
  const navButtons = document.querySelectorAll('nav.bottom-nav button');
  navButtons.forEach(btn => {
    btn.addEventListener('click', () => {
      navButtons.forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
      switch(btn.id) {
        case 'navHome': goHome(); break;
        case 'navCategories': window.location.href='sections.html'; break;
        case 'navFavorites': window.location.href='favorites.html'; break;
        case 'navNotifications': window.location.href='notifications.html'; break;
        case 'navProfile': openModal('profileModal'); break;
      }
    });
  });
</script>
</body>
</html><!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>مكتبتي</title>
<!-- خط جديد للاسم -->
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@700&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet"/>
<style>
  body {
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: #ffffff;
    color: #0d3b66;
  }
  header, nav {
    background-color: #e6f0ff;
  }
  header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 15px;
    position: sticky;
    top: 0;
    z-index: 1000;
  }
  header .title {
    font-family: 'Cairo', sans-serif;
    font-size: 26px;
    cursor: pointer;
  }
  header .buttons {
    display: flex;
    gap: 15px;
  }
  button.icon-btn {
    background: none;
    border: none;
    color: #0d3b66;
    font-size: 22px;
    cursor: pointer;
  }
  button.icon-btn:hover {
    color: #1c5fad;
  }

  /* Sidebar */
  aside.sidebar {
    position: fixed;
    right: -300px;
    top: 0;
    width: 300px;
    height: 100%;
    background-color: #f0f4ff;
    overflow-y: auto;
    transition: right 0.3s ease-in-out;
    padding: 20px;
    box-sizing: border-box;
    z-index: 1500;
  }
  aside.sidebar.open {
    right: 0;
  }
  aside.sidebar h2 {
    margin-top: 30px;
  }
  aside.sidebar ul {
    list-style: none;
    padding: 0;
  }
  aside.sidebar ul li {
    margin: 15px 0;
    cursor: pointer;
    color: #0d3b66;
  }
  aside.sidebar ul li:hover {
    color: #1c5fad;
  }
  .close-btn {
    position: absolute;
    top: 10px;
    left: 10px;
    background: none;
    border: none;
    font-size: 22px;
    cursor: pointer;
    color: #0d3b66;
  }
  .close-btn:hover {
    color: #1c5fad;
  }

  main {
    padding: 15px;
    min-height: 80vh;
  }
  .banner {
    background: url('https://images.unsplash.com/photo-1524995997946-a1c2e315a42f?auto=format&fit=crop&w=800&q=80') center/cover no-repeat;
    height: 180px;
    border-radius: 10px;
    margin-bottom: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: bold;
    font-size: 20px;
    color: white;
    text-shadow: 0 0 5px black;
  }
  .section {
    margin-bottom: 25px;
  }
  .section-header {
    font-weight: bold;
    font-size: 18px;
    margin-bottom: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .section-header button {
    background: none;
    border: none;
    color: #1c5fad;
    cursor: pointer;
    font-size: 14px;
  }
  .horizontal-scroll {
    display: flex;
    overflow-x: auto;
    gap: 15px;
    padding-bottom: 10px;
  }
  .book-card {
    background-color: #e6f0ff;
    border-radius: 8px;
    width: 120px;
    flex-shrink: 0;
    cursor: pointer;
    text-align: center;
  }
  .book-card img {
    width: 100%;
    height: 160px;
    object-fit: cover;
    border-radius: 8px 8px 0 0;
  }
  .book-info {
    padding: 10px;
  }
  .book-title {
    font-family: 'Cairo', sans-serif;
    font-size: 14px;
    font-weight: bold;
    margin-bottom: 6px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  .book-author {
    font-size: 12px;
    opacity: 0.7;
  }
  .read-btn {
    margin-top: 5px;
    background-color: #1c5fad;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 4px 6px;
    font-size: 12px;
    cursor: pointer;
  }
  .read-btn:hover {
    background-color: #0d3b66;
  }
  nav.bottom-nav {
    position: fixed;
    bottom: 0;
    width: 100%;
    background: #e6f0ff;
    display: flex;
    justify-content: space-around;
    padding: 8px 0;
    box-shadow: 0 -2px 5px rgba(0,0,0,0.1);
    z-index: 1000;
  }
  nav.bottom-nav button {
    background: none;
    border: none;
    color: #0d3b66;
    font-size: 24px;
    cursor: pointer;
  }
  nav.bottom-nav button.active {
    color: #1c5fad;
  }
  .horizontal-scroll::-webkit-scrollbar {
    height: 6px;
  }
  .horizontal-scroll::-webkit-scrollbar-thumb {
    background: #1c5fad;
    border-radius: 3px;
  }

  /* واجهات ثانوية (Profile، Settings ...) */
  .overlay {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.4);
    z-index: 2000;
  }
  .overlay.open {
    display: block;
  }
  .modal {
    background: #ffffff;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 90%;
    max-width: 400px;
    border-radius: 10px;
    padding: 20px;
    box-sizing: border-box;
    z-index: 2100;
    box-shadow: 0 0 10px rgba(0,0,0,0.3);
  }
  .modal h2 {
    margin-top: 30px;
  }
</style>
</head>
<body>

<header>
  <div class="buttons">
    <button class="icon-btn" id="menuBtn" title="عرض القائمة"><span class="material-icons">menu</span></button>
    <button class="icon-btn" id="searchBtn" title="بحث"><span class="material-icons">search</span></button>
  </div>
  <div class="title" onclick="goHome()">مكتبتي</div>
  <div class="buttons">
    <button class="icon-btn" id="notificationsBtn" title="الإشعارات"><span class="material-icons">notifications</span></button>
    <button class="icon-btn" id="accountBtn" title="حسابي"><span class="material-icons">account_circle</span></button>
  </div>
</header>

<aside class="sidebar" id="sidebar">
  <button class="close-btn" onclick="closeSidebar()">✖</button>
  <h2>القائمة</h2>
  <ul>
    <li onclick="openModal('profileModal')">حسابي</li>
    <li onclick="openModal('settingsModal')">الإعدادات</li>
    <li onclick="toggleDarkMode()">الوضع الداكن/الفاتح</li>
    <li onclick="shareApp()">مشاركة التطبيق</li>
    <li onclick="contactUs()">تواصل معنا</li>
    <li onclick="aboutApp()">عن التطبيق</li>
  </ul>
</aside>

<main>
  <div class="banner" tabindex="0">
    "اقرأ لتتغير حياتك"
  </div>

  <section class="section">
    <div class="section-header">
      <span>أقسام الكتب</span>
      <button onclick="seeAllSections()">عرض المزيد</button>
    </div>
    <div class="horizontal-scroll" id="categoriesScroll">
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=علوم" alt="علوم"/>
        <div class="book-info"><div class="book-title">علوم</div></div>
        <button class="read-btn" onclick="readBook('book-science.pdf')">قراءة</button>
      </div>
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=أدب" alt="أدب"/>
        <div class="book-info"><div class="book-title">أدب</div></div>
        <button class="read-btn" onclick="readBook('book-literature.pdf')">قراءة</button>
      </div>
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=تاريخ" alt="تاريخ"/>
        <div class="book-info"><div class="book-title">تاريخ</div></div>
        <button class="read-btn" onclick="readBook('book-history.pdf')">قراءة</button>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="section-header">
      <span>كتب شائعة اليوم</span>
      <button onclick="seeMorePopular()">عرض المزيد</button>
    </div>
    <div class="horizontal-scroll" id="popularBooksScroll">
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=كتاب1" alt="كتاب 1"/>
        <div class="book-info"><div class="book-title">كتاب 1</div><div class="book-author">مؤلف 1</div></div>
        <button class="read-btn" onclick="readBook('book1.pdf')">قراءة</button>
      </div>
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=كتاب2" alt="كتاب 2"/>
        <div class="book-info"><div class="book-title">كتاب 2</div><div class="book-author">مؤلف 2</div></div>
        <button class="read-btn" onclick="readBook('book2.pdf')">قراءة</button>
      </div>
    </div>
  </section>
</main>

<nav class="bottom-nav">
  <button id="navHome" class="active" title="الرئيسية"><span class="material-icons">home</span></button>
  <button id="navCategories" title="الأقسام"><span class="material-icons">category</span></button>
  <button id="navFavorites" title="المفضلة"><span class="material-icons">favorite</span></button>
  <button id="navNotifications" title="الإشعارات"><span class="material-icons">notifications</span></button>
  <button id="navProfile" title="حسابي"><span class="material-icons">person</span></button>
</nav>

<!-- النوافذ المنبثقة للواجهات الثانوية -->
<div class="overlay" id="overlay"></div>

<div class="modal" id="profileModal">
  <button class="close-btn" onclick="closeModal('profileModal')">✖</button>
  <h2>حسابي</h2>
  <p>تفاصيل الحساب هنا...</p>
</div>

<div class="modal" id="settingsModal">
  <button class="close-btn" onclick="closeModal('settingsModal')">✖</button>
  <h2>الإعدادات</h2>
  <p>خيارات الإعدادات هنا...</p>
</div>

<script>
  const sidebar = document.getElementById('sidebar');
  const menuBtn = document.getElementById('menuBtn');
  const overlay = document.getElementById('overlay');

  menuBtn.addEventListener('click', () => { sidebar.classList.toggle('open'); });

  function closeSidebar() {
    sidebar.classList.remove('open');
  }

  function openModal(modalId) {
    document.getElementById(modalId).style.display = 'block';
    overlay.classList.add('open');
  }

  function closeModal(modalId) {
    document.getElementById(modalId).style.display = 'none';
    overlay.classList.remove('open');
  }

  overlay.addEventListener('click', () => {
    document.querySelectorAll('.modal').forEach(m => m.style.display='none');
    overlay.classList.remove('open');
  });

  // وظائف حقيقية للأزرار
  function goHome() { window.location.href = 'index.html'; }
  function toggleDarkMode() { alert('الوضع الداكن/الفاتح سيتم لاحقاً'); }
  function shareApp() { alert('مشاركة التطبيق: رابط + QR'); }
  function contactUs() { window.location.href = 'contact.html'; }
  function aboutApp() { window.location.href = 'about.html'; }
  function seeAllSections() { window.location.href = 'sections.html'; }
  function <!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>مكتبتي</title>
<!-- خط جديد للاسم -->
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@700&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet"/>
<style>
  body {
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: #ffffff;
    color: #0d3b66;
  }
  header, nav {
    background-color: #e6f0ff;
  }
  header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 15px;
    position: sticky;
    top: 0;
    z-index: 1000;
  }
  header .title {
    font-family: 'Cairo', sans-serif;
    font-size: 26px;
    cursor: pointer;
  }
  header .buttons {
    display: flex;
    gap: 15px;
  }
  button.icon-btn {
    background: none;
    border: none;
    color: #0d3b66;
    font-size: 22px;
    cursor: pointer;
  }
  button.icon-btn:hover {
    color: #1c5fad;
  }

  /* Sidebar */
  aside.sidebar {
    position: fixed;
    right: -300px;
    top: 0;
    width: 300px;
    height: 100%;
    background-color: #f0f4ff;
    overflow-y: auto;
    transition: right 0.3s ease-in-out;
    padding: 20px;
    box-sizing: border-box;
    z-index: 1500;
  }
  aside.sidebar.open {
    right: 0;
  }
  aside.sidebar h2 {
    margin-top: 30px;
  }
  aside.sidebar ul {
    list-style: none;
    padding: 0;
  }
  aside.sidebar ul li {
    margin: 15px 0;
    cursor: pointer;
    color: #0d3b66;
  }
  aside.sidebar ul li:hover {
    color: #1c5fad;
  }
  .close-btn {
    position: absolute;
    top: 10px;
    left: 10px;
    background: none;
    border: none;
    font-size: 22px;
    cursor: pointer;
    color: #0d3b66;
  }
  .close-btn:hover {
    color: #1c5fad;
  }

  main {
    padding: 15px;
    min-height: 80vh;
  }
  .banner {
    background: url('https://images.unsplash.com/photo-1524995997946-a1c2e315a42f?auto=format&fit=crop&w=800&q=80') center/cover no-repeat;
    height: 180px;
    border-radius: 10px;
    margin-bottom: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: bold;
    font-size: 20px;
    color: white;
    text-shadow: 0 0 5px black;
  }
  .section {
    margin-bottom: 25px;
  }
  .section-header {
    font-weight: bold;
    font-size: 18px;
    margin-bottom: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .section-header button {
    background: none;
    border: none;
    color: #1c5fad;
    cursor: pointer;
    font-size: 14px;
  }
  .horizontal-scroll {
    display: flex;
    overflow-x: auto;
    gap: 15px;
    padding-bottom: 10px;
  }
  .book-card {
    background-color: #e6f0ff;
    border-radius: 8px;
    width: 120px;
    flex-shrink: 0;
    cursor: pointer;
    text-align: center;
  }
  .book-card img {
    width: 100%;
    height: 160px;
    object-fit: cover;
    border-radius: 8px 8px 0 0;
  }
  .book-info {
    padding: 10px;
  }
  .book-title {
    font-family: 'Cairo', sans-serif;
    font-size: 14px;
    font-weight: bold;
    margin-bottom: 6px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  .book-author {
    font-size: 12px;
    opacity: 0.7;
  }
  .read-btn {
    margin-top: 5px;
    background-color: #1c5fad;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 4px 6px;
    font-size: 12px;
    cursor: pointer;
  }
  .read-btn:hover {
    background-color: #0d3b66;
  }
  nav.bottom-nav {
    position: fixed;
    bottom: 0;
    width: 100%;
    background: #e6f0ff;
    display: flex;
    justify-content: space-around;
    padding: 8px 0;
    box-shadow: 0 -2px 5px rgba(0,0,0,0.1);
    z-index: 1000;
  }
  nav.bottom-nav button {
    background: none;
    border: none;
    color: #0d3b66;
    font-size: 24px;
    cursor: pointer;
  }
  nav.bottom-nav button.active {
    color: #1c5fad;
  }
  .horizontal-scroll::-webkit-scrollbar {
    height: 6px;
  }
  .horizontal-scroll::-webkit-scrollbar-thumb {
    background: #1c5fad;
    border-radius: 3px;
  }

  /* واجهات ثانوية (Profile، Settings ...) */
  .overlay {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.4);
    z-index: 2000;
  }
  .overlay.open {
    display: block;
  }
  .modal {
    background: #ffffff;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 90%;
    max-width: 400px;
    border-radius: 10px;
    padding: 20px;
    box-sizing: border-box;
    z-index: 2100;
    box-shadow: 0 0 10px rgba(0,0,0,0.3);
  }
  .modal h2 {
    margin-top: 30px;
  }
</style>
</head>
<body>

<header>
  <div class="buttons">
    <button class="icon-btn" id="menuBtn" title="عرض القائمة"><span class="material-icons">menu</span></button>
    <button class="icon-btn" id="searchBtn" title="بحث"><span class="material-icons">search</span></button>
  </div>
  <div class="title" onclick="goHome()">مكتبتي</div>
  <div class="buttons">
    <button class="icon-btn" id="notificationsBtn" title="الإشعارات"><span class="material-icons">notifications</span></button>
    <button class="icon-btn" id="accountBtn" title="حسابي"><span class="material-icons">account_circle</span></button>
  </div>
</header>

<aside class="sidebar" id="sidebar">
  <button class="close-btn" onclick="closeSidebar()">✖</button>
  <h2>القائمة</h2>
  <ul>
    <li onclick="openModal('profileModal')">حسابي</li>
    <li onclick="openModal('settingsModal')">الإعدادات</li>
    <li onclick="toggleDarkMode()">الوضع الداكن/الفاتح</li>
    <li onclick="shareApp()">مشاركة التطبيق</li>
    <li onclick="contactUs()">تواصل معنا</li>
    <li onclick="aboutApp()">عن التطبيق</li>
  </ul>
</aside>

<main>
  <div class="banner" tabindex="0">
    "اقرأ لتتغير حياتك"
  </div>

  <section class="section">
    <div class="section-header">
      <span>أقسام الكتب</span>
      <button onclick="seeAllSections()">عرض المزيد</button>
    </div>
    <div class="horizontal-scroll" id="categoriesScroll">
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=علوم" alt="علوم"/>
        <div class="book-info"><div class="book-title">علوم</div></div>
        <button class="read-btn" onclick="readBook('book-science.pdf')">قراءة</button>
      </div>
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=أدب" alt="أدب"/>
        <div class="book-info"><div class="book-title">أدب</div></div>
        <button class="read-btn" onclick="readBook('book-literature.pdf')">قراءة</button>
      </div>
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=تاريخ" alt="تاريخ"/>
        <div class="book-info"><div class="book-title">تاريخ</div></div>
        <button class="read-btn" onclick="readBook('book-history.pdf')">قراءة</button>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="section-header">
      <span>كتب شائعة اليوم</span>
      <button onclick="seeMorePopular()">عرض المزيد</button>
    </div>
    <div class="horizontal-scroll" id="popularBooksScroll">
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=كتاب1" alt="كتاب 1"/>
        <div class="book-info"><div class="book-title">كتاب 1</div><div class="book-author">مؤلف 1</div></div>
        <button class="read-btn" onclick="readBook('book1.pdf')">قراءة</button>
      </div>
      <div class="book-card" tabindex="0">
        <img src="https://via.placeholder.com/120x160?text=كتاب2" alt="كتاب 2"/>
        <div class="book-info"><div class="book-title">كتاب 2</div><div class="book-author">مؤلف 2</div></div>
        <button class="read-btn" onclick="readBook('book2.pdf')">قراءة</button>
      </div>
    </div>
  </section>
</main>

<nav class="bottom-nav">
  <button id="navHome" class="active" title="الرئيسية"><span class="material-icons">home</span></button>
  <button id="navCategories" title="الأقسام"><span class="material-icons">category</span></button>
  <button id="navFavorites" title="المفضلة"><span class="material-icons">favorite</span></button>
  <button id="navNotifications" title="الإشعارات"><span class="material-icons">notifications</span></button>
  <button id="navProfile" title="حسابي"><span class="material-icons">person</span></button>
</nav>

<!-- النوافذ المنبثقة للواجهات الثانوية -->
<div class="overlay" id="overlay"></div>

<div class="modal" id="profileModal">
  <button class="close-btn" onclick="closeModal('profileModal')">✖</button>
  <h2>حسابي</h2>
  <p>تفاصيل الحساب هنا...</p>
</div>

<div class="modal" id="settingsModal">
  <button class="close-btn" onclick="closeModal('settingsModal')">✖</button>
  <h2>الإعدادات</h2>
  <p>خيارات الإعدادات هنا...</p>
</div>

<script>
  const sidebar = document.getElementById('sidebar');
  const menuBtn = document.getElementById('menuBtn');
  const overlay = document.getElementById('overlay');

  menuBtn.addEventListener('click', () => { sidebar.classList.toggle('open'); });

  function closeSidebar() {
    sidebar.classList.remove('open');
  }

  function openModal(modalId) {
    document.getElementById(modalId).style.display = 'block';
    overlay.classList.add('open');
  }

  function closeModal(modalId) {
    document.getElementById(modalId).style.display = 'none';
    overlay.classList.remove('open');
  }

  overlay.addEventListener('click', () => {
    document.querySelectorAll('.modal').forEach(m => m.style.display='none');
    overlay.classList.remove('open');
  });

  // وظائف حقيقية للأزرار
  function goHome() { window.location.href = 'index.html'; }
  function toggleDarkMode() { alert('الوضع الداكن/الفاتح سيتم لاحقاً'); }
  function shareApp() { alert('مشاركة التطبيق: رابط + QR'); }
  function contactUs() { window.location.href = 'contact.html'; }
  function aboutApp() { window.location.href = 'about.html'; }
  function seeAllSections() { window.location.href = 'sections.html'; }
  function seeMorePopular() { window.location.href = 'popular.html'; }

  function readBook(file) { window.open(file, '_blank'); }

  // شريط التنقل السفلي
  const navButtons = document.querySelectorAll('nav.bottom-nav button');
  navButtons.forEach(btn => {
    btn.addEventListener('click', () => {
      navButtons.forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
      switch(btn.id) {
        case 'navHome': goHome(); break;
        case 'navCategories': window.location.href='sections.html'; break;
        case 'navFavorites': window.location.href='favorites.html'; break;
        case 'navNotifications': window.location.href='notifications.html'; break;
        case 'navProfile': openModal('profileModal'); break;
      }
    });
  });
</script>
</body>
</html>() { window.location.href = 'popular.html'; }

  function readBook(file) { window.open(file, '_blank'); }

  // شريط التنقل السفلي
  const navButtons = document.querySelectorAll('nav.bottom-nav button');
  navButtons.forEach(btn => {
    btn.addEventListener('click', () => {
      navButtons.forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
      switch(btn.id) {
        case 'navHome': goHome(); break;
        case 'navCategories': window.location.href='sections.html'; break;
        case 'navFavorites': window.location.href='favorites.html'; break;
        case 'navNotifications': window.location.href='notifications.html'; break;
        case 'navProfile': openModal('profileModal'); break;
      }
    });
  });
</script>
</body>
</html>
