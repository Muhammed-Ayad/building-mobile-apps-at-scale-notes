# التحدي الثالث من كتاب Building Mobile Apps at Scale

🔗 [البوست على LinkedIn](https://ae.linkedin.com/posts/mohamedayaddev_flutter-mobiledevelopment-softwareengineering-activity-7527711622329516032-GvOq)

---

تخيل إنك نشرت Version جديدة من تطبيقك وكل حاجة شغالة بشكل تمام
بعد فترة الـBackend عمل تعديل في API وفجأة بدأت تظهر مشاكل عند بعض المستخدمين
اكتشفت إنهم لسه بيستخدموا إصدارات قديمة من التطبيق

وده تحدي مهم في Mobile Development:
مش كل المستخدمين بيستخدموا أحدث Version من التطبيق

ليه الإصدارات القديمة بتفضل موجودة؟
لأسباب مختلفة زي:
بعض المستخدمين بيعطلوا Automatic Updates
أجهزة قديمة مش بتدعم الإصدارات الجديده
بعض المستخدمين ببساطة مش بيهتموا بالتحديثات

وده معناه إن أي تغيير في الـBackend ممكن يأثر على تطبيقات لسه مستخدمة حتى لو الإصدار الجديد شغال بشكل سليم

مثال عملي
افترض إن الـAPI بترجع:
{   "name": "Mohamed",   "phone": "01000000000" }
وفي Flutter Model عندك:
final String phone;

بعد فترة، الـBackend قرر يسمح إن phone تكون null:
{   "name": "Mohamed",   "phone": null }

الإصدار الجديد ممكن يكون اتعامل مع التغيير باستخدام ?String ، لكن الإصدار القديم لسه متوقع String

النتيجة؟ ممكن يحصل Runtime Type Error أثناء Parsing
تغيير بسيط بالنسبة للإصدار الجديد ممكن يكسر إصدارات قديمة عند المستخدمين

إزاي نتعامل مع المشكلة دي؟
فيه شوية حاجات ممكن تساعدنا:

1. الاتفاق على عقد واضح للـAPI (API Contracts)
لازم فريق الـMobile والـBackend يتفقوا على أسماء الـFields وأنواع البيانات وهل الحقول تقبل null أو اختيارية
ممكن نستخدم أدوات زي GraphQL وApache Thrift أو Code Generation من API Schemas
 وفي Flutter
 json_serializable 
بيساعد في توليد كود Parsing لكنه لوحده مش بيضمن Backward Compatibility

2. التخطيط للتغييرات  (Breaking Changes)
لو هتغير Endpoint أو شكل Response خطط للتغيير مسبقا وممكن تسيب القديم شغال بالتوازي لحد ما المستخدمين ينتقلوا للجديد

3. استخدام API Versioning
ممكن توفر نسخ مختلفة للتغييرات  زي:
/api/v1/users 
/api/v2/users

لكن مش كل تغيير محتاج Version جديدة الأفضل تحافظ على Backward Compatibility قدر الإمكان

4. تراقب استخدام الـEndpoints
قبل ما توقف Endpoint قديم راقب الـTraffic واعرف هل فيه إصدارات من التطبيق لسه بتستخدمه

5. تتبع إصدارات التطبيق (App Version Tracking)
ابعت App Version مع كل API Request من خلال Header أو Metadata عشان تعرف توزيع المستخدمين على الإصدارات المختلفة

6. تراقب أخطاء التطبيق (Client-side Monitoring)
تابع الـCrashes والـAPI Errors واربطها بإصدار التطبيق ونوع الجهاز ونظام التشغيل عشان تقدر تحدد الإصدارات اللي بتواجه مشاكل

7. اختبار التحديثات (Upgrade Testing)
ما تختبرش التطبيق بعد تثبيته من الصفر بس جرب التحديث من إصدار قديم لإصدار جديد وتأكد إن البيانات والإعدادات لسه سليمة خصوصا مع تغييرات الـLocal Database

في Mobile Development مش كفاية تتأكد إن التطبيق شغال على أحدث Version
لازم تفكر كمان في المستخدم اللي لسه بيستخدم إصدار من شهور أو حتى سنين.

 #Flutter #MobileDevelopment #SoftwareEngineering #Backend
