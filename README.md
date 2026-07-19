# 🚀 IndexNow URL Submitter | ابزار ایندکس لینک با IndexNow

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"/>
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3"/>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript"/>
  <img src="https://img.shields.io/badge/IndexedDB-003545?style=for-the-badge&logo=indexeddb&logoColor=white" alt="IndexedDB"/>
  <img src="https://img.shields.io/badge/PWA-5A0FC8?style=for-the-badge&logo=pwa&logoColor=white" alt="PWA"/>
  <img src="https://img.shields.io/badge/Service_Worker-FFD700?style=for-the-badge&logo=javascript&logoColor=black" alt="Service Worker"/>
</p>

<p align="center">
  <b>🇮🇷 فارسی</b> &nbsp;|&nbsp; <b>🇬🇧 English</b>
</p>

---

## 🇮🇷 فارسی

### 📖 درباره پروژه
این یک ابزار **کاملاً کلاینت‌ساید (Client‑Side)** و رایگان برای **ارسال لینک به موتورهای جستجو با استفاده از پروتکل IndexNow** است.  
با استفاده از این ابزار، وب‌مسترها می‌توانند تنها با یک کلیک، لینک صفحات جدید یا به‌روزرسانی‌شده خود را به **بینگ (Bing)، یاندکس (Yandex)، سِزنام (Seznam) و نِیور (Naver)** اطلاع دهند تا سریع‌تر ایندکس شوند.

ویژگی برجسته این ابزار **شفافیت کامل درباره محدودیت‌های مرورگر** است و کاربر را گام‌به‌گام برای ایجاد فایل `key.txt` و اثبات مالکیت دامنه راهنمایی می‌کند. برخلاف بسیاری از ابزارهای مشابه که «تیک سبز دروغین» نشان می‌دهند، این ابزار دقیقاً مشخص می‌کند که چه زمانی امکان تأیید نتیجه وجود ندارد.

### ✨ امکانات
- **راهنمای گام‌به‌گام هوشمند:** تولید خودکار کلید IndexNow، دانلود `key.txt` و تست وجود فایل روی دامنه.
- **ارسال تکی و گروهی لینک:** پشتیبانی از ارسال ۱ تا ۱۰۰ لینک با تأخیر تصادفی (شبیه‌سازی رفتار انسانی).
- **پیش‌بررسی صفحه:** تشخیص وضعیت HTTP، تگ `noindex`، `canonical` و هدرهای مهم.
- **بررسی robots.txt و sitemap:** آنالیز اولیه وضعیت دامنه.
- **تاریخچه در IndexedDB:** ذخیره تمام ارسال‌ها با قابلیت خروجی CSV/JSON و ارسال مجدد.
- **رابط کاربری دوزبانه (فارسی/انگلیسی)** و تم تاریک/روشن (ذخیره در localStorage).
- **PWA:** قابلیت نصب روی دسکتاپ و موبایل (Add to Home Screen).
- **بدون نیاز به سرور:** تمام پردازش‌ها در مرورگر کاربر انجام می‌شود و روی هر هاست اشتراکی ساده قابل اجراست.

### 🛠️ تکنولوژی‌ها و روش ساخت
- **HTML5 / CSS3 / JavaScript (Vanilla)** – بدون هیچ فریم‌ورک یا کتابخانه خارجی.
- **IndexedDB** – ذخیره‌سازی کلید IndexNow و تاریخچه (به جای localStorage محدود).
- **Service Worker** – کش کردن دارایی‌ها برای عملکرد آفلاین نسبی و نصب PWA.
- **Fetch API (mode: no‑cors) و sendBeacon** – ارسال درخواست به `api.indexnow.org` با آگاهی از محدودیت‌های CORS مرورگر.
- **طراحی واکنش‌گرا (Responsive)** – استفاده از CSS Variables، Flexbox و Grid برای نمایش در تمام دستگاه‌ها.

### ⚙️ روش کار و عملکرد
1. کاربر کلید IndexNow را دریافت می‌کند (تولید خودکار در IndexedDB).
2. فایل `key.txt` را دانلود کرده و در ریشه دامنه خود آپلود می‌کند.
3. ابزار سعی می‌کند وجود فایل را از طریق درخواست HEAD بررسی کند (در صورت مجاز بودن CORS).
4. پس از تأیید (یا با آگاهی از محدودیت CORS) لینک/لینک‌ها با یک درخواست POST به `api.indexnow.org` ارسال می‌شوند.
5. نتیجه به کاربر نمایش داده می‌شود و در تاریخچه ثبت می‌گردد.

> ⚠️ به دلیل محدودیت CORS مرورگر، **وضعیت واقعی پاسخ (Status Code) قابل خواندن نیست**. به‌همین دلیل ابزار صریحاً اعلام می‌کند که تنها در صورتی لینک ایندکس می‌شود که فایل `key.txt` به‌درستی روی دامنه قرار گرفته باشد. این رویکرد شفاف، ابزار را از نمونه‌های «دروغین» متمایز می‌کند.

### 🔗 لینک سازنده
این پروژه توسط **[IntellSoft](https://intellsoft.ir) – نرم‌افزارهای هوشمند** توسعه داده شده است.  
برای مشاهده نسخه آنلاین و اطلاعات بیشتر به [intellsoft.ir](https://intellsoft.ir) مراجعه کنید.

---

## 🇬🇧 English

### 📖 About
A fully **client‑side**, free tool to submit URLs to search engines using the **IndexNow protocol**.  
Webmasters can instantly notify **Bing, Yandex, Seznam & Naver** about new or updated pages to speed up indexing.

The key differentiator is **honest transparency** about browser limitations – it will never show a fake “success” message. Users are guided step‑by‑step to create and validate the `key.txt` file, ensuring a real submission whenever possible.

### ✨ Features
- **Smart step‑by‑step wizard:** automatic key generation, `key.txt` download, and live verification on the domain.
- **Single & batch URL submission:** 1 to 100 URLs with random delays (human‑like behavior).
- **Pre‑check page analysis:** HTTP status, `noindex`, `canonical`, important headers.
- **robots.txt & sitemap checker:** quick domain status.
- **IndexedDB history:** store all submissions, export to CSV/JSON, re‑submit with one click.
- **Bilingual UI (Persian/English)** & dark/light theme (localStorage).
- **PWA:** installable on desktop & mobile.
- **Zero server dependency:** runs entirely in the browser, compatible with any basic shared hosting.

### 🛠️ Technologies & Architecture
- **Vanilla HTML, CSS, JavaScript** – no frameworks, no CDN.
- **IndexedDB** – persistent storage for the IndexNow key and history.
- **Service Worker** – basic caching for offline support and PWA installation.
- **Fetch API (no‑cors mode) & sendBeacon** – communicate with `api.indexnow.org` while respecting browser CORS restrictions.
- **Responsive design** – CSS variables, Flexbox, Grid.

### ⚙️ How It Works
1. The user gets a unique IndexNow key (auto‑generated and stored in IndexedDB).
2. They download `key.txt` and upload it to their domain root.
3. The tool tries to verify the file via a HEAD request (CORS permitting).
4. After verification (or with an explicit warning about CORS), the URL(s) are POSTed to `api.indexnow.org`.
5. Feedback is displayed and saved in the history.

> ⚠️ Due to browser CORS policy, the real HTTP response status cannot be read. The tool honestly informs the user that indexing will only succeed if `key.txt` is correctly placed on the domain. No fake green checkmarks.

### 🔗 Creator
Developed by **[IntellSoft](https://intellsoft.ir)** – Smart Software Solutions.  
Visit [intellsoft.ir](https://intellsoft.ir) for more tools and plugins.

---

## 📂 How to Use
1. Clone or download the repository.
2. Open `index.html` directly in your browser (no build step required).
3. Follow the on‑screen wizard to generate your key and start submitting URLs.

## 📄 License
MIT – feel free to use, modify and distribute.

---

<p align="center">
  Made with ❤️ by <a href="https://intellsoft.ir" target="_blank">IntellSoft</a>
</p>
