<div dir="rtl">

# التحدي الرابع من كتاب <span dir="ltr">Building Mobile Apps at Scale</span>: الروابط العميقة <br><span dir="ltr">(Deep Links)</span>

🔗 [البوست على LinkedIn](https://www.linkedin.com/posts/mohamedayaddev_flutter-flutterdevelopment-mobiledevelopment-share-7530271911063277570-n_1F/)

---

تخيل إن عندك تطبيق متجر إلكتروني وشخص بعتلك رابط منتج

<div dir="ltr">

```text
https: mystore.com/products/123
```

</div>

لما تضغط عليه المفروض التطبيق يفتح مباشرة صفحة المنتج رقم 123 مش الصفحة الرئيسية

**ده مفهوم Deep Linking: الوصول لصفحة أو محتوى محدد داخل التطبيق من خلال رابط**

لكن تنفيذه مش مجرد استقبال URL وفتح شاشة

فيه تحديات لازم نفكر فيها أثناء تصميم الـNavigation Architecture

## 1. التوافق مع الروابط القديمة <span dir="ltr">(Backward Compatibility)</span>

بعد نشر التطبيق المستخدمين ممكن يشاركوا روابط لصفحات معينة

لكن إيه اللي يحصل لو غيرت نظام الـNavigation أو شكل الـURLs؟

مينفعش الروابط القديمة تتعطل لمجرد إنك غيرت الـRouting Structure

علشان كده لازم تحافظ على الروابط القديمة أو توفر طريقة لتحويلها للمسارات الجديدة

## 2. التعامل مع حالة التطبيق <span dir="ltr">(App State)</span>

لازم تحدد سلوك التطبيق عند استقبال رابط في حالتين:

- Cold Start: التطبيق مقفول والرابط بيبدأ تشغيله ويفتح الصفحة المطلوبة
- Warm Start: التطبيق شغال بالفعل فلازم يتعامل مع الرابط وينقل المستخدم للوجهة المطلوبة

**كمان لازم تراعي حالة تسجيل الدخول**

مثلا، لو الصفحة محتاجة Login وجه المستخدم لتسجيل الدخول وبعدها رجعه للصفحة اللي كان عايز يوصل لها

## 3. اختلاف التنفيذ بين المنصات <span dir="ltr">(Platform Differences)</span>

رغم إن Flutter بيوحد معظم كود التطبيق إعداد استقبال الروابط بيختلف بين Android وiOS.

- على Android: بنستخدم Android App Links لربط روابط HTTPS بالتطبيق مع التحقق من الدومين عن طريق assetlinks.json.
- على iOS: بنستخدم Universal Links مع إعداد Associated Domains والتحقق من الدومين عن طريق apple-app-site-association

وفيه كمان Custom URL Schemes زي: myApp://products/123

لكنها مختلفة عن App Links وUniversal Links لأنها مش بتوفر نفس التحقق من ملكية الدومين، وممكن تطبيق تاني يسجل نفس الـScheme

## 4. التخطيط من البداية <span dir="ltr">(Plan Ahead)</span>

تأجيل التفكير في Deep Linking لحد ما التطبيق يكبر ممكن يضطرك لتغييرات كبيرة في الـNavigation Architecture

**الأفضل تحدد من البداية:**

- شكل الـURLs
- الصفحات المتاحة من خارج التطبيق
- سلوك التطبيق عند استقبال رابط
- التعامل مع تسجيل الدخول وحالة التطبيق

**Android App Links – Flutter Cookbook**  
https://lnkd.in/eHDMxBxe

**iOS Universal Links – Flutter Cookbook**  
https://lnkd.in/eG7W7JYs

**Flutter Navigation and Routing**  
https://lnkd.in/ezZDgMyN

#Flutter #FlutterDevelopment #MobileDevelopment #DeepLinking #BuildingInPublic

</div>
