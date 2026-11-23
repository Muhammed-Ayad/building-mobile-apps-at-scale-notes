# التحدي الأول من كتاب Building Mobile Apps at Scale

🔗 [البوست على LinkedIn](https://ae.linkedin.com/posts/mohamedayaddev_github-muhammed-ayadbuilding-mobile-apps-at-scale-notes-activity-7498025786180931587-fxmt)

---

بدأت أقرأ كتاب **Building Mobile Apps at Scale** لـ **Gergely Orosz**، والكتاب بيتكلم بشكل عام عن **Mobile Development** والتحديات اللي بتظهر لما الـ Apps تكبر، مش عن Flutter تحديدا.

أول حاجة شدتني كانت:

## State Management

في البداية الموضوع بيبان بسيط، لكن مع كبر الـ App بيبدأ يبقى معقد جدا.

ليه؟

لأن عندك Events كتير بتحصل بشكل asynchronous، ومش شرط تخلص بنفس الترتيب اللي بدأت بيه.

وده مش معناه إن أكتر من حاجة بتتنفذ في نفس الوقت. حتى مع single thread، ممكن تبدأ Request وتستنى نتيجتها، وفي الوقت ده الـ App يتعامل مع Events تانية.

مثلا:

```text
Request A starts

Request B starts

B finishes first

      ↓

New State

A finishes after

      ↓

Old State ❌
```

المشكلة هنا إن لو الاتنين بيغيروا نفس الـ State، ممكن الـ Request الأقدم يرجع في الآخر ويكتب فوق البيانات الجديدة.

وده ممكن يعمل Invalid State أو Bugs صعب جدا تعرف سببها.

أكتر حاجة عجبتني في الجزء ده إن المشكلة مش:

> "عندي State كتير"

لكن:

* مين مسؤول عن الـ State؟
* مين يقدر يغيرها؟
* وإيه اللي يحصل لما كذا Event يحصل ورا بعض ويغيروا نفس الـ State؟

الكتاب بيتكلم عن Reactive Programming، يعني ببساطة إنك تخلي الأجزاء المهتمة بالـ State تتفاعل لما يحصل تغيير، بدل ما كل جزء يفضل يسأل: "البيانات اتغيرت؟".

وده قريب من اللي بنستخدمه في Flutter مع Riverpod / BLoC ومش معناه بس Streams، دي مجرد أمثلة على الـ Reactive approach.

ومن ناحية Flutter، ده خلاني أربط الكلام بأفكار زي:

* Immutable State
* Unidirectional Data Flow
* Reactive Programming

وبالنسبة لي كـ Flutter Developer، بدأت أبص لـ Riverpod / BLoC بشكل مختلف.

مش مجرد إني أعرف أستخدم `ref.watch()` أو `BlocBuilder`، لكن الأهم أفهم:

* إزاي أصمم الـ State؟
* ومين المفروض يغيرها؟
* وإيه الـ States اللي ممكن أوصل لها؟

**Challenge #1 — State Management**
