---

status: active  
document_type: development-task-log  
project_status: not-started  
current_milestone: M00  
current_task: DEV-001  
last_completed_task: none  
last_verified_build: none  
updated: 2026-11-04
tags:

- development
    
- task-log
    
- progress
    
- godot
    
- claude-code
    
- testing
    
- git
    

revision: approved-changes-2026-11-04
---

# TASK LOG — Журнал розробки гри

> Редакція 2026-11-04: затверджені зміни за [Decisions](Decisions.md) мають пріоритет над суперечними правилами попередніх Word Bible. Оновлено документацію; реалізацію та ігровий баланс не перевірено.

> Робочий журнал створення 2D Dark Fantasy Clicker / Incremental Action RPG на Godot 4.
> 
> Призначення: зберігати фактичний прогрес програмування, зміни файлів, результати перевірок, виявлені помилки, залежності між задачами та наступні кроки.
> 
> Документ використовується разом із [Roadmap](Roadmap.md), [Decisions](Decisions.md) та [02_Core_Rules](../02_Core_Rules.md).
> 
> **Основне правило:** задача вважається завершеною тільки після реалізації та перевірки. Згенерований код без підтвердженого результату не дорівнює виконаній задачі.

## 1. Призначення Task Log

Task Log відповідає на питання:

- На якому етапі перебуває розробка?
    
- Яка задача зараз активна?
    
- Що вже реалізовано?
    
- Які файли були змінені?
    
- Які функції перевірено?
    
- Які помилки залишилися?
    
- Чи запускається Godot-проєкт?
    
- Чи працюють Save/Load?
    
- Чи є ризик зламати попередні системи?
    
- Який наступний конкретний крок?
    
- Які рішення розробника потрібні для продовження?
    

### Чому це важливо

Claude Code працює з контекстом конкретної сесії.

Під час нової сесії він повинен мати змогу зрозуміти поточний стан проєкту, не вимагаючи повторного пояснення всієї історії розробки.

### Головний принцип

**Task Log — запис того, що фактично сталося, а не список того, що AI хотів зробити.**

Плани зберігаються в Roadmap.

Рішення — у Decisions.

Реальні дії та їх результати — у Task Log.

---

## 2. Поточний стан проєкту

**Дата початкового запису:** 2026-10-15.

**Project Status:** Not Started.

**Current Milestone:** M00 — Environment Ready.

**Current Task:** DEV-001 — Create Godot Project.

**Last Completed Task:** None.

**Last Verified Build:** None.

**Godot Project Created:** No.

**Claude Code Connected:** No.

**Gameplay Implemented:** No.

**Automated Tests:** Not Run.

**Manual Gameplay Tests:** Not Run.

### Що вже є

- Підготовлені Word Design Bible.
    
- Створена структура Markdown-документації для Obsidian.
    
- Заповнені основні документи `Systems/`.
    
- Заповнені документи `World/`.
    
- Заповнені документи `Characters/`.
    
- Підготовлений `Art/Art_Direction.md`.
    
- Підготовлений `Development/Roadmap.md`.
    
- Підготовлений `Development/Decisions.md`.
    
- Godot встановлений.
    
- VS Code встановлений.
    

### Що ще відсутнє

- Створений і перевірений Godot Project.
    
- Налаштована інтеграція Claude Code.
    
- Реалізована ігрова архітектура.
    
- Створені бойові сцени.
    
- Реалізована система атаки.
    
- Реалізований інвентар.
    
- Реалізована система збережень.
    
- Реалізовані ігрові системи.
    
- Фінальні графічні ассети.
    
- Тестовий Build.
    
- Steam Build.
    

### Важлива примітка

Документація підготовлена, але ще потребує фінального аудиту внутрішніх посилань, суперечностей і незатверджених Balance/Content значень.

Факт існування Markdown-файлу не підтверджує, що його правила реалізовані в Godot.

---

## 3. Основні джерела істини

Перед кожною задачею перевіряти:

1. [00_HOME](../00_HOME.md) — структура документації.
    
2. [01_Game_Overview](../01_Game_Overview.md) — концепція гри.
    
3. [02_Core_Rules](../02_Core_Rules.md) — основні обмеження.
    
4. [Roadmap](Roadmap.md) — порядок розробки.
    
5. [Decisions](Decisions.md) — затверджені рішення.
    
6. Відповідний спеціалізований документ.
    
7. Поточний Task Log.
    
8. Наявний код Godot.
    

### Пріоритет

Спеціалізовані правила системи мають пріоритет над загальними прикладами програмування.

### Якщо знайдена суперечність

- Не вибирати випадкове правило.
    
- Перевірити спеціалізовану Bible.
    
- Перевірити останні затверджені Decisions.
    
- Якщо відповідь відсутня — позначити задачу Blocked.
    
- Попросити погодження розробника.
    

---

## 4. Статуси задач

Використовувати єдину систему статусів.

|Status|Значення|
|---|---|
|Planned|Задача запланована|
|Ready|Вимоги перевірені, задача готова до роботи|
|In Progress|Виконання розпочато|
|Blocked|Роботу блокує проблема або невизначеність|
|Testing|Код написаний, потрібна перевірка|
|Rework|Результат потребує виправлення|
|Done|Реалізація завершена та перевірена|

### Правила переходів

**Planned → Ready**

Вимоги зрозумілі, залежності перевірені.

**Ready → In Progress**

Розпочато фактичну роботу.

**In Progress → Testing**

Код реалізовано, але ще не підтверджено його працездатність.

**Testing → Done**

Необхідні перевірки виконані успішно.

**Testing → Rework**

Знайдено помилки або невідповідності.

**Rework → Testing**

Виправлення виконані, потрібна повторна перевірка.

**Будь-який статус → Blocked**

Є проблема, яка не дозволяє безпечно продовжити.

### Заборона

Не переводити задачу безпосередньо в Done тільки тому, що Claude Code написав «готово».

---

## 5. Ідентифікатори задач

Використовувати стабільні Task IDs.

### Формат

`DEV-001`

`DEV-002`

`DEV-003`

### Для інших видів записів

|Префікс|Призначення|
|---|---|
|DEV|Задачі розробки|
|BUG|Виявлені помилки|
|TEST|Тестові перевірки|
|SESSION|Робочі сесії|
|DOC|Перевірки та зміни документації|
|PERF|Оптимізація продуктивності|

### Головне правило

ID після створення не змінюється.

Наприклад:

DEV-010 завжди означає ту саму задачу.

Якщо згодом потрібно істотно змінити її обсяг, слід залишити історію та створити новий запис або пов'язану задачу.

---

## 6. Формат запису задачі

Кожна задача має містити такі поля.

### Task ID

Унікальний номер.

### Назва

Короткий опис результату.

### Status

Один із визначених статусів.

### Milestone

Відповідний етап Roadmap.

### Priority

High / Medium / Low.

### Documents

Markdown-файли з правилами.

### Goal

Який результат потрібно отримати.

### Scope

Що входить у задачу.

### Out of Scope

Що не потрібно робити.

### Dependencies

Від чого залежить задача.

### Modified Files

Фактично змінені файли.

### Implementation

Що реалізовано.

### Testing

Які перевірки виконано.

### Bugs

Знайдені проблеми.

### Git Commit

Фактичний commit, якщо створений.

### Next Step

Конкретна наступна дія.

---

## 7. Шаблон нової задачі

Наступний блок є шаблоном. Його потрібно копіювати для реальних задач.

### TASK TEMPLATE

**Task ID:** DEV-XXX

**Title:** Назва задачі.

**Status:** Planned.

**Milestone:** MXX.

**Priority:** High / Medium / Low.

**Created:** дата створення.

**Started:** Not Started.

**Completed:** Not Completed.

**Related Documents:**

- Відповідний документ.
    
- Додатковий документ.
    

**Goal:**

Опис очікуваного результату.

**Scope:**

- Перша дія.
    
- Друга дія.
    
- Третя дія.
    

**Out of Scope:**

Що не входитиме в поточну реалізацію.

**Dependencies:**

Необхідні попередні задачі.

**Planned Files:**

Файли, які передбачається створити або змінити.

**Modified Files:**

None.

**Implementation Notes:**

Not Started.

**Automated Tests:**

Not Run.

**Manual Tests:**

Not Run.

**Known Bugs:**

None reported — not tested.

**Git Commit:**

None.

**Definition of Done:**

- Функція реалізована.
    
- Немає критичних помилок.
    
- Функція відповідає документації.
    
- Проведено відповідні тести.
    
- Не зламані залежні системи.
    
- Результат підтверджено.
    

**Next Step:**

Одна наступна конкретна дія.

---

## 8. Шаблон робочої сесії

Кожна повноцінна сесія розробки повинна мати власний запис.

### SESSION TEMPLATE

**Session ID:** SESSION-XXX

**Date:** фактична дата.

**Milestone:** поточний етап.

**Starting Task:** поточна задача.

**Starting Project State:**

Стан проєкту на початку роботи.

**Session Goal:**

Конкретна мета.

**Tasks Worked On:**

- Task ID.
    
- Task ID.
    

**Files Created:**

- Реально створені файли.
    

**Files Modified:**

- Реально змінені файли.
    

**Files Deleted:**

- Реально видалені файли.
    

**Implementation Summary:**

Що саме реалізовано.

**Automated Tests:**

- Назва.
    
- Результат.
    

**Manual Tests:**

- Назва.
    
- Результат.
    

**Godot Errors:**

Фактичні помилки або `None observed` лише якщо проводилася перевірка.

**Known Bugs:**

Відкриті проблеми.

**Documentation Changes:**

Які документи змінено та чому.

**Git Commit:**

Реальний hash або `Not Created`.

**Session Result:**

Done / Partial / Blocked / Rework.

**Next Task:**

Одна конкретна задача.

**Resume Notes:**

Коротка інструкція для наступної сесії Claude Code.

---

## 9. Початковий Backlog

Задачі перенесені з [Roadmap](Roadmap.md).

Жодна ще не виконана.

|ID|Назва|Status|Milestone|
|---|---|---|---|
|DEV-001|Create Godot Project|Planned|M00|
|DEV-002|Configure VS Code|Planned|M00|
|DEV-003|Configure Claude Code|Planned|M00|
|DEV-004|Connect Documentation|Planned|M00|
|DEV-005|Initialize Git|Planned|M00|
|DEV-006|Create Main Scene|Planned|M01|
|DEV-007|Create Combat Scene|Planned|M02|
|DEV-008|Create Enemy Definition|Planned|M02|
|DEV-009|Implement Enemy HP|Planned|M02|
|DEV-010|Implement Manual Attack|Planned|M02|
|DEV-011|Implement Hold Attack|Planned|M02|
|DEV-012|Implement Enemy Death|Planned|M02|
|DEV-013|Implement Gold Reward|Planned|M02|
|DEV-014|Implement Gold Upgrade|Planned|M02|
|DEV-015|Implement Save/Load Test|Planned|M02|

### Примітка

Це початковий список, а не повний перелік усіх задач гри.

Нові задачі створюються відповідно до Roadmap та поточної архітектури.

---

## 10. Current Task — DEV-001

**Task ID:** DEV-001.

**Title:** Create Godot Project.

**Status:** Planned.

**Milestone:** M00 — Environment Ready.

**Priority:** High.

**Created:** 2026-10-15.

**Started:** Not Started.

**Completed:** Not Completed.

### Goal

Створити новий Godot 4 Project та підтвердити, що він коректно запускається.

### Related Documents

- [Roadmap](Roadmap.md)
    
- [00_HOME](../00_HOME.md)
    
- [02_Core_Rules](../02_Core_Rules.md)
    

### Scope

- Вибрати робочу директорію.
    
- Створити Godot Project.
    
- Відкрити проєкт у Godot.
    
- Перевірити версію Godot.
    
- Створити мінімальну стартову сцену, якщо це необхідно для перевірки запуску.
    
- Запустити проєкт.
    
- Перевірити Output/Debugger.
    
- Зберегти початкову структуру.
    

### Out of Scope

- Combat.
    
- Enemy AI.
    
- Equipment.
    
- Forge.
    
- Talent Tree.
    
- Heroes.
    
- Pets.
    
- Full UI.
    
- Final Art.
    
- Steam Integration.
    

### Dependencies

Наявність встановленого Godot.

### Modified Files

None.

### Testing

Not Run.

### Expected Result

Новий порожній Godot 4 Project, який відкривається та запускається без критичних помилок.

### Definition of Done

- Проєкт створений.
    
- `project.godot` існує.
    
- Godot відкриває проєкт.
    
- Початкова сцена працює, якщо створена.
    
- Немає критичних помилок запуску.
    
- Результат перевірено.
    

### Next Task

DEV-002 — Configure VS Code.

---

## 11. Правила ведення Task Log

### Перед початком сесії

Claude Code повинен:

1. Прочитати поточний Task Log.
    
2. Визначити Current Milestone.
    
3. Визначити Current Task.
    
4. Перевірити Roadmap.
    
5. Перевірити відповідні Decisions.
    
6. Перевірити фактичний стан файлів проєкту.
    
7. Перевірити Git Status, якщо Git уже налаштований.
    
8. Запропонувати короткий план.
    

### Під час виконання

Записувати:

- Фактично створені файли.
    
- Фактично змінені файли.
    
- Причини значних змін.
    
- Нові залежності.
    
- Знайдені проблеми.
    

Не потрібно після кожного рядка коду оновлювати Task Log.

### Після виконання

1. Виконати доступні перевірки.
    
2. Описати реальний результат.
    
3. Оновити статус задачі.
    
4. Зафіксувати помилки.
    
5. Оновити Session Log.
    
6. Визначити наступну задачу.
    
7. Запропонувати Git Commit, якщо зміни перевірені.
    

---

## 12. Розмежування плану та фактичного результату

Це один із найважливіших принципів документа.

### Planned Files

Файли, які Claude Code планує змінити.

### Modified Files

Файли, які Claude Code дійсно змінив.

### Planned Tests

Перевірки, які потрібно виконати.

### Tests Performed

Перевірки, які справді виконано.

### Expected Result

Результат, який повинен бути.

### Actual Result

Фактично підтверджена поведінка.

### Приклад

**Planned Test:**

Запустити Godot Project.

**Actual Result:**

Not Run.

У такому випадку не можна писати:

«Godot Project працює без помилок».

Можна написати:

«Файли створені, але запуск у Godot ще не перевірено».

---

## 13. Рівні перевірки результату

Використовувати три рівні підтвердження.

### Level 1 — Code Written

Код створений або змінений.

Це ще не завершена задача.

### Level 2 — Technical Verification

Виконано доступні технічні перевірки.

Приклади:

- Перевірка синтаксису.
    
- Перевірка існування ресурсів.
    
- Запуск відповідних тестів.
    
- Перевірка помилок завантаження.
    
- Перевірка Godot Project.
    

### Level 3 — Gameplay Verification

Перевірено фактичну поведінку у грі.

Приклади:

- Клік завдає шкоди.
    
- HP зменшується.
    
- Ворог помирає.
    
- Gold додається.
    
- Save/Load відновлює стан.
    

### Правило

Для Gameplay Task статус Done потребує відповідної фактичної перевірки, а не лише наявності написаного коду.

---

## 14. Позначення тестових результатів

|Result|Значення|
|---|---|
|NOT_RUN|Тест не виконувався|
|PASS|Тест проведено успішно|
|FAIL|Тест проведено, є помилка|
|BLOCKED|Немає можливості виконати тест|
|PARTIAL|Перевірена лише частина вимог|

### Обов'язкові поля тесту

- Test ID.
    
- Task ID.
    
- Перевірка.
    
- Очікуваний результат.
    
- Фактичний результат.
    
- Статус.
    
- Дата.
    
- Середовище або спосіб перевірки.
    

### Заборона

Не ставити PASS без виконання відповідної перевірки.

Не припускати успішність тільки тому, що алгоритм виглядає правильним.

---

## 15. Шаблон тесту

**Test ID:** TEST-XXX.

**Related Task:** DEV-XXX.

**Test Name:** Назва перевірки.

**Expected:**

Очікувана поведінка.

**Steps:**

1. Перша дія.
    
2. Друга дія.
    
3. Третя дія.
    

**Actual:**

Not Tested.

**Result:** NOT_RUN.

**Test Environment:**

Not Recorded.

**Notes:**

Додаткові спостереження.

---

## 16. Приклад тесту майбутньої бойової системи

**Test ID:** TEST-001.

**Related Task:** DEV-010.

**Test Name:** Manual Attack reduces Enemy HP.

**Status:** NOT_RUN.

### Preconditions

- Combat Scene існує.
    
- Enemy має Current HP.
    
- Manual Attack реалізовано.
    

### Steps

1. Запустити Combat Scene.
    
2. Дочекатися появи ворога.
    
3. Зафіксувати поточне HP.
    
4. Натиснути ЛКМ на ворозі.
    
5. Перевірити HP після атаки.
    

### Expected

- Ворог отримує один дозволений удар.
    
- HP зменшується на розраховану величину.
    
- Damage Number відображається.
    
- Не виникає подвійного удару від одного натискання.
    

### Actual

Not Tested.

### Result

NOT_RUN.

### Причина

Manual Attack ще не реалізовано.

---

## 17. Реєстр помилок

Помилки мають окремі BUG IDs.

### Формат

**Bug ID:** BUG-XXX.

**Title:** Коротка назва.

**Severity:** Critical / High / Medium / Low.

**Status:** Open / In Progress / Fixed / Verified / Reopened.

**Related Task:** DEV-XXX.

**Steps to Reproduce:**

Послідовність дій.

**Expected Result:**

Правильна поведінка.

**Actual Result:**

Фактична помилка.

**Affected Files:**

Файли, якщо визначені.

**Fix:**

Що було змінено.

**Verification:**

Який тест підтвердив виправлення.

### Severity

**Critical:**

Проєкт не запускається, Save пошкоджується або блокується основна прогресія.

**High:**

Система працює неправильно, можливий exploit або неправильні нагороди.

**Medium:**

Функціональна помилка з обмеженим впливом.

**Low:**

Косметична або незначна UI-проблема.

### Початковий стан

Поки ігрового проєкту немає, фактичний Bug Register порожній.

Це не означає, що майбутній код не матиме помилок.

---

## 18. Правило виправлення помилок

Коли з'являється помилка:

1. Зафіксувати BUG ID.
    
2. Описати відтворення.
    
3. Знайти причину.
    
4. Визначити пов'язані файли.
    
5. Запропонувати мінімальне виправлення.
    
6. Не переписувати всю систему без потреби.
    
7. Виконати повторний тест.
    
8. Виконати необхідний Regression Test.
    
9. Оновити Bug Status.
    
10. Записати результат у Task Log.
    

### Приклад

Якщо Gold Reward нараховується двічі, потрібно перевірити Reward Claim та Death State.

Не слід одразу переписувати всю Economy System.

---

## 19. Modified Files Log

Для кожної виконаної задачі вказувати фактичні зміни.

### Формат

|File|Change Type|Reason|
|---|---|---|
|Фактичний шлях|Created / Modified / Deleted|Причина|

### Важливо

Шляхи повинні відповідати реальній структурі Godot-проєкту.

Не використовувати вигадані назви файлів тільки тому, що вони були в Roadmap як приклад.

### Для великих змін

Додатково пояснювати:

- Які класи змінені.
    
- Які Signals додані.
    
- Які дані тепер зберігаються.
    
- Які системи можуть бути зачеплені.
    
- Які тести потрібні.
    

---

## 20. Контроль Git

Після налаштування Git кожна завершена перевірена задача або логічна група змін може мати Commit.

### Приклад назв

- `init: create Godot project`
    
- `feat: add enemy health`
    
- `feat: add manual attack`
    
- `feat: add combat rewards`
    
- `fix: prevent duplicate rewards`
    
- `test: add save load checks`
    
- `docs: update combat decisions`
    

### У Task Log записувати

- Commit Hash.
    
- Task ID.
    
- Короткий опис.
    
- Чи проходять відповідні тести.
    

### Заборони

- Не вигадувати Commit Hash.
    
- Не писати, що Git Commit створено, якщо цього не відбулося.
    
- Не видаляти історію заради приховування невдалих спроб.
    
- Не включати секретні ключі або токени в Git.
    
- Не виконувати руйнівні Git-операції без погодження.
    

---

## 21. Зв'язок із Decisions

Task Log не повинен самостійно змінювати канон гри.

### Приклад

Під час реалізації Equipment система виявила невизначеність:

Як технічно екіпірувати лучника, якщо стандартний каталог зброї не має Bow Class?

### Правильна дія

1. Зафіксувати блокер у задачі.
    
2. Знайти відповідне OPEN-рішення в [Decisions](Decisions.md).
    
3. Пояснити можливі варіанти.
    
4. Отримати затвердження.
    
5. Оновити Decisions.
    
6. Оновити Equipment/Heroes.
    
7. Продовжити реалізацію.
    

### Неправильна дія

Самостійно додати восьмий тип зброї та позначити задачу Done.

---

## 22. Зв'язок із Roadmap

Roadmap визначає великі контрольні етапи.

Task Log фіксує їхнє фактичне виконання.

### Приклад

Roadmap:

M02 — First Combat.

Task Log:

- DEV-008 — Enemy Definition.
    
- DEV-009 — Enemy HP.
    
- DEV-010 — Manual Attack.
    
- DEV-011 — Hold Attack.
    
- DEV-012 — Enemy Death.
    
- DEV-013 — Gold Reward.
    

### Milestone Done

Етап M02 можна завершити лише тоді, коли виконані його приймальні критерії.

Завершення останньої запланованої задачі саме по собі не гарантує готовність Milestone.

---

## 23. Milestone Register

|Milestone|Назва|Status|
|---|---|---|
|M00|Environment Ready|Not Started|
|M01|Foundation Ready|Not Started|
|M02|First Combat|Not Started|
|M03|Floors 1–20|Not Started|
|M04|Floors 21–40|Not Started|
|M05|Systems Slice|Not Started|
|M06|First Tower 141|Not Started|
|M07|Rebirth & World|Not Started|
|M08|First Triad|Not Started|
|M09|Seven Regions|Not Started|
|M10|Celestial Towers|Not Started|
|M11|Endgame & Finale|Not Started|
|M12|Balancing & QA|Not Started|
|M13|Steam Release|Not Started|

### Правило оновлення

Milestone змінює статус після перевірки його Definition of Done.

Детальні критерії брати з [Roadmap](Roadmap.md).

---

## 24. Save/Load Change Tracking

Кожна задача, що змінює ігровий стан, повинна перевіряти вплив на SaveData.

### Записувати

- Чи створено нові Saved Fields.
    
- Чи змінено існуючі.
    
- Чи змінено Stable IDs.
    
- Чи потрібна Migration.
    
- Чи перевірено старе збереження.
    
- Чи перевірено нове збереження.
    

### Приклад

Нова система Pet Stars додає дані прогресу вихованця.

Перед завершенням задачі потрібно переконатися, що після Save/Load кількість Stars не змінюється.

### Критично важливі системи

- Souls.
    
- Rebirth.
    
- Equipment Instances.
    
- Hero Ascension.
    
- Pet Instances.
    
- Talent Presets.
    
- Story Flags.
    
- Guardian Materials.
    
- General Hearts.
    
- Expedition Reward Claims.
    

### Заборона

Не очищати весь SaveData через додавання нового поля.

---

## 25. Atomic Reward Tracking

Відповідні нагороди повинні видаватися не більше одного разу на дозволену подію.

### Особливо важливі

- First Guardian Reward.
    
- First General Heart.
    
- Triad Regional Blueprint.
    
- First Egg.
    
- First Hero.
    
- Expedition Claim.
    
- Trial Milestone.
    
- Одноразова видача бойових/квестових нагород.
    
- Rebirth Souls.
    

### Для задач Reward System перевіряти

- Event ID.
    
- Source ID.
    
- Claim State.
    
- Повторний виклик.
    
- Save/Load.
    
- Rebirth.
    
- Захист від подвійного натискання.
    

### Правило

Якщо нагорода випадково видається двічі, задача не може мати статус Done.

---

## 26. Regression Testing

Після зміни вже реалізованої системи потрібно перевіряти залежні механіки.

### Combat Change

Можливі залежності:

- Equipment.
    
- RES.
    
- Resonance.
    
- Heroes.
    
- Pets.
    
- Boss Timers.
    

### Economy Change

Можливі залежності:

- Gold Rewards.
    
- Crafting.
    
- Видача бойових і квестових нагород без купівлі випадкового вмісту.
    
- Souls.
    
- Rebirth.
    
- AFK.
    

### World Progress Change

Можливі залежності:

- Story Flags.
    
- Tower Unlocks.
    
- Expeditions.
    
- Dungeon Discovery.
    
- General Echo.
    

### SaveData Change

Можливі залежності:

- Усі постійні системи.
    

### Заборона

Не проводити великий рефакторинг без перевірки залежних функцій.

---

## 27. Документаційні зміни

Для змін Markdown створювати DOC-записи, якщо вони важливі для подальшої реалізації.

### Приклад формату

**DOC ID:** DOC-XXX.

**Document:** відповідний файл.

**Change:** точний опис.

**Reason:** причина.

**Decision ID:** відповідне рішення, якщо є.

**Affected Code:** фактичні файли, якщо є.

**Validation:** перевірка узгодженості.

### Не потребує окремого рішення

- Виправлення друкарської помилки.
    
- Виправлення внутрішнього посилання.
    
- Уточнення оформлення без зміни змісту.
    

### Потребує Decisions

- Зміна канонічного правила.
    
- Зміна сюжетного гейту.
    
- Додавання нової механіки.
    
- Зміна Rebirth Reset/Keep.
    
- Зміна затвердженого джерела нагороди.
    

---

## 28. Правило роботи з відкритими питаннями

Якщо задача потребує ще не погоджених даних:

### Варіант A — питання не блокує задачу

Можна реалізувати:

- Структуру даних.
    
- Інтерфейс.
    
- Конфігурацію.
    
- Тимчасову заглушку для тесту.
    

Але параметр повинен бути явно позначений як Temporary/Balance v1.

### Варіант B — питання впливає на канон

Задача повинна бути Blocked до рішення.

### Приклад

Точний BaseDPS Героя ще не затверджений.

Можна реалізувати HeroDefinition і читання BaseDPS із конфігурації.

Не можна назвати довільне число остаточним балансом усіх 14 Героїв.

---

## 29. Правила Claude Code щодо Task Log

Claude Code повинен:

- Читати журнал на початку сесії.
    
- Не припускати, що попередні задачі виконані.
    
- Перевіряти реальні файли.
    
- Не змінювати статус без фактичної підстави.
    
- Описувати створені файли.
    
- Описувати змінені файли.
    
- Повідомляти про помилки.
    
- Відрізняти PASS від NOT_RUN.
    
- Фіксувати Blockers.
    
- Вказувати наступну задачу.
    
- Зберігати історію.
    

### Заборонено

- Вигадувати результати тестів.
    
- Вигадувати Git Commits.
    
- Позначати всі задачі Done після генерації коду.
    
- Видаляти невдалі сесії.
    
- Приховувати відомі помилки.
    
- Перезаписувати історію без потреби.
    
- Самовільно змінювати Canon.
    
- Створювати нові системи поза Scope поточної задачі.
    

---

## 30. Короткий протокол нової сесії

Перед початком роботи Claude Code потрібно надати таку інструкцію:

### Session Start Instruction

Прочитай документацію Godot-проєкту, починаючи з:

- docs/00_HOME.md
    
- docs/01_Game_Overview.md
    
- docs/02_Core_Rules.md
    
- docs/Development/Roadmap.md
    
- docs/Development/Decisions.md
    
- docs/Development/Task_Log.md
    

Потім:

1. Перевір реальну структуру проєкту.
    
2. Визнач поточну задачу.
    
3. Прочитай відповідні спеціалізовані документи.
    
4. Перевір залежності.
    
5. Перевір Git Status, якщо Git налаштований.
    
6. Запропонуй короткий план змін.
    
7. Переліч файли, які плануєш змінити.
    
8. Не змінюй затверджені механіки.
    
9. Не починай сторонні задачі.
    
10. Після погодження реалізуй поточну задачу.
    

### Session End Instruction

Після виконання:

1. Назви реально змінені файли.
    
2. Поясни фактично виконану роботу.
    
3. Вкажи проведені тести.
    
4. Вкажи їхні результати.
    
5. Переліч невиправлені помилки.
    
6. Визнач поточний статус задачі.
    
7. Онови Task Log.
    
8. Запропонуй одну наступну задачу.
    

Якщо не можеш запустити Godot або виконати тест, прямо зазнач це.

Не заявляй про успішне тестування без перевірки.

---

## 31. Критерії завершення задачі

Для кожної задачі використовувати контрольний список.

- Реалізовано всі заплановані вимоги.
    
- Не реалізовано зайвих механік.
    
- Дотримано Core Rules.
    
- Дотримано відповідних Decisions.
    
- Код не дублює існуючі системи.
    
- Файли правильно підключені.
    
- Немає підтверджених критичних помилок.
    
- Проведено необхідні тести.
    
- Save/Load перевірено, якщо змінюється стан.
    
- Проведено необхідні Regression Tests.
    
- Task Log оновлений.
    
- Результат підтверджено.
    

### Done

Задачу можна позначити Done лише після відповідних тестів.

### Testing

Якщо код є, але не перевірений, використовувати Testing.

### Blocked

Якщо існує нерозв'язана залежність, використовувати Blocked.

---

## 32. Правило роботи з Git Commits

Рекомендований цикл:

1. Реалізація.
    
2. Технічна перевірка.
    
3. Ручна перевірка, якщо потрібна.
    
4. Оновлення Task Log.
    
5. Перевірка Git Diff.
    
6. Commit.
    
7. Перевірка Git Status.
    
8. Перехід до наступної задачі.
    

### Якщо задача не завершена

Можна зафіксувати проміжний технічний стан.

Але Task Log не повинен позначати її Done.

### Якщо виникла критична помилка

Потрібно:

- Зберегти відомості про неї.
    
- Визначити останній перевірений стан.
    
- Запропонувати виправлення або безпечне повернення до попередньої версії.
    

Не виконувати руйнівні операції без дозволу.

---

## 33. Вимоги до збереження історії

Task Log має залишатися читабельним протягом усієї розробки.

### Активні записи

На початку документа:

- Project Status.
    
- Current Milestone.
    
- Current Task.
    
- Active Blockers.
    
- Latest Session.
    

### Історія

Нижче зберігаються:

- Completed Tasks.
    
- Previous Sessions.
    
- Fixed Bugs.
    
- Documentation Changes.
    
- Important Test Results.
    

### Майбутня оптимізація

Коли журнал стане великим, можна створити окремі архівні Markdown-файли за місяцями або Milestones.

Але це окреме організаційне рішення.

Історію не потрібно видаляти.

---

## 34. Поточні Blockers

### BLK-001 — Godot Project Not Created

**Status:** Active.

**Related Task:** DEV-001.

Поки Godot Project не створено, неможливо реально тестувати Gameplay.

### BLK-002 — Claude Code Not Connected

**Status:** Active.

**Related Task:** DEV-003.

Не налаштована робота Claude Code з локальним проєктом.

### BLK-003 — Project Architecture Not Verified

**Status:** Active.

**Related Task:** M01.

Реальна структура папок і файлів ще не створена та не перевірена.

### Важливе уточнення

Це стартові організаційні залежності, а не виявлені помилки Godot.

Вони повинні бути закриті після відповідних задач.

---

## 35. Початковий Session Log

### SESSION-000 — Documentation Preparation

**Date:** 2026-10-15.

**Type:** Documentation Preparation.

**Status:** Documentation Prepared.

**Related Milestone:** Pre-Development.

### Summary

Підготовлена структура Markdown-документації для Obsidian на основі фінальних Word Design Bible.

### Prepared Documents

**General**

- 00_HOME.md
    
- 01_Game_Overview.md
    
- 02_Core_Rules.md
    

**Systems**

- Combat.md
    
- Elements.md
    
- Resonances.md
    
- Equipment.md
    
- Crafting.md
    
- Progression.md
    
- Economy.md
    
- Talents.md
    

**World**

- Regions.md
    
- Towers.md
    
- Enemies.md
    
- Expeditions.md
    

**Characters**

- Main_Character.md
    
- Heroes.md
    
- Pets.md
    

**Art**

- Art_Direction.md
    

**Development**

- Roadmap.md
    
- Decisions.md
    
- Task_Log.md
    

### Important Notes

- Документація підготовлена для подальшої реалізації.
    
- Фінальна перевірка всіх внутрішніх посилань ще не проведена.
    
- Фінальний аудит суперечностей ще потрібний.
    
- Balance v1 не пройшов плейтести.
    
- Реальний Godot Project ще не створений.
    
- Успішних Gameplay Tests немає.
    

### Modified Godot Files

None.

### Automated Tests

NOT_RUN.

### Manual Gameplay Tests

NOT_RUN.

### Git Commit

None recorded.

### Next Milestone

M00 — Environment Ready.

### Next Task

DEV-001 — Create Godot Project.

---

## 36. Latest Session

**Session ID:** SESSION-000.

**Date:** 2026-10-15.

**Result:** Documentation Prepared.

**Last Gameplay Build:** None.

**Last Completed Development Task:** None.

**Active Milestone:** M00.

**Next Task:** DEV-001.

### Resume Notes

Почати зі створення нового Godot 4 Project.

Перед створенням великої структури файлів перевірити:

- Обрану директорію.
    
- Версію Godot.
    
- Доступність VS Code.
    
- Доступність документації.
    
- План підключення Claude Code.
    
- Початкову архітектуру.
    

Не реалізовувати Gameplay до підтвердження працездатності стартового проєкту.

---

## 37. Правила фінального звіту Claude Code

Після кожної задачі Claude Code повинен надавати короткий структурований звіт.

### Task Result

- Task ID.
    
- Status.
    
- Що реалізовано.
    
- Створені файли.
    
- Змінені файли.
    
- Виконані тести.
    
- Фактичні результати.
    
- Відомі помилки.
    
- Наступна задача.
    

### Формулювання результату

**Done:**

Лише якщо реалізацію перевірено.

**Implemented, Not Tested:**

Код готовий, але працездатність не підтверджена.

**Blocked:**

Є проблема або відсутнє рішення.

**Rework Required:**

Проведено перевірку й знайдено невідповідність.

### Заборона

Не використовувати «повністю готово» для функції, яку ніхто не перевірив.

---

## 38. Пов'язані документи

- [00_HOME](../00_HOME.md)
    
- [01_Game_Overview](../01_Game_Overview.md)
    
- [02_Core_Rules](../02_Core_Rules.md)
    
- [Roadmap](Roadmap.md)
    
- [Decisions](Decisions.md)
    
- [Combat](../Systems/Combat.md)
    
- [Elements](../Systems/Elements.md)
    
- [Resonances](../Systems/Resonances.md)
    
- [Equipment](../Systems/Equipment.md)
    
- [Crafting](../Systems/Crafting.md)
    
- [Progression](../Systems/Progression.md)
    
- [Economy](../Systems/Economy.md)
    
- [Talents](../Systems/Talents.md)
    
- [Regions](../World/Regions.md)
    
- [Towers](../World/Towers.md)
    
- [Enemies](../World/Enemies.md)
    
- [Expeditions](../World/Expeditions.md)
    
- [Main_Character](../Characters/Main_Character.md)
    
- [Heroes](../Characters/Heroes.md)
    
- [Pets](../Characters/Pets.md)
    
- [Art_Direction](../Art/Art_Direction.md)
    

---

## 39. Головні заборони

Claude Code не повинен:

- Починати нову задачу, не перевіривши стан попередньої.
    
- Ігнорувати Task Log.
    
- Вигадувати результати тестів.
    
- Вигадувати створені файли.
    
- Вигадувати Git Commits.
    
- Позначати неперевірений код Done.
    
- Приховувати відомі помилки.
    
- Видаляти історію розробки.
    
- Самовільно змінювати Canon.
    
- Самовільно міняти Balance без запису.
    
- Додавати сторонні механіки.
    
- Створювати кілька несумісних Save Systems.
    
- Переписувати великий обсяг робочого коду без причини.
    
- Починати масштабування контенту до перевірки основної механіки.
    
- Замінювати фактичний результат власним очікуванням.
    

---

## 40. Підсумковий стан

**Project:** 2D Dark Fantasy Clicker / Incremental Action RPG.

**Engine:** Godot 4.

**Code Editor:** VS Code.

**AI Development Tool:** Claude Code.

**Target Platform:** PC / Steam.

**Project Status:** Not Started.

**Current Milestone:** M00 — Environment Ready.

**Current Task:** DEV-001 — Create Godot Project.

**Last Completed Development Task:** None.

**Last Verified Build:** None.

**Documentation:** Prepared, final audit pending.

**Balance:** Balance v1, not playtested.

**Next Action:** Create and verify the initial Godot project.

### Головне правило

**Журнал має відображати тільки реальний прогрес. Кожна задача повинна мати підтверджений результат, а кожна нова сесія — зрозумілу точку продовження.**

## 41. DOC-2026-11-04 — Оновлення дизайн-документації

**Дата:** 2026-11-04. **Статус:** Documentation Updated; Gameplay Not Verified.

Джерело — новий архів docs.rar, наданий розробником, із вже доданими Enemy Action Bar, Interrupt, Impact Sync та процедурною анімацією. Застосовано затверджені зміни отримання Героїв/петів, Sigils, автоатаки, візуалу зброї та уточнення релізного обсягу/талантів/ціни. Підтримано нову модель непереривних базових ударів.

Оновлено основні правила й залежні FTUE-таблиці, перевірки, архітектурні поля та Decisions. Старі Word-джерела не редагувалися; нові рішення мають пріоритет у змінених механіках.

Перевірка цього пакета охоплює тексти, посилання, відсутність активних старих умов та збереження каталогів. Код Godot, ігрові тести й баланс не виконувались; старий запис про стан проєкту вище є історичним і не підтверджує актуальний стан зовнішнього Godot-проєкту.

### Наступні задачі — Planned

- Узгодити точні Hero Purchase Prices, квестові thresholds і encounter IDs персональних випробувань.
- Заповнити квестові завдання Special Pets та кількості Essence; перевірити всі шляхи отримання/розвитку.
- Реалізувати й перевірити бойовий зріз 1–20 з раннім Interrupt та Auto Attack.
- Виміряти таймінги бою, захист від повторного Interrupt та економіку після вилучення скринь.
- Підготувати й порівняти профілі талантів за Talents §34.
- Оцінити демо/фестивалі перед рішенням про ціну.
