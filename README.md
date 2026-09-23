# درع الغابة v4.3.1 — منظومة إدارة حرائق الغابات

## المكونات
- `index.html` : بوابة الدخول (Firebase Auth)
- `ops.html`   : غرفة العمليات (خريطة تفاعلية + NASA FIRMS + الطقس)
- `manifest.json` / `sw.js` : PWA
- `assets/`    : الأيقونات

## حساب دخول تجريبي
- demo@forest.gov.sy / demo123

## روابط مهمة
- Firebase Console: https://console.firebase.google.com/project/forest-shield-syria
- المستودع: https://github.com/USERNAME/forest-shield
- الرابط المباشر: https://USERNAME.github.io/forest-shield/

## خطوات التشغيل
1. ارفع المجلد كاملاً إلى Firebase Hosting أو GitHub Pages.
2. فعّل Email/Password في Firebase Authentication.
3. فعّل Firestore (نمط الإنتاج) مع القواعد المقترحة أدناه.

## قواعد Firestore المقترحة
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null;
    }
  }
}
```

## التقنيات
- Leaflet 1.9.4 (الخرائط)
- Firebase 10.12 (Auth + Firestore)
- Open-Meteo API (الطقس)
- NASA FIRMS API (حرائق الأقمار)
- OSRM (المسارات)
