<div dir="rtl">

# التحدي الخامس من كتاب <span dir="ltr">Building Mobile Apps at Scale</span>: الـ <span dir="ltr">Push and Background Notifications</span> 🔔

🔗 [البوست على LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7531709009372856320/)

---

الـ <span dir="ltr">Push Notifications</span> بنستخدمها تقريبا في كل تطبيق، لكن تنفيذها بشكل صحيح فيه تحديات أكتر من مجرد إرسال <span dir="ltr">Notification</span>.

وأنا براجع الفصل ده وقفت عند شوية نقاط مهمة:

## 1. العلاقة بين الـ <span dir="ltr">Push Notifications</span> والـ <span dir="ltr">Deep Links</span>

الكتاب بيشير إن الـ <span dir="ltr">Push Notifications</span> بتواجه تحديات مشابهة للـ <span dir="ltr">Deep Links</span>، لأن الإشعار ممكن يكون رسالة مرتبطة بـ <span dir="ltr">Action</span> بتوجه المستخدم لجزء معين داخل التطبيق.

مثلا لو المستخدم استقبل إشعار عن إعلان جديد في النادي، ممكن لما يضغط عليه نفتح صفحة الإعلان بدل الصفحة الرئيسية.

لكن مش كل <span dir="ltr">Notification</span> لازم تكون مرتبطة بـ <span dir="ltr">Deep Link</span>، ده حسب الهدف من الإشعار.

## 2. التعامل مع حالات التطبيق في <span dir="ltr">Flutter</span>

مع <span dir="ltr">Firebase Messaging</span> بنتعامل مع الرسائل حسب حالة التطبيق:

- <span dir="ltr">Foreground</span>: باستخدام <span dir="ltr">FirebaseMessaging.onMessage</span>.
- <span dir="ltr">Background</span>: عند الضغط على الإشعار نستخدم <span dir="ltr">FirebaseMessaging.onMessageOpenedApp</span>.
- <span dir="ltr">Terminated</span>: لو التطبيق مقفول واتفتح من الإشعار نستخدم <span dir="ltr">getInitialMessage()</span>.

أما <span dir="ltr">onBackgroundMessage</span> فبيستخدم لمعالجة الرسائل في الخلفية، وده مختلف عن التعامل مع ضغط المستخدم على الإشعار.

## 3. الفرق بين <span dir="ltr">FCM Tokens</span> و<span dir="ltr">Topics</span>

- <span dir="ltr">Token</span>: بيحدد <span dir="ltr">App Instance</span> معين.
- <span dir="ltr">Topic</span>: بيسمح بإرسال الرسائل لمجموعة أجهزة مشتركة فيه.

والجهاز ممكن يكون عنده <span dir="ltr">Token</span> ومشترك في أكتر من <span dir="ltr">Topic</span>.

و<span dir="ltr">FCM</span> بيدعم 3 أنواع من الـ <span dir="ltr">Targets</span>: <span dir="ltr">Token</span> و<span dir="ltr">Topic</span> و<span dir="ltr">Condition</span>، والـ <span dir="ltr">Condition</span> ممكن يجمع أكتر من <span dir="ltr">Topic</span> باستخدام <span dir="ltr">Boolean Expressions</span>.

## 4. إدارة الـ <span dir="ltr">Permissions</span> والـ <span dir="ltr">Silent Push</span>

مش كل المستخدمين بيسمحوا بظهور الـ <span dir="ltr">Notifications</span>، ممكن يرفضوا الـ <span dir="ltr">Permission</span> أو يقفلوا الإشعارات من إعدادات الجهاز.

على <span dir="ltr">iOS</span> الـ <span dir="ltr">Silent Push</span> ممكن يوصل للتطبيق من غير <span dir="ltr">Alert</span> أو <span dir="ltr">Sound</span> أو <span dir="ltr">Badge</span> حتى لو المستخدم مش سامح بظهور الإشعارات، لكن وصوله مش مضمون وبيخضع لقيود النظام.

ومعلومة مهمة: لما نستخدم <span dir="ltr">FCM</span> مع أجهزة <span dir="ltr">Apple</span> بيوجه الرسالة إلى <span dir="ltr">APNs (Apple Push Notification service)</span>، وهي المسؤولة عن توصيلها للجهاز.

## 5. وصول الـ <span dir="ltr">Notification</span> مش مضمون

إرسال الـ <span dir="ltr">Notification</span> بنجاح مش معناه بالضرورة إنها وصلت أو ظهرت للمستخدم، ممكن يحصل تأخير أو <span dir="ltr">Throttling</span> أو مشاكل اتصال أو قيود من النظام.

وعشان كده الـ <span dir="ltr">Notification</span> مش مصدر الحقيقة للبيانات.

مثلا لو المستخدم استقبل إشعار إن الـ <span dir="ltr">Order</span> بتاعه لسه قيد التنفيذ، ممكن حالته تكون اتغيرت قبل ما يفتحه.

الأفضل نستخدم الإشعار كإشارة، ونرجع للـ <span dir="ltr">Backend</span> عشان نجيب أحدث بيانات ونتأكد من صلاحية المستخدم.

## 6. استخدام الـ <span dir="ltr">Background Notifications</span>

ممكن نستخدم رسائل في الخلفية عشان نزامن البيانات بين التطبيق والـ <span dir="ltr">Backend</span>:

- على <span dir="ltr">Android</span>: <span dir="ltr">Data Messages</span>
- على <span dir="ltr">iOS</span>: <span dir="ltr">Background Notifications</span>

وده ممكن يقلل اعتمادنا على الـ <span dir="ltr">Polling</span>، يعني إن التطبيق يفضل يبعت <span dir="ltr">Requests</span> للـ <span dir="ltr">Backend</span> كل فترة عشان يسأل: هل فيه بيانات جديدة؟

بدل كده ممكن الـ <span dir="ltr">Backend</span> يبعت إشعار للتطبيق لما يحصل تحديث، فيبدأ التطبيق يزامن البيانات.

لكن لازم ناخد بالنا إن وصول الرسائل وتشغيل التطبيق في الخلفية مش مضمونين، ونراعي حالة عدم وجود إنترنت <span dir="ltr">(Offline State)</span>، ونستخدم <span dir="ltr">Local Caching</span> للاحتفاظ بالبيانات محليا.

**وفي النهاية، الـ <span dir="ltr">Notification</span> مجرد إشارة بتنبه المستخدم إن فيه تحديث حصل، لكن الـ <span dir="ltr">Backend</span> هو مصدر الحقيقة والمرجع الأساسي لأحدث البيانات.**

#Flutter #Firebase #PushNotifications #MobileDevelopment

</div>
