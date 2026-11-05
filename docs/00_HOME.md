---
status: draft
document_type: knowledge-base-index
source: GDD v2.3 and Design Bibles
tags:
  - game-design
  - godot
  - documentation
updated: 2026-11-04
revision: approved-changes-2026-11-04
---

# GAME DESIGN KNOWLEDGE BASE

> Редакція 2026-11-04: затверджені зміни за [Decisions](Development/Decisions.md) мають пріоритет над суперечними правилами попередніх Word Bible. Оновлено документацію; реалізацію та ігровий баланс не перевірено.

> Головна база знань 2D Incremental Action RPG.
> Призначена для розробки гри на Godot із Claude Code.

## 1. Загальна інформація

- **Жанр:** Incremental Action RPG / Clicker RPG
- **Додаткові елементи:** Idle, Roguelite, Fantasy
- **Ігровий рушій:** Godot 4
- **Основна платформа:** PC (Steam)
- **Візуальний стиль:** 2D Dark Fantasy
- **Стан проєкту:** Pre-Production
- **Мова документації:** Українська

## 2. Основні документи

- [Огляд гри](01_Game_Overview.md)
- [Головні правила](02_Core_Rules.md)

## 3. Ігрові системи

- [Бойова система](Systems/Combat.md)
- [Стихії](Systems/Elements.md)
- [Резонанси](Systems/Resonances.md)
- [Екіпірування](Systems/Equipment.md)
- [Крафт](Systems/Crafting.md)
- [Економіка](Systems/Economy.md)
- [Прогресія](Systems/Progression.md)
- [Таланти](Systems/Talents.md)

## 4. Світ гри

- [Регіони](World/Regions.md)
- [Вежі](World/Towers.md)
- [Вороги та боси](World/Enemies.md)
- [Експедиції](World/Expeditions.md)

## 5. Персонажі

- [Головний герой](Characters/Main_Character.md)
- [Герої](Characters/Heroes.md)
- [Вихованці](Characters/Pets.md)

## 6. Візуальний стиль

- [Художній напрям](Art/Art_Direction.md)

## 7. Розробка

- [План розробки](Development/Roadmap.md)
- [Журнал рішень](Development/Decisions.md)
- [Журнал завдань](Development/Task_Log.md)

## 8. Основні принципи

1. Затверджені механіки не змінюються без погодження.
2. Незатверджені ідеї позначаються як draft.
3. Balance v1 потребує тестування в Godot.
4. Усі ігрові системи повинні бути сумісними.
5. Заборонено вигадувати відсутні числові значення.
6. Суперечності між документами потрібно виявляти.
7. Перед реалізацією механіки необхідно прочитати відповідну документацію.

## 9. Джерела інформації

Основою документації є Word-документи:

- Game Design Document
- Combat System
- Equipment & Accessories
- Enemies & Loot
- Crafting / Forge
- Heroes & Pets
- Talent Tree
- Economy & Balance
- World & Towers

Спеціалізовані Design Bible мають пріоритет
у деталях відповідної системи.

Невирішені суперечності потрібно погоджувати
перед реалізацією.

## 10. Статуси документації

- draft — документ ще розробляється.
- approved — механіка затверджена.
- implemented — реалізована та перевірена в Godot.

## 11. Поточний етап

Підготовка документації до розробки.

Наступні завдання:
- Перенесення затверджених правил із Word.
- Перевірка взаємозв'язків систем.
- Підготовка CLAUDE.md.
- Створення Skills для Claude Code.
- Підготовка архітектури Godot-проєкту.

## 12. Редакція від 2026-11-04

Оновлення за затвердженими рішеннями розробника: [Decisions](Development/Decisions.md), DEC-038–045 та оновлений DEC-016. Змінені Markdown-правила мають пріоритет над суперечними фрагментами попередніх Word Bible.

Почати з [Combat](Systems/Combat.md) §4, §9.4–9.5, [Heroes](Characters/Heroes.md) §27, §30–31, [Economy](Systems/Economy.md) §20, [Pets](Characters/Pets.md) §20, [Talents](Systems/Talents.md) §34 та [Roadmap](Development/Roadmap.md) §46. Збережено повний каталог 49/147 мобів і 14 Героїв. Фінальна кількість талантів і ціна залишаються відкритими.

Цей пакет — оновлена документація, не реалізований або перевірений ігровий build. Точні ціни, квестові encounter IDs, пороги та частина балансних чисел позначені OPEN/Balance v1.
