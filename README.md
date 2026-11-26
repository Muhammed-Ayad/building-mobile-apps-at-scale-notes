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

الكتاب مقسم إلى **5 أجزاء**، وفيهم **39 Challenge**.

الملاحظات المتاحة حاليًا للتحديات 1 إلى 5. باقي التحديات لسه ملاحظاتها مش مضافة، وهتتحول لروابط لما ملفاتها تتضاف.

## Part 1 — Challenges Due to the Nature of Mobile Applications

1. [State Management](./01-state-management.md)
2. [Mistakes Are Hard to Revert](./02-mistakes-are-hard-to-revert.md)
3. [The Long Tail of Old App Versions](./03-old-app-versions.md)
4. [Deeplinks](./04-deeplinks.md)
5. [Push and Background Notifications](./05-push-notifications.md)
6. App Crashes
7. Offline Support
8. Accessibility
9. CI/CD & The Build Train
10. Third-Party Libraries and SDKs
11. Device and OS Fragmentation
12. In-App Purchases

---

## Part 2 — Challenges Due to App Complexity

13. Navigation Architecture Within Large Apps
14. Application State & Event-Driven Changes
15. Localization
16. Modular Architecture & Dependency Injection
17. Automated Testing
18. Manual Testing

---

## Part 3 — Challenges Due to Large Engineering Teams

19. Planning and Decision Making
20. Architecting Ways to Avoid Stepping on Each Other's Toes
21. Shared Architecture Across Several Apps
22. Tooling Maturity for Large Engineering Teams
23. Scaling Build & Merge Times
24. Mobile Platform Libraries and Teams

---

## Part 4 — Languages and Cross-Platform Approaches

25. Adopting New Languages and Frameworks
26. Kotlin Multiplatform and KMM
27. Cross-Platform Feature Development
28. Cross-Platform App Development versus Native
29. Web, PWA & Backend-Driven Mobile Apps

---

## Part 5 — Challenges Due to Stepping Up Your Game

30. Experimentation
31. Feature Flag Hell
32. Performance
33. Analytics, Monitoring and Alerting
34. Mobile On-Call
35. Advanced Code Quality Checks
36. Compliance, Privacy and Security
37. Client-Side Data Migrations
38. Forced Upgrading
39. App Size
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

 
 
