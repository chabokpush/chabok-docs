---
id: gradle-setup
title: نصب چابک
layout: android
permalink: android/gradle-setup.html
prev: firebasehtml
next: application-class.html
---

### افزودن کتابخانه

کتابخانه چابک از طریق `jcenter` در دسترس است. برای این منظور ابتدا در فایل `gradle` اصلی پروژه، `jcenter` را بعنوان `repository` مطابق قطعه کد زیر اضافه نمایید:

```javascript
buildscript {
  repositories {
    jcenter()
  }
}
  
```

> `نکته :` به علت محدودیت‌‌های اندروید ۸ به بالا دقت کنید حتما مطابق جدول زیر تنظیمات نسخه‌ها را بدرستی انجام دهید.  در صورت رعایت نکردن نسخه‌های ذکر شده در جدول زیر هنگامی که اپلیکیشن **kill** شده باشد به هنگام دریافت نوتیفیکیشن با خطا مواجه خواهد شد.

<table dir="ltr">
    <thead>
    <tr align="center">
        <th>buildTools</th>
        <th>compileSdk</th>
        <th>targetSdk</th>
        <th>googlePlayServices</th>
    </tr>
    </thead>
    <tbody>
    <tr align="center">
        <td>25.x.x</td>
        <td>25</td>
        <td>&gt;= 23</td>
        <td>&gt;= 9.6.0</td>
    </tr>
    <tr align="center">
        <td>26.x.x</td>
        <td>26</td>
        <td>&gt;= 23</td>
        <td>&gt;= 9.6.0</td>
    </tr>
    <tr align="center">
        <td>27.x.x</td>
        <td>27</td>
        <td>&gt;= 23</td>
        <td>&gt;= 10.2.1</td>
    </tr>
    </tbody>
</table>

سپس فایل `build.gradle` در مسیر app را بازکرده و در بخش `dependencies` خط زیر را اضافه نمایید:

```javascript
dependencies {
    compile 'me.leolin:ShortcutBadger:1.1.18@aar'
    compile 'com.adpdigital.push:chabok-lib-VERSION'
}
```

> `نکته`: دقت داشته باشید که همیشه از جدیدترین نسخه **ShortcutBadger** استفاده کنید. برای اطلاع از آخرین نسخه می‌توانید به [این لینک](https://github.com/leolin310148/ShortcutBadger) مراجعه نمایید. همچنین با توجه به حجم زیاد مجوزهای نمایش نشان (**Badge**) روی آیکون اپ،‌ می‌توانید از [این قسمت](https://doc.chabokpush.com/android/features.html#برداشتن-مجوزهای-غیر-ضروری-برای-نمایش-نشان-badge-روی-آیکون) هر کدام از آن‌ها را با اختیار خودتان بردارید. 

> `نکته`: برای اینکه نسخه کتابخانه‌ای که استفاده می‌کنید همواره آخرین نسخه
> باشد، می‌توانید به جای ‌VERSION از + استفاده نمایید.

آخرین نسخه فایل کتابخانه چابک از  [اینجا](https://bintray.com/bintray/jcenter?filterByPkgName=com.adpdigital.push) قابل دسترس می‌باشد.
در انتها گزینه سینک را بزنید.

> `نکته`: برای استفاده از سرویس جی‌سی‌ام گوگل لازم است خط زیر نیز در بخش
> `dependencies`  اضافه شود:

```javascript
dependencies {
    compile "com.google.android.gms:play-services-gcm:10.2.6" 
}
```

### کتابخانه با قابلیت مکان‌یابی

 چابک دارای دو کتابخانه استاندارد و با قابلیت مکان‌یابی می‌باشد. درصورتی که در برنامه خود نیاز به استفاده از موقعیت مکانی کاربر دارید لازم است از کتابخانه chabok-lib-geo-VERSION استفاده نمایید. 
 باتوجه به اینکه در این کتابخانه از سرویس فیوز گوگل استفاده شده است لذا لازم است تا تغییرات زیر نیز در قسمت ‌‌‌`dependencies` اعمال شود:
 
 ```javascript
dependencies {
   compile 'com.google.android.gms:play-services-location:10.2.6'
   compile 'com.adpdigital.push:chabok-lib-geo-VERSION'

}  
```
