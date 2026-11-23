# رفيق السائق · Rafiq Driver — مشروع تطبيق أندرويد

التطبيق صفحة ويب (www/index.html) مغلّفة بـ Capacitor لتصبح تطبيق أندرويد.

## الطريقة 1 — الأسهل: بناء APK على GitHub (بلا تثبيت شيء على حاسوبك)
1. أنشئ حسابًا على github.com ثم مستودعًا جديدًا (Repository) فارغًا.
2. ارفع كل محتويات هذا المجلد إليه (Upload files)، مع المجلد المخفي `.github`.
3. افتح تبويب **Actions** ← **Build Android APK** ← **Run workflow**.
4. بعد 5 إلى 8 دقائق افتح التشغيل المكتمل ونزّل الملف **rafiq-driver-apk** من قسم Artifacts (ملف zip بداخله app-debug.apk).
5. انقل app-debug.apk إلى الهاتف وثبّته (فعّل «التثبيت من مصادر غير معروفة»).

## الطريقة 2 — بلا كود: PWABuilder
1. استضف مجلد `www` على أي موقع HTTPS (مثل GitHub Pages أو Netlify).
2. افتح pwabuilder.com وأدخل الرابط ثم اختر Android ونزّل الحزمة.

## الطريقة 3 — Android Studio
npm install ← npx cap add android ← npx @capacitor/assets generate --android ← أضف صلاحيات الموقع
(ACCESS_FINE_LOCATION وACCESS_COARSE_LOCATION) إلى AndroidManifest.xml ← npx cap sync android ← npx cap open android ← Build ▸ Build APK.

## ملاحظات
- الملف الناتج نسخة تجريبية (debug) صالحة للتثبيت المباشر. للنشر على Google Play يلزم توقيع نسخة release.
- يعمل التطبيق دون إنترنت. البيانات تُحفظ على الهاتف فقط.
- GPS: يطلب التطبيق إذن الموقع عند أول تشغيل لعدّاد السرعة.
- لتحديث البيانات (قطارات، سرعات...) عدّل www/index.html ثم أعد البناء.
