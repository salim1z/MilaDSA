<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>المديرية الولائية للفلاحة - DSA</title>
  <style>
    body {
      margin: 0;
      font-family: "Cairo", sans-serif;
      background: #f9f9f9;
      color: #333;
      line-height: 1.6;
    }

    header {
      background: #2e7d32;
      color: #fff;
      padding: 15px 20px;
      text-align: center;
      position: sticky;
      top: 0;
      z-index: 1000;
    }

    header h1 {
      margin: 0;
      font-size: 26px;
    }

    nav {
      margin-top: 10px;
    }

    nav a {
      color: #fff;
      margin: 0 10px;
      text-decoration: none;
      font-weight: bold;
      transition: color 0.3s;
    }

    nav a:hover {
      color: #ffeb3b;
    }

    .slider {
      position: relative;
      height: 60vh;
      overflow: hidden;
    }

    .slides {
      display: flex;
      width: 400%;
      height: 100%;
      animation: slide 16s infinite;
    }

    .slides img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    @keyframes slide {
      0% { transform: translateX(0); }
      25% { transform: translateX(-100%); }
      50% { transform: translateX(-200%); }
      75% { transform: translateX(-300%); }
      100% { transform: translateX(0); }
    }

    section {
      padding: 40px 20px;
      text-align: center;
    }

    section h2 {
      color: #2e7d32;
      margin-bottom: 20px;
    }

    .btn {
      display: inline-block;
      padding: 10px 20px;
      background: #2e7d32;
      color: #fff;
      text-decoration: none;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: 0.3s;
    }

    .btn:hover {
      background: #1b5e20;
    }

    form {
      max-width: 500px;
      margin: auto;
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 6px rgba(0,0,0,0.1);
      text-align: right;
    }

    form input {
      width: 100%;
      padding: 10px;
      margin: 8px 0;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    footer {
      background: #2e7d32;
      color: #fff;
      text-align: center;
      padding: 15px;
      margin-top: 40px;
    }
  </style>
</head>
<body>

<header>
  <h1>المديرية الولائية للفلاحة - DSA</h1>
  <nav>
    <a href="#home">الرئيسية</a>
    <a href="#about"></a>
    <a href="#events">التظاهرات</a>
    <a href="#register">التسجيل</a>
    <a href="#contact">اتصل بنا</a>
  </nav>
</header>

<div class="slider" id="home">
  <div class="slides">
    <img src="https://upload.wikimedia.org/wikipedia/commons/7/70/Wheat_close-up.JPG" alt="قمح">
    <img src="https://upload.wikimedia.org/wikipedia/commons/3/35/Barley_field.jpg" alt="شعير">
    <img src="https://upload.wikimedia.org/wikipedia/commons/f/f5/Maize_-_corn.jpg" alt="ذرة">
    <img src="https://upload.wikimedia.org/wikipedia/commons/1/1a/Cows_in_field.jpg" alt="تربية الأبقار">
  </div>
</div>

<section id="about">
  <h2>من نحن</h2>
  <p>المديرية الولائية للفلاحة (DSA) تسهر على تطوير القطاع الفلاحي عبر دعم الفلاحين وتنظيم التظاهرات والمعارض الفلاحية لتبادل الخبرات وتعزيز الإنتاج الوطني.</p>
</section>

<section id="events">
  <h2>التظاهرات الفلاحية</h2>
  <p>تنظم المديرية العديد من المعارض والملتقيات في مجالات القمح، الشعير، الذرة، وتربية الأبقار، وذلك لتشجيع الاستثمار وتبادل الخبرات بين الفلاحين.</p>
  <a href="#register" class="btn">سجل الآن</a>
</section>

<section id="register">
  <h2>إنشاء حساب للتسجيل في التظاهرات</h2>
  <form name="submit-to-google-sheet">
    <input type="text" name="firstname" placeholder="الاسم" required>
    <input type="text" name="lastname" placeholder="اللقب" required>
    <input type="email" name="email" placeholder="البريد الإلكتروني" required>
    <input type="text" name="phone" placeholder="رقم الهاتف" required>
    <input type="date" name="birthdate" required>

    <input type="password" name="password" placeholder="كلمة المرور" required>
    <input type="password" name="confirm_password" placeholder="تأكيد كلمة المرور" required>

    <button type="submit" class="btn">إنشاء حساب</button>
    <p id="msg"></p>
  </form>
</section>

<section id="contact">
  <h2>اتصل بنا</h2>
  <p>📍 العنوان: مقر المديرية الولائية للفلاحة</p>
  <p>📞 الهاتف: 031484828</p>
  <p>📧 البريد: contact@dsa.dz</p>
</section>

<footer>
  <p>© 2025 - المديرية الولائية للفلاحة - جميع الحقوق محفوظة</p>
</footer>

<script>
  const scriptURL = 'https://script.google.com/macros/s/AKfycbzRtwoDKDQi5Fg40UBjv0J6HxE9iiE9IxeorJ0fYqrxkLksioMZgaglmUzFsMiuRW3KEw/exec' // ضع رابط Google Script هنا
  const form = document.forms['submit-to-google-sheet']
  const msg = document.getElementById("msg")

  form.addEventListener('submit', e => {
    e.preventDefault()

    const password = form.password.value
    const confirmPassword = form.confirm_password.value
    if (password !== confirmPassword) {
      msg.innerHTML = "⚠️ كلمتا المرور غير متطابقتين"
      return
    }

    fetch(scriptURL, { method: 'POST', body: new FormData(form)})
      .then(response => {
        msg.innerHTML = "✅ تم إنشاء الحساب بنجاح"
        form.reset()
        setTimeout(()=> msg.innerHTML="", 5000)
      })
      .catch(error => console.error('Error!', error.message))
  })
</script>

</body>
</html># madr.gov
