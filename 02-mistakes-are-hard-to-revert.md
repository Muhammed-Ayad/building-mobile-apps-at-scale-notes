# التحدي الثاني من كتاب Building Mobile Apps at Scale

🔗 [البوست على LinkedIn](https://ae.linkedin.com/posts/mohamedayaddev_flutter-mobiledevelopment-softwareengineering-activity-7525885213210521602-1BT6)

---

تخيل إنك اكتشفت Bug خطير في تطبيقك بعد ما وصل لآلاف المستخدمين. صلحت المشكلة ونشرت Release جديدة لكن جزء من المستخدمين لسه بيستخدم النسخة القديمة!

دي واحدة من تحديات Mobile Development: إصلاح المشاكل بعد النشر مش دايما سهل.

Backend vs Mobile
في الـBackend تقدر تصلح المشكلة وتنشر التعديل على السيرفر والمستخدم يستفيد منه من غير Update.

لكن في Mobile Apps التطبيق بيتوزع على أجهزة المستخدمين عشان توصلهم بتعديل جديد محتاج Release جديدة والمستخدم لازم يحدث التطبيق بنفسه.

وبالتالي ممكن تلاقي أكتر من App Version شغالة في نفس الوقت وده بيخلي توافق الـBackend مع الإصدارات القديمة حاجه مهمه 

ازاي نقلل الحاجه دي ؟

Testing
استخدام Automated Testing وManual Testing وBeta Testing بيساعدنا نكتشف المشاكل قبل ما توصل لكل المستخدمين.

Gradual Rollouts
بدل ما ننشر التحديث للكل مرة واحده ممكن تبدأ بنسبة صغيرة وتراقب الـCrashes والـPerformance ثم تزود النسبة تدريجيا
ولو ظهرت مشكلة تقدر توقف الـRollout عشان تمنع مستخدمين إضافيين من استلام الإصدار لكن المستخدمين اللي ثبتوه مش هيرجعوا تلقائيا للإصدار السابق وهيحتاجوا حل منفصل.

Feature Flags
تقدر تتحكم في تشغيل أو إيقاف Feature من الـServer من غير Release جديدة
مثلا لو New Checkout Flow فيه مشكلة ممكن تعطله وترجع للـOld Checkout
لكن لازم الكود القديم يكون موجود في التطبيق والـBackend والـAPIs والـData يفضلوا متوافقين معاه ، الـFeature Flags مش ضمان لوحدها لرجوع آمن.

Shorebird Code Push (Flutter)
Shorebird بتسمح لك تبعت Patches لتعديلات Dart Code بعد نشر التطبيق، من غير Store Release جديدة.
الـPatch بتتحمل في الخلفية، وتتطبق عند تشغيل التطبيق مرة تانية.

لكنها مش بتقدر تحدث:
Native Code زي Kotlin وSwift
Assets زي Images وFonts وJSON
Permissions أو Build Files
Flutter Engine أو إصدار Flutter نفسه
ولو Plugin محتاج Native Code جديد لازم يكون موجود بالفعل في النسخة المثبتة وكمان كل Patch مرتبطة بـRelease معينة
ولو الـPatch نفسها سببت مشكلة، Shorebird بتوفر Patch Rollback للرجوع للـPatch السابقة أو الـBase Release.
لكن دعم التراجع الكامل بيعتمد على إصدار Flutter
 بعض الإصدارات القديمة لا تدعمه.

Forced Upgrading
لو إصدار قديم فيه مشكلة خطيرة ممكن تستخدم Version Check عشان تقارن إصدار التطبيق بالـMinimum Supported Version، وتطلب من المستخدم التحديث قبل المتابعة
لكن لازم تستخدم الحل ده بحذر لأنه ممكن يأثر على تجربة المستخدم.

في بعض الاسئله اللي ممكن تسالها لنفس قبل ما تطلع بنسخه جديده
هل أقدر أعطل Feature لو ظهرت فيها مشكلة؟
هل أقدر أصلح Dart Code باستخدام Shorebird وأتراجع عن الـPatch لو لزم الأمر؟
هل الـBackend متوافق مع الإصدارات القديمة؟

في Mobile Development، الـRelease مش مجرد Build وتنشره.
كتابة Code شغال مهمة، لكن الأهم كمان إنك تكون مستعد تتعامل مع المشاكل بعد النشر.

#Flutter #MobileDevelopment #SoftwareEngineering #Shorebird #BuildingMobileAppsAtScale
