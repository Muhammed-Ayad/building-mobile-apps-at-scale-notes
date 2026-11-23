# Building Mobile Apps at Scale — Notes & Challenges

ملاحظاتي، الدروس اللي بتعلمها، والتطبيقات العملية أثناء قراءة كتاب:

**Building Mobile Apps at Scale**
by **Gergely Orosz**

> هذا الـ Repository يحتوي على ملاحظاتي وفهمي الشخصي للتحديات والأفكار التي يناقشها الكتاب، وليس ملخصًا رسميًا أو نسخة من محتوى الكتاب.

---

## 📚 عن الكتاب

كتاب **Building Mobile Apps at Scale** بيتكلم عن التحديات الهندسية اللي بتظهر لما تطبيقات الموبايل تكبر، سواء بسبب زيادة عدد المستخدمين، أو حجم الـ Codebase والـ Features، أو زيادة حجم فرق الـ Engineering.

الكتاب بيتكلم عن **Mobile Development بشكل عام**، ومش مرتبط بـ Flutter أو Framework معين.

وده اللي خلاني مهتم بيه كمطور Flutter، لأن الهدف مش بس إني أعرف أستخدم Framework أو Library، لكن أفهم المشاكل الهندسية اللي ممكن تظهر في تطبيقات الـ Mobile الكبيرة، وإزاي أتعامل معاها.

---

# 📖 محتوى الكتاب

الكتاب مقسم إلى **5 أجزاء**، وفيهم **39 Challenge**# Building Mobile Apps at Scale
# Building Mobile Apps at Scale

## Part 1 — Challenges Due to the Nature of Mobile Applications

1. [State Management](./01-state-management.md) — [البوست على LinkedIn](https://ae.linkedin.com/posts/mohamedayaddev_github-muhammed-ayadbuilding-mobile-apps-at-scale-notes-activity-7498025786180931587-fxmt)
2. [Mistakes Are Hard to Revert](./02-mistakes-are-hard-to-revert.md) — [البوست على LinkedIn](https://ae.linkedin.com/posts/mohamedayaddev_flutter-mobiledevelopment-softwareengineering-activity-7525885213210521602-1BT6)
3. [The Long Tail of Old App Versions](./03-old-app-versions.md) — [البوست على LinkedIn](https://ae.linkedin.com/posts/mohamedayaddev_flutter-mobiledevelopment-softwareengineering-activity-7527711622329516032-GvOq)
4. [Deeplinks](./04-deeplinks.md) — [البوست على LinkedIn](https://www.linkedin.com/posts/mohamedayaddev_flutter-flutterdevelopment-mobiledevelopment-share-7530271911063277570-n_1F/)
5. [Push and Background Notifications](./05-push-and-background-notifications.md)
6. [App Crashes](./06-app-crashes.md)
7. [Offline Support](./07-offline-support.md)
8. [Accessibility](./08-accessibility.md)
9. [CI/CD & The Build Train](./09-ci-cd-and-build-train.md)
10. [Third-Party Libraries and SDKs](./10-third-party-libraries-and-sdks.md)
11. [Device and OS Fragmentation](./11-device-and-os-fragmentation.md)
12. [In-App Purchases](./12-in-app-purchases.md)

---

## Part 2 — Challenges Due to App Complexity

13. [Navigation Architecture Within Large Apps](./13-navigation-architecture-within-large-apps.md)
14. [Application State & Event-Driven Changes](./14-application-state-and-event-driven-changes.md)
15. [Localization](./15-localization.md)
16. [Modular Architecture & Dependency Injection](./16-modular-architecture-and-dependency-injection.md)
17. [Automated Testing](./17-automated-testing.md)
18. [Manual Testing](./18-manual-testing.md)

---

## Part 3 — Challenges Due to Large Engineering Teams

19. [Planning and Decision Making](./19-planning-and-decision-making.md)
20. [Architecting Ways to Avoid Stepping on Each Other's Toes](./20-architecting-to-avoid-team-conflicts.md)
21. [Shared Architecture Across Several Apps](./21-shared-architecture-across-several-apps.md)
22. [Tooling Maturity for Large Engineering Teams](./22-tooling-maturity.md)
23. [Scaling Build & Merge Times](./23-scaling-build-and-merge-times.md)
24. [Mobile Platform Libraries and Teams](./24-mobile-platform-libraries-and-teams.md)

---

## Part 4 — Languages and Cross-Platform Approaches

25. [Adopting New Languages and Frameworks](./25-adopting-new-languages-and-frameworks.md)
26. [Kotlin Multiplatform and KMM](./26-kotlin-multiplatform-and-kmm.md)
27. [Cross-Platform Feature Development](./27-cross-platform-feature-development.md)
28. [Cross-Platform App Development versus Native](./28-cross-platform-vs-native.md)
29. [Web, PWA & Backend-Driven Mobile Apps](./29-web-pwa-and-backend-driven-mobile-apps.md)

---

## Part 5 — Challenges Due to Stepping Up Your Game

30. [Experimentation](./30-experimentation.md)
31. [Feature Flag Hell](./31-feature-flag-hell.md)
32. [Performance](./32-performance.md)
33. [Analytics, Monitoring and Alerting](./33-analytics-monitoring-and-alerting.md)
34. [Mobile On-Call](./34-mobile-on-call.md)
35. [Advanced Code Quality Checks](./35-advanced-code-quality-checks.md)
36. [Compliance, Privacy and Security](./36-compliance-privacy-and-security.md)
37. [Client-Side Data Migrations](./37-client-side-data-migrations.md)
38. [Forced Upgrading](./38-forced-upgrading.md)
39. [App Size](./39-app-size.md)
---

# 🎯 هدفي من الـ Repository

الهدف مش إني أعمل **Summary للكتاب** وخلاص.

أنا بحاول مع كل Challenge أفهم:

1. **إيه المشكلة؟**
2. **ليه المشكلة بتحصل؟**
3. **إيه الـ Engineering Concepts المرتبطة بيها؟**
4. **إزاي ممكن تظهر في مشروع حقيقي؟**
5. **إزاي أتعامل معاها كمطور Flutter؟**
6. **إيه الحلول والـ Trade-offs؟**
7. **إيه الحاجة اللي أقدر أطبقها في مشاريعي؟**

---

# 📱 Flutter Perspective

الكتاب مش عن Flutter.

لكن بما إني **Flutter Developer**، هحاول أربط كل Challenge لما يكون مناسب بالمفاهيم والأدوات اللي بنستخدمها في Flutter، مثل:

- Flutter
- Dart
- Riverpod
- BLoC
- REST APIs
- Streams
- Reactive Programming
- Clean Architecture
- Dependency Injection
- App Lifecycle
- CI/CD
- Testing
- Performance

لكن مش هحاول أربط كل موضوع بـ Flutter بالعافية.

بعض الـ Challenges مرتبطة مباشرة بالـ Flutter، وبعضها مرتبط بـ **Mobile Engineering** بشكل عام، وبعضها متعلق أكثر بالـ Architecture والـ Teams والـ Engineering Practices.

 
 
