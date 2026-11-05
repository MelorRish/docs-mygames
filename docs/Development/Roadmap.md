---

status: draft  
document_type: development-roadmap  
source: GDD v2.3, Design Bibles, Art Direction, approved decisions 2026-10-14  
development_status: not-started  
priority: high  
updated: 2026-11-04
tags:

- development
    
- roadmap
    
- godot
    
- claude-code
    
- vertical-slice
    
- testing
    
- steam
    

revision: approved-changes-2026-11-04
---

# DEVELOPMENT ROADMAP — План розробки гри

> Редакція 2026-11-04: затверджені зміни за [Decisions](Decisions.md) мають пріоритет над суперечними правилами попередніх Word Bible. Оновлено документацію; реалізацію та ігровий баланс не перевірено.

> Покроковий план реалізації 2D Dark Fantasy Clicker / Incremental Action RPG на Godot 4 для PC/Steam.
> 
> Основне джерело ігрових вимог: GDD v2.3 та десять фінальних Design Bible.
> 
> Основне середовище розробки: Godot 4, VS Code, Claude Code.
> 
> Головний принцип: створювати гру невеликими робочими етапами, завершувати кожен тестуванням і не переходити до масштабування контенту до стабілізації основних систем.
> 
> **Важливо:** порядок реалізації, розбиття на технічні етапи та рекомендована архітектура в цьому документі є Development Plan. Вони не змінюють канонічних правил самої гри.

## 1. Мета Roadmap

Roadmap потрібен, щоб:

- Розуміти, що розробляти першим.
    
- Не намагатися створити всю гру одним промптом.
    
- Не змішувати реалізацію різних систем.
    
- Розділяти Gameplay Logic і Visual Art.
    
- Зберігати працездатність Godot-проєкту.
    
- Контролювати залежності між системами.
    
- Перевіряти результат після кожного етапу.
    
- Не втрачати прогрес роботи з Claude Code.
    
- Своєчасно виявляти архітектурні помилки.
    
- Поступово отримати придатну для Steam гру.
    

### Головне правило

**Спочатку робоча механіка, потім її візуальна обробка, далі тестування та масштабування.**

Не потрібно створювати сотні красивих ассетів для бойової системи, якщо базовий клік, отримання шкоди, нагороди та збереження ще не працюють.

## 2. Поточний стан проєкту

Стан на момент створення Roadmap.

|Компонент|Статус|
|---|---|
|GDD|Підготовлений|
|Design Bible|Підготовлені|
|Obsidian Knowledge Base|Заповнена основними специфікаціями|
|Art Direction|Чернетка підготовлена|
|Godot|Встановлений|
|VS Code|Встановлений|
|Claude Code Integration|Не налаштовано|
|Godot Game Project|Не створено|
|Gameplay Code|Не реалізовано|
|Final Art Assets|Не створено|
|Vertical Slice|Не реалізовано|
|Steam Build|Не створено|

### Важливе уточнення

Те, що документація написана, не означає, що її фінально перевірено.

Основні Markdown-документи мають статус `draft` до затвердження.

При виявленні суперечностей потрібно:

1. Знайти точне спеціалізоване джерело.
    
2. Встановити, яке правило затверджене.
    
3. Зафіксувати рішення в Decisions.
    
4. Синхронізувати відповідні Markdown-документи.
    
5. Лише потім реалізовувати спірну механіку.
    

## 3. Цільова платформа

### Основна платформа

PC — Steam.

### Ігровий формат

- Single-player-first.
    
- Premium Game.
    
- Incremental Action RPG.
    
- Clicker RPG.
    
- Roguelite Progression.
    
- 2D Stylized Dark Fantasy.
    

### Управління

- ЛКМ: Manual Attack.
    
- Утримання ЛКМ: Hold Attack.
    
- Клавіші 1–4: активні навички.
    
- Миша: Inventory, Tooltips, UI.
    
- Окреме керування Hero Ultimate.
    
- Auto Attack після сюжетного відкриття.
    

### Інтерфейс

Підтримувати співвідношення:

- 16:9.
    
- 16:10.
    

Інтерфейс має масштабуватися.

### Майбутні можливості

- Steam Achievements.
    
- Steam Cloud Save.
    
- Інші інтеграції Steam після стабілізації основної гри.
    
- Потенційний Mobile Port у майбутньому.
    

### Обмеження

- Не створювати Mobile Port раніше основної PC-версії.
    
- Не додавати купівлю випадкового вмісту скринь за гроші або внутрішньоігрові валюти.
    
- Не створювати обов'язковий Online Backend без необхідності.
    
- Не створювати глобальний Competitive Leaderboard без перевірки достовірності результатів.
    

## 4. Головні принципи розробки

### 4.1. Маленькі завершені задачі

Кожна задача повинна мати конкретний результат.

Приклад:

«Додати HP Bar слайма, який зменшується при кліку».

Це краща задача, ніж:

«Зробити всю бойову систему».

### 4.2. Робоча версія після кожного кроку

Після завершення задачі Godot-проєкт повинен запускатися.

### 4.3. Data-Driven Architecture

Числа та ігровий контент не повинні бути жорстко записані всередині UI.

### 4.4. Єдине джерело правил

Використовувати відповідні Markdown-специфікації з `docs/`.

### 4.5. Відокремлення графіки

Можна використовувати тимчасові графічні заглушки до затвердження фінального Art Style.

### 4.6. Регулярне тестування

Будь-яка нова механіка повинна перевірятися в Godot.

### 4.7. Контроль змін

Кожне важливе архітектурне або канонічне рішення потрібно зафіксувати.

## 5. Основні джерела істини

Claude Code повинен використовувати такі документи:

### Загальні

- [00_HOME](../00_HOME.md)
    
- [Game Overview](../01_Game_Overview.md)
    
- [Core Rules](../02_Core_Rules.md)
    

### Systems

- [Combat](../Systems/Combat.md)
    
- [Elements](../Systems/Elements.md)
    
- [Resonances](../Systems/Resonances.md)
    
- [Equipment](../Systems/Equipment.md)
    
- [Crafting](../Systems/Crafting.md)
    
- [Progression](../Systems/Progression.md)
    
- [Economy](../Systems/Economy.md)
    
- [Talents](../Systems/Talents.md)
    

### World

- [Regions](../World/Regions.md)
    
- [Towers](../World/Towers.md)
    
- [Enemies](../World/Enemies.md)
    
- [Expeditions](../World/Expeditions.md)
    

### Characters

- [Main Character](../Characters/Main_Character.md)
    
- [Heroes](../Characters/Heroes.md)
    
- [Pets](../Characters/Pets.md)
    

### Art

- [Art Direction](../Art/Art_Direction.md)
    

### Development

- [Decisions](Decisions.md)
    
- [Task Log](Task_Log.md)
    

### Пріоритет

Коли задача належить до конкретної системи, відповідна спеціалізована Bible має пріоритет у деталях цієї системи.

Не слід автоматично замінювати канонічне правило загальним прикладом із програмування.

## 6. Порядок великих етапів

Roadmap поділено на технічні стадії.

|Етап|Назва|Результат|
|---|---|---|
|0|Project Setup|Налаштоване середовище|
|1|Technical Foundation|Базова архітектура|
|2|First Combat Prototype|Перший робочий бій|
|3|Vertical Slice 1–20|Перша повноцінна бойова петля|
|4|Vertical Slice 21–40|Другий біом, RES та Loot|
|5|Systems Slice|Основні системи розвитку|
|6|First Tower 1–141|Повний перший FTUE|
|7|Rebirth & World|Переродження та карта|
|8|First Region|Три Башти першої Тріади|
|9|Campaign Expansion|Усі сім регіонів|
|10|Celestial Content|Сім Небесних Веж|
|11|Endgame & Story Finale|Король Демонів і Trial|
|12|Balancing & QA|Стабільність і баланс|
|13|Steam Release Preparation|Підготовка релізу|

### Важливе уточнення

Це рекомендоване розбиття на етапи розробки.

Воно не означає, що всі підсистеми повинні бути повністю написані до моменту їх появи у грі.

Дозволено створювати базовий технічний фундамент заздалегідь, але гравець повинен отримувати доступ до функцій лише за встановленими FTUE Unlock Conditions.

## 7. Етап 0 — Project Setup

**Ціль:** підготувати робоче середовище.

**Статус:** Not Started.

### Задачі

- Створити новий Godot 4 Project.
    
- Вибрати директорію проєкту.
    
- Перевірити запуск порожнього проєкту.
    
- Підключити VS Code як редактор коду.
    
- Перевірити відкриття скриптів у VS Code.
    
- Встановити та налаштувати Claude Code.
    
- Надати Claude Code доступ до робочої папки проєкту.
    
- Підключити папку `docs/`.
    
- Перевірити, що Claude Code може читати Markdown.
    
- Створити систему контролю версій Git.
    
- Створити перший Commit.
    
- Перевірити запуск сцени в Godot.
    

### Рекомендація

Використовувати один основний каталог гри.

Не створювати декілька несинхронізованих копій Godot-проєкту.

### Definition of Done

Етап вважається завершеним, коли:

1. Godot-проєкт запускається.
    
2. VS Code відкриває його скрипти.
    
3. Claude Code може працювати з файлами проєкту.
    
4. `docs/` доступна для читання.
    
5. Перший Git Commit збережено.
    

### Заборони

Не починати масове створення ігрових сцен до перевірки середовища.

## 8. Етап 1 — Technical Foundation

**Ціль:** створити мінімальну архітектуру для подальших систем.

**Статус:** Not Started.

### Основні модулі

- Game State.
    
- Save/Load.
    
- Combat.
    
- Tower/Encounter.
    
- Inventory/Loot.
    
- Economy.
    
- Progression/Unlocks.
    
- UI Navigation.
    
- Audio/VFX.
    

### Рекомендована структура

Приклад організації Godot-проєкту:

```
project/
├── project.godot
├── docs/
├── scenes/
│   ├── main/
│   ├── combat/
│   ├── ui/
│   ├── world/
│   └── characters/
├── scripts/
│   ├── core/
│   ├── combat/
│   ├── progression/
│   ├── inventory/
│   ├── economy/
│   └── ui/
├── data/
│   ├── enemies/
│   ├── items/
│   ├── towers/
│   ├── heroes/
│   ├── pets/
│   └── balance/
├── assets/
│   ├── characters/
│   ├── enemies/
│   ├── backgrounds/
│   ├── equipment/
│   ├── effects/
│   ├── ui/
│   └── audio/
└── tests/
```

### Статус структури

Це рекомендована архітектура.

Остаточні назви папок і файлів потрібно погодити на початку реалізації.

### Основні задачі

- Створити Main Scene.
    
- Створити перший Combat Scene.
    
- Створити мінімальний Game State.
    
- Створити систему Game Events/Signals.
    
- Створити систему Stable IDs.
    
- Створити основу SaveData.
    
- Додати Version Field у SaveData.
    
- Створити мінімальний Data Loader.
    
- Відокремити Balance Config.
    
- Створити базову UI Navigation.
    
- Додати Error/Debug Logging.
    

### Definition of Done

- Проєкт запускається.
    
- Немає критичних помилок завантаження.
    
- Є основна сцена.
    
- Є система читання даних.
    
- Є можливість зберегти та завантажити тестовий стан.
    
- Контент не залежить від випадкових назв вузлів UI.
    

## 9. Етап 2 — First Combat Prototype

**Ціль:** створити перший повністю робочий бій.

**Статус:** Not Started.

### Перша ціль

Малий слайм.

### Необхідні функції

- Ворог має HP.
    
- Ворог має Max HP.
    
- Ворог має базову атаку.
    
- ГГ має ATK.
    
- ГГ має HP.
    
- Клік завдає шкоди.
    
- Утримання ЛКМ завдає повторні удари.
    
- HP ворога зменшується.
    
- HP ГГ зменшується після атак ворога.
    
- Коли HP ворога дорівнює нулю, він помирає.
    
- Після перемоги гравець отримує Gold.
    
- Відображаються Damage Numbers.
    
- Працює проста Hit Reaction.
    
- Відображається поточний поверх.
    

### Необхідні сцени

- Combat Scene.
    
- Enemy Scene.
    
- Main Character Visual.
    
- Enemy HP Bar.
    
- Basic Combat HUD.

- Enemy Action / Cast Bar під смужкою HP ворога.
    

### Графіка

Дозволені тимчасові заглушки.

Не потрібно створювати фінального ГГ або всі сім стихій.

### Перевірки

- Один клік завдає один дозволений удар.
    
- Hold Attack працює.
    
- Немає нескінченного Attack Spam.
    
- Ворог отримує шкоду.
    
- Ворог атакує ГГ.
    
- HP коректно зменшується.
    
- Перемога спрацьовує один раз.
    
- Gold нараховується один раз.
    
- Сцена не зависає після перемоги.
    
- Немає критичних Godot Errors.
    

### Definition of Done

Гравець може відкрити гру, побачити слайма, атакувати його, перемогти та отримати нагороду.

### Важливе правило

Якщо цей цикл не приносить зрозумілого відчуття удару й нагороди, не потрібно переходити до створення всього світу.

## 10. Етап 3 — Vertical Slice 1–20

**Ціль:** створити перші 20 поверхів Башти 01-I.

**Статус:** Not Started.

### Контент

Регіон:

R1 — Заражені топі.

Башта:

01-I — Слизна Долина.

### Вороги

- Малий слайм.
    
- Болотний слайм.
    
- Панцирний слайм.
    
- Elite-варіації.
    
- Слизний Король.
    

### Розподіл

|Поверхи|Ворог|
|---|---|
|1–5|Малий слайм|
|6–10|Болотний слайм|
|11–15|Панцирний слайм|
|16–19|Elite Mix|
|20|Слизний Король|

### Механіки

- Floor Progression.
    
- Enemy Definition.
    
- HP Scaling.
    
- ATK Scaling.
    
- Manual Attack.
    
- Hold Attack.
    
- Basic Gold.
    
- Basic XP.
    
- Level Up.
    
- Gold Upgrade.
    
- Loot Drops.
    
- First Equipment Drop.
    
- Inventory.
    
- Equipment.
    
- Elite Modifier.
    
- Zone Boss.
    
- Boss Timer.
    
- Bestiary Unlock.
    
- Save/Load.
    
- Basic SFX.
    
- Basic VFX.

- Enemy Action / Cast Bar: непереривна смужка «Атака» для слаймів та переривний каст здібності для Зонального боса (Слизний Король).

- Interrupt Mechanic: можливість збити каст навички Слизного Короля активною навичкою ГГ із візуальним статусом «ПЕРЕРВАНО!».

- Projectile Skill Impact Sync: візуальний приліт тестової навички (наприклад, «Метеор») із нанесенням шкоди в момент удару.

- Procedural Enemy Animation: шейдер дихання та `Tween`-реакція на удари для спрайтів слаймів.
    

### FTUE

Floor 1:

Manual/Hold Combat.

Floor 2:

Gold Upgrades.

Floor 10:

Перший гарантований предмет та Inventory.

Floor 20:

Перший Zone Boss і Bestiary.

### Definition of Done

- Гравець може пройти 20 поверхів.
    
- Усі чотири типи Encounter працюють.
    
- Перший бос має таймер.
    
- Гравець отримує Gold/XP/Loot.
    
- Інвентар не дублює предмети.
    
- Save/Load зберігає прогрес.
    
- Базовий бій приємний протягом 30–60 с.
    

### Milestone

**MVP Combat Slice 0–20.**

Не переходити до масового створення регіонів, поки цей етап нестабільний.

## 11. Етап 4 — Vertical Slice 21–40

**Ціль:** перевірити, що система підтримує інші типи ворогів та більш складні бойові механіки.

**Статус:** Not Started.

### Контент

Другий візуальний блок першої Башти.

Наступне Enemy Family:

Ґобліни топей.

### Системи

- Другий Enemy Family.
    
- Інший візуальний біом.
    
- Physical RES.
    
- Elemental RES.
    
- Weakness.
    
- Affix Generation.
    
- Порівняння предметів.
    
- Нові Loot Pools.
    
- Boss Variation.
    
- Enemy Bestiary Details.
    
- Daily Tasks Unlock Floor 40.
    

### Definition of Done

- RES реально впливає на шкоду.
    
- Weakness працює.
    
- Другий бос відрізняється від першого.
    
- Другий набір ворогів працює через ту саму архітектуру.
    
- Можна додати нового ворога через дані без переписування Combat Scene.
    

## 12. Етап 5 — Systems Slice

**Ціль:** послідовно додати основні системи розвитку.

**Статус:** Not Started.

GDD визначає рекомендований порядок:

**Forge → Talent Tree → Pets → Heroes → Reaction Focus.**

Кожну систему потрібно завершувати окремим тестом.

### 5.1. Forge

- Crafting UI.
    
- Recipes.
    
- Item Upgrade.
    
- Synthesis.
    
- Salvage.
    
- Enchantment.
    
- Rarity/Rank Rules.
    
- Material Costs.
    
- Save/Load.
    

### 5.2. Talent Tree

- Talent Data Structure.
    
- Talent Node IDs.
    
- Prerequisites.
    
- Talent Points.
    
- Node Purchase.
    
- Run Reset.
    
- Presets.
    
- UI.
    

### 5.3. Pets

- Pet Species Data.
    
- Egg Instances.
    
- Incubator.
    
- First Hatch.
    
- Two Active Slots.
    
- Pet Effects.
    
- Pet XP.
    
- Pet Synthesis.
    
- Pet Essence.
    
- Stars.
    

### 5.4. Heroes

- Hero Definitions.
    
- Hero Roster.
    
- First Hero Unlock.
    
- Autonomous Hero Attack.
    
- Active Skill.
    
- Ultimate.
    
- Six Equipment Slots.
    
- Hero XP.
    
- Ascension.
    

### 5.5. Reaction Focus

- Primary Element Channel.
    
- Secondary Element Channel.
    
- Core Resonance.
    
- Hero Element.
    
- Hero Resonance.
    
- Reaction Focus Selection.
    
- Triple Resonance.
    
- Alignment States.
    

### Важливе правило

Ці системи повинні мати власні сюжетні Unlock Flags.

Технічно готова система не обов'язково доступна гравцеві з першого поверху.

### Definition of Done

Кожна система:

1. Працює окремо.
    
2. Має правильні вхідні дані.
    
3. Не ламає вже готові системи.
    
4. Має UI.
    
5. Зберігає стан.
    
6. Має перевірені Unlock Conditions.
    

## 13. Етап 6 — Повна перша Башта 1–141

**Ціль:** завершити весь FTUE першої Башти Ув'язнення.

**Статус:** Not Started.

### Контент

Сім Enemy Families R1.

Сім Zone Boss.

Один Guardian 141.

### Відкриття функцій

|Floor|Система|
|---|---|
|1|Combat|
|2|Gold Upgrades|
|10|Inventory + utility_interrupt|
|20|Bestiary + Auto Attack після перемоги|
|40|Daily Tasks|
|60|Quests / Reputation|
|70|Звичайний прогрес; магазин випадкових скринь вилучено|
|80|Forge I|
|100|Talent Tree|
|115|Pets|
|130|Heroes / Reaction Focus|
|141|World Map / Rebirth / Expeditions|

### Ключові перевірки

- Floor 70 не відкриває купівлю випадкових скринь.
    
- Скрині є лише поданням бойової/квестової нагороди; купівля випадкового вмісту відсутня.
    
- Forge I працює на Floor 80 без безкоштовного Element Crystal.
    
- Enchant I вимагає відповідний отриманий Crystal.
    
- Floor 100 видає перший TP.
    
- Floor 115 дає гарантоване яйце.
    
- Floor 130 дає гарантовану Сільву.
    
- Floor 141 має Guardian.
    
- Перший Guardian Clear дає один його спеціальний матеріал.
    
- World Map відкривається.
    
- Rebirth відкривається.
    
- Expedition System відкривається.
    
- Перша Небесна Вежа стає доступною.
    
- Trial Tower стає видимою, але ще закритою.
    

### Definition of Done

Перша Башта проходиться повністю.

Усі FTUE Events спрацьовують на потрібних поверхах.

Гравець розуміє основний ігровий цикл.

Сюжетні нагороди не дублюються після Reload.

## 14. Етап 7 — Rebirth та World Progress

**Ціль:** реалізувати головну довгострокову петлю гри.

**Статус:** Not Started.

### Rebirth

- Rebirth Preview.
    
- Souls Earned Calculation.
    
- Total Souls Collected.
    
- Available Souls.
    
- Soul Power.
    
- Permanent Soul Skills.
    
- Soul Relics.
    
- Run Reset Rules.
    
- Keep Rules.
    
- Rebirth Seal.
    
- Rebirth Confirmation.
    
- Persistent Save.
    

### World Map

- Один континент.
    
- Сім регіонів.
    
- Locked/Unlocked States.
    
- Prison Tower Markers.
    
- Celestial Tower Markers.
    
- Dungeon Discovery.
    
- Story Progress.
    

### Expeditions

- Expedition Slot 1.
    
- Targeted.
    
- Unknown.
    
- Hero Assignment.
    
- Timers.
    
- Rewards.
    
- Scout Event.
    
- Guaranteed Dungeon Discovery.
    

### Перша розвідка

Після першого Guardian 141:

- Одноразова миттєва навчальна розвідка.
    
- Гарантоване відкриття першого Данжу.
    
- Відповідні Persistent Flags.
    

### Важливий інваріант

Rebirth має скидати лише те, що визначено Progression Bible.

Не можна випадково втрачати:

- Permanent Unlocks.
    
- Souls.
    
- Soul Skills.
    
- Soul Relics.
    
- Hero Collection.
    
- Pet Collection.
    
- Story Flags.
    
- Відкриті рецепти.
    

### Definition of Done

Гравець може:

1. Пройти першу Башту.
    
2. Виконати Rebirth.
    
3. Отримати Souls.
    
4. Зберегти Meta Progress.
    
5. Почати новий run.
    
6. Швидше проходити знайомий контент.
    

## 15. Етап 8 — Перша повна регіональна Тріада

**Ціль:** зробити перший регіон завершеним.

**Статус:** Not Started.

### Контент

Три Башти R1:

- 01-I — Слизна Долина.
    
- 01-II — Туманні Болота.
    
- 01-III — Серце Гниття.
    

### Основні задачі

- Додати Башту 01-II.
    
- Додати Башту 01-III.
    
- Налаштувати повторне використання сімейств.
    
- Додати варіації босів.
    
- Додати нові RES Profiles.
    
- Додати нові регіональні Loot Pools.
    
- Додати Guardian Special Materials.
    
- Додати Triad Clear.
    
- Додати Regional Blueprint Unlock.
    
- Додати відповідний World Progress.
    

### Auto Attack

Базова Auto Attack відкривається після першої перемоги над Зональним босом на поверсі 20 Башти 01-I. Відкриття постійне, зберігається після Rebirth; доступний перемикач увімкнення/вимкнення. Вхід у 01-II більше не є умовою відкриття.

Це Permanent Unlock.

### First Triad Clear

Після першого очищення всіх трьох Башт:

- Встановлюється Triad Clear Flag.
    
- Відкриваються відповідні затверджені регіональні рецепти.
    
- Не видаються дублікати після Rebirth.
    

### Definition of Done

Гравець може пройти три Башти, змінювати білд, використовувати Auto Attack та отримати перший повний регіональний прогрес.

## 16. Етап 9 — Campaign Expansion

**Ціль:** реалізувати повний основний контент семи регіонів.

**Статус:** Not Started.

### Контент

- Сім регіонів.
    
- 21 Башта Ув'язнення.
    
- Сім Тріад.
    
- 49 Enemy Families.
    
- 147 базових Mob A/B/C.
    
- 21 Prison Guardian.
    
- Сім стихійних Данжів.
    
- Сім поселень.
    
- Повна система регіональних ресурсів.
    

### Основні системи

- Region Definitions.
    
- Tower Definitions.
    
- Enemy Families.
    
- Guardian Definitions.
    
- Regional Loot Tables.
    
- Dungeon Definitions.
    
- Element Crystal Rewards.
    
- Regional Quests.
    
- Reputation Progression.
    
- Exploration/Expeditions.
    
- Triad Blueprints.
    
- World Recovery States.
    

### Технічний принцип

Не дублювати всю Combat Logic для кожної Башти.

Додавати новий контент через:

- Data Definitions.
    
- Enemy Pools.
    
- Boss Definitions.
    
- Background Sets.
    
- Loot Tables.
    
- Story Unlocks.
    

### Definition of Done

Усі 21 Башта функціонують через одну стабільну систему проходження.

Сім Данжів відкриваються за Scout Rules.

Усі сюжетні та регіональні нагороди видаються коректно.

## 17. Етап 10 — Celestial Content

**Ціль:** реалізувати сім Небесних Веж.

**Статус:** Not Started.

### Структура

- Сім Небесних Веж.
    
- По 666 поверхів.
    
- 42 іменні командири.
    
- Сім Генералів.
    
- Сім General Hearts.
    
- Унікальні Boss Mechanics.
    
- True Elemental Immunity.
    
- General Echo.
    
- Named Drops.
    
- Сюжетне руйнування Пальців.
    

### Для кожної Небесної Вежі

- Створити Definition.
    
- Налаштувати Floor Progression.
    
- Додати тематичні Enemy Pools.
    
- Додати Zone Boss.
    
- Додати шість командирів.
    
- Додати командирські матеріали.
    
- Створити Генерала.
    
- Реалізувати три фази.
    
- Реалізувати Signature Immunity.
    
- Реалізувати General Story Clear.
    
- Реалізувати Echo.
    
- Реалізувати General Heart Rewards.
    
- Створити відповідний сюжетний VFX.
    

### Порядок босів

- Zone Boss: кожні 20 поверхів.
    
- Commander: 100/200/300/400/500/600.
    
- General: 666.
    

Commander замінює Zone Boss свого поверху.

### Відкриття

**Небесна Вежа 1**

Після Guardian 141 Башти 01-I.

**Вежі 2–4**

Через відповідні експедиції та регіональні Story Gates.

**Вежа 5**

Усі умови одночасно:

- Мінімум чотири очищені Тріади.
    
- Reputation Rank ≥6.
    
- Мінімум три переможені Генерали.
    

**Вежа 6**

Усі умови одночасно:

- Мінімум п'ять очищених Тріад.
    
- Reputation Rank ≥8.
    
- Мінімум чотири переможені Генерали.
    

**Вежа 7**

Після шести Генералів та відповідного сюжетного доступу до R7.

### General Hearts

First Story Clear:

Один гарантований відповідний Heart.

General Echo:

30% на один відповідний Heart.

### Definition of Done

Усі сім Небесних Веж доступні лише за правильними Story Gates.

Генерали мають власні механіки й імунітети.

Гравець може перемогти кожного Генерала сюжетно тільки один раз.

Повторний фарм виконується через Echo.

## 18. Етап 11 — Endgame та фінальна історія

**Ціль:** завершити основну сюжетну кампанію й довгостроковий контент.

**Статус:** Not Started.

### Infinite Trial Tower

Одна нескінченна Вежа Випробувань.

Стани:

1. Sealed.
    
2. Awakened.
    
3. True Infinite.
    

### Відкриття

- Після першого Guardian 141: видима.
    
- Після першого Генерала: рання доступна.
    
- Після Короля Демонів: повний ендґейм.
    

### Основні задачі

- Trial Encounter System.
    
- Infinite Floor Scaling.
    
- Boss кожні 10 поверхів.
    
- Elite Modifier Pool.
    
- Trial Marks.
    
- Milestone Rewards.
    
- Personal Best Record.
    
- Save/Load Trial State.
    
- Захист від нескінченного Soul Farm.
    

### Demon Rift

- Story Access після семи Генералів.
    
- Вісім сюжетних етапів Розлому.
    
- Прадавній Клинок Відсічення.
    
- Demon King Battle.
    
- Три фази Короля.
    
- Фінальний сюжетний перехід.
    
- Story Completion Flag.
    

### Postgame

- Повний стан Trial.
    
- General Echo.
    
- Повторний доступ до старого контенту.
    
- World Recovery States.
    
- World Codex.
    

### Definition of Done

Основна кампанія має завершення.

Після фіналу зберігається доступ до дозволеного фарму й нескінченної Вежі Випробувань.

## 19. Етап 12 — Balancing & QA

**Ціль:** перевірити, що всі системи працюють разом.

**Статус:** Not Started.

### Combat

- Manual/Hold/Auto Balance.
    
- Attack Speed Caps.
    
- Cooldown Recovery Caps.
    
- Crit Rules.
    
- RES.
    
- RES Shred.
    
- Penetration.
    
- True Immunity.
    
- Resonance ICD.
    
- Boss Timers.
    
- Status Effects.
    

### Progression

- GG Level Curve.
    
- Gold Upgrade Prices.
    
- Talent Point Supply.
    
- Soul Power.
    
- Rebirth Frequency.
    
- Rebirth Seal.
    
- Permanent Unlocks.
    

### Economy

- Gold Income.
    
- XP Income.
    
- Equipment Drops.
    
- Ore/Metal.
    
- Element Crystals.
    
- Boss Material Drops.
    
- Бойові/квестові нагороди та гарантовані колекційні джерела.
    
- Гарантовані умови отримання Героїв.
    
- Named Soft Pity.
    
- Expedition Rewards.
    
- AFK Rewards.
    

### Characters

- 14 Heroes.
    
- Hero Damage.
    
- Hero Ascension.
    
- 35 Pet Species.
    
- Incubator.
    
- Synthesis.
    
- Pet Stars.
    
- Pet Pair Bonuses.
    

### Quality

- Save/Load.
    
- Save Migration.
    
- No Duplicate Rewards.
    
- Crash Testing.
    
- UI Scaling.
    
- Performance.
    
- Reduced Motion.
    
- Reduced VFX.
    
- Different Screen Ratios.
    

### Definition of Done

Не залишилося критичних помилок, які блокують основний прогрес гри.

Ключові економічні й бойові показники перевірено симуляціями та плейтестами.

## 20. Етап 13 — Steam Release Preparation

**Ціль:** підготувати PC-версію до публікації.

**Статус:** Not Started.

### Технічна підготовка

- Release Export для Windows.
    
- Запуск гри поза редактором Godot.
    
- Перевірка залежностей.
    
- Перевірка збережень.
    
- Перевірка нового Save.
    
- Перевірка оновлення старого Save.
    
- Налаштування версії гри.
    
- Виправлення критичних помилок.
    
- Перевірка ліцензій ассетів.
    

### Steam

- Підготувати Steamworks Account.
    
- Заповнити необхідні дані розробника.
    
- Підготувати сторінку гри.
    
- Підготувати назву та опис.
    
- Підготувати капсули та скриншоти.
    
- Підготувати трейлер, якщо потрібний.
    
- Налаштувати ціну й регіони продажу.
    
- Налаштувати Build Upload.
    
- Перевірити Steam Build.
    
- Провести відповідне тестування.
    
- Виконати актуальні вимоги Steam до публікації.
    

### Steam Features

Після стабільного Core Build:

- Steam Achievements.
    
- Steam Cloud, якщо включений у релізний обсяг.
    
- Особисті рекорди.
    
- Інші підтримувані функції за окремим рішенням.
    

### Обмеження

Деталі реєстрації, платежів, податків, вартості публікації та вимоги платформи необхідно перевіряти за актуальними офіційними правилами Steamworks безпосередньо перед оформленням релізу.

Не вважати цей Roadmap юридичною або податковою інструкцією.

## 21. Порядок реалізації графіки

### Prototype

Тимчасові спрайти.

### Vertical Slice

Перші узгоджені Style References.

### Systems Development

Окремі UI Icons і прості анімації.

### Campaign Expansion

Повноцінні фони, вороги та регіональні набори.

### Celestial Content

Унікальні боси, Генерали, фазові ефекти.

### Release Polish

Фінальні анімації, звуки, оптимізація та перевірка якості.

### Основне правило

Не потрібно чекати створення всіх фінальних спрайтів, щоб тестувати Gameplay.

Але перед масовим виробництвом графіки потрібно затвердити єдиний Art Style.

Повний художній напрям:

[Art Direction](../Art/Art_Direction.md).

## 22. Data-Driven Architecture

Всі основні системи повинні використовувати структуровані дані.

### Приклади

EnemyDefinition:

- ID.
    
- HP.
    
- ATK.
    
- RES.
    
- Loot Table.
    
- Skills.
    
- Art Reference.
    

ItemDefinition:

- ID.
    
- Item Type.
    
- Rarity Rules.
    
- Main Stats.
    
- Affix Pools.
    
- Art Reference.
    

TowerDefinition:

- ID.
    
- Region.
    
- Floors.
    
- Enemy Pools.
    
- Boss Floors.
    
- Unlock Rules.
    

HeroDefinition:

- ID.
    
- Element.
    
- Rarity.
    
- Skills.
    
- Equipment Rules.
    

PetSpecies:

- ID.
    
- Role.
    
- Element Theme.
    
- Bonus.
    
- Skills.
    

### Заборона

Не створювати десятки копій одного Combat Script лише через те, що різні вороги мають різний HP чи вигляд.

## 23. Save System — обов'язкова основа

Save/Load потрібно створити рано, а не залишати наприкінці.

### Мінімальні дані

- Save Version.
    
- Run ID.
    
- GG Level/XP.
    
- Gold.
    
- Inventory.
    
- Equipped Items.
    
- Current Tower.
    
- Current Floor.
    
- Unlock Flags.
    

### Пізніше додаються

- Souls.
    
- Rebirth.
    
- Story Progress.
    
- Quest/Reputation.
    
- Talent Presets.
    
- Heroes.
    
- Pets.
    
- Expeditions.
    
- Trial.
    
- General Echo.
    
- World States.
    

### Основний принцип

Кожний новий модуль зберігає дані через узгоджену систему SaveData.

Не створювати незалежний випадковий файл збереження для кожної механіки.

## 24. Save Migration

Коли структура SaveData змінюється:

1. Визначити стару версію.
    
2. Визначити нову версію.
    
3. Описати зміну полів.
    
4. Додати Migration Rule.
    
5. Створити тестовий Save старої версії.
    
6. Перевірити завантаження.
    
7. Перевірити збереження прогресу.
    

### Заборони

- Не видаляти старі поля без перевірки.
    
- Не перезаписувати Save порожнім станом через помилку.
    
- Не ламати прогрес після оновлення.
    
- Не змінювати Stable IDs без міграції.
    

## 25. Система тестування

Тести потрібні на кожному етапі.

### Unit Tests

Для чистої логіки:

- Damage.
    
- RES.
    
- XP.
    
- Gold.
    
- Crafting Costs.
    
- Drop Rolls.
    
- Soul Calculations.
    
- Reputation.
    
- Element Thresholds.
    

### Integration Tests

Для взаємодії:

- Combat + Equipment.
    
- Combat + Resonance.
    
- Combat + Hero.
    
- Combat + Pet.
    
- Inventory + Forge.
    
- Boss + Rewards.
    
- Rebirth + Save.
    
- Expedition + Hero.
    
- Story Unlock + World Map.
    

### Manual Tests

Для:

- UI.
    
- Анімацій.
    
- Відчуття удару.
    
- Читабельності.
    
- Boss Telegraphs.
    
- Балансу.
    
- Продуктивності.
    

### Regression Tests

Після великих змін повторно перевіряти вже робочі системи.

## 26. Test Scenes

Рекомендується створити окремі тестові сцени або інструменти для перевірки:

- Basic Combat.
    
- Boss Combat.
    
- Damage Calculator.
    
- Element/Resonance.
    
- Inventory.
    
- Forge.
    
- Talent Tree.
    
- Hero.
    
- Pet.
    
- Save/Load.
    
- Rebirth.
    
- Loot Simulation.
    

### Правило

Test Scene не повинна автоматично бути частиною фінального меню гравця.

Потрібне розмежування Development Tools і Release Build.

## 27. Балансні симуляції

Необхідно проводити симуляції прогресії.

### Перевірки

- Скільки часу займає перша Башта.
    
- Скільки Gold потрібно для Upgrade.
    
- Як часто випадає корисне спорядження.
    
- Яка середня швидкість Rebirth.
    
- Наскільки сильний Soul Power.
    
- Чи можна пройти босів без вузького обов'язкового білду.
    
- Чи збалансовані Manual/Auto.
    
- Чи не стають економічні пети обов'язковими.
    
- Чи відповідає доступність спеціальних матеріалів цінам Кузні.
    

### Цілі GDD — Balance v1

Перша Башта 141:

Приблизно 4–6 год першого проходження з навчанням та фармом.

Повторні проходження:

Орієнтовно 1–3 год, а за сильного розвитку — 15–45 хв.

### Статус

Це цільові орієнтири балансу.

Вони не є гарантованим часом для всіх гравців.

## 28. Definition of Done для будь-якої задачі

Будь-яка задача вважається завершеною лише за виконання умов:

- Реалізовано запитану функцію.
    
- Код відповідає канону.
    
- Немає критичних Godot Errors.
    
- Функція перевірена.
    
- Не зламано попередні системи.
    
- Дані не дублюються.
    
- Save/Load працює, якщо задача змінює стан.
    
- UI показує відповідний результат.
    
- Зміни описані в Task Log.
    
- Немає неузгоджених нових механік.
    

### Головний принцип

Задача не є завершеною тільки тому, що Claude Code написав код.

Потрібна перевірка роботи.

## 29. Протокол роботи з Claude Code

### Перед задачею

Claude Code повинен:

1. Прочитати відповідний документ.
    
2. Прочитати пов'язані правила.
    
3. Перевірити поточний Task Log.
    
4. Перевірити існуючі файли.
    
5. Скласти короткий план змін.
    
6. Вказати, які файли змінюватимуться.
    

### Під час задачі

Claude Code повинен:

- Змінювати лише необхідні файли.
    
- Не переписувати цілу систему без потреби.
    
- Використовувати існуючі класи та дані.
    
- Не додавати непогоджені механіки.
    
- Не змінювати Canon Rules.
    
- Зберігати стабільні IDs.
    
- Не хардкодити Balance Values всередині UI.
    

### Після задачі

Claude Code повинен:

1. Перевірити синтаксис.
    
2. Перевірити запуск або повідомити, якщо перевірка недоступна.
    
3. Назвати змінені файли.
    
4. Описати виконані функції.
    
5. Описати відомі помилки.
    
6. Запропонувати конкретні кроки ручного тестування.
    
7. Оновити Task Log після підтвердження результату.
    

## 30. Формат однієї задачі

Рекомендований шаблон для Claude Code:

**Task ID:** DEV-001

**Назва:** Basic Enemy HP.

**Мета:** ворог отримує шкоду та помирає.

**Документи:**

- Combat.
    
- Enemies.
    
- Core Rules.
    

**Обсяг:**

- Enemy HP.
    
- Damage Event.
    
- Death State.
    

**Не входить:**

- Loot Tables.
    
- Boss Mechanics.
    
- Elemental Resonance.
    

**Definition of Done:**

- HP зменшується після удару.
    
- Death спрацьовує один раз.
    
- Немає критичних помилок.
    

**Після завершення:**

- Список змінених файлів.
    
- Інструкція тестування.
    
- Відомі обмеження.
    

### Принцип

Одна задача повинна мати конкретні межі.

Не об'єднувати в ній десять незалежних систем.

## 31. Статуси задач

Використовувати єдині статуси:

|Status|Значення|
|---|---|
|Planned|Задача запланована|
|Ready|Вимоги готові|
|In Progress|Реалізація триває|
|Blocked|Є залежність або проблема|
|Testing|Функція перевіряється|
|Done|Завершена та перевірена|
|Rework|Потрібне виправлення|

### Правило

Не змінювати статус `Done`, поки задача не пройшла перевірку.

## 32. Task Log

Кожна робоча сесія повинна залишати короткий запис.

### Приклад

**Session:** 001.

**Tasks:**

- DEV-001: Basic Enemy HP.
    
- DEV-002: Manual Attack.
    

**Modified Files:**

- Відповідні фактично змінені файли.
    

**Result:**

- Реалізовані функції.
    
- Проведені тести.
    
- Поточні помилки.
    

**Next:**

- Одна наступна конкретна задача.
    

### Повна структура

[Task Log](Task_Log.md).

## 33. Decisions Log

Важливі рішення повинні фіксуватися окремо.

### Приклади

- Яку техніку 2D-малювання вибрано.
    
- Яку архітектуру SaveData затверджено.
    
- Як організовані Hero Weapons.
    
- Які Balance Values змінені після плейтестів.
    
- Який алгоритм Animation State вибрано.
    
- Як вирішено суперечності специфікацій.
    

### Правило

Roadmap не потрібно перетворювати на архів усіх технічних дискусій.

Він визначає порядок розробки.

[Decisions](Decisions.md) зберігає пояснення важливих змін.

## 34. Робота із суперечностями

Якщо Claude Code знаходить суперечність між документами:

1. Не вибирати випадковий варіант.
    
2. Знайти відповідну спеціалізовану Bible.
    
3. Перевірити останнє затверджене рішення.
    
4. Якщо відповідь усе ще неочевидна — позначити питання як Blocked.
    
5. Попросити рішення розробника.
    
6. Зафіксувати його в Decisions.
    
7. Синхронізувати залежні документи.
    

### Заборона

Не змінювати механіку мовчки лише тому, що інший варіант простіше запрограмувати.

## 35. Управління ризиками

### RISK-01 — Надто великий початковий обсяг

Рішення:

Почати з одного слайма та перших 20 поверхів.

### RISK-02 — Нестабільна архітектура

Рішення:

Створити Foundation, стабільні IDs та Data-Driven конфігурації.

### RISK-03 — Втрата прогресу

Рішення:

Save/Load, Backups, Versioning і Git.

### RISK-04 — Суперечності документації

Рішення:

Спеціалізовані Bible, Decisions, перевірка перед реалізацією.

### RISK-05 — Перевантажений арт

Рішення:

Art Prototype та єдиний Style Reference.

### RISK-06 — Надмірний балансний ріст

Рішення:

Симуляції HP/DPS/Gold/Souls.

### RISK-07 — Нескінченні нагороди

Рішення:

Atomic Reward Claims і стабільні First-Clear Flags.

### RISK-08 — Втрата Save при оновленні

Рішення:

Save Migration та Compatibility Tests.

### RISK-09 — Неконтрольовані зміни Claude Code

Рішення:

Малі задачі, погодження плану, перевірка файлів, Git Commits.

### RISK-10 — Дуже довга розробка

Рішення:

Завершувати контрольні версії й не вимагати весь фінальний контент для першого тестового білдів.

## 36. Важливі обмеження канону

Claude Code не повинен змінювати:

- Сім стихій.
    
- 21 подвійний резонанс.
    
- 35 потрійних резонансів.
    
- 12 слотів ГГ.
    
- Шість слотів союзного Героя.
    
- 14 союзних Героїв.
    
- 35 видів вихованців.
    
- Два активні Pet Slots.
    
- Чотири Active Skill Slots ГГ.
    
- 21 Башту Ув'язнення.
    
- 141 поверх кожної Башти.
    
- Сім Небесних Веж.
    
- 666 поверхів кожної.
    
- Сім Генералів.
    
- Сім стихійних Данжів.
    
- Одну Infinite Trial Tower.
    
- Каталог 120 вузлів Talent Tree; кількість для релізу перевіряється експериментально.
    
- Відкриття Auto Attack після першої перемоги над босом 20 Башти 01-I.
    
- Story Unlock Conditions.
    
- Rebirth Keep/Reset Rules.
    
- Guardian та General Material Rules.
    

Усі відповідні деталі потрібно брати з документації, а не з цього короткого переліку.

## 37. Що не потрібно робити на початку

Не потрібно одразу:

- Створювати всі 21 Башту.
    
- Малювати всіх 14 Героїв.
    
- Малювати всіх 35 вихованців.
    
- Створювати всі 147 базових Mob Variants.
    
- Реалізовувати сім Генералів.
    
- Додавати всі 120 Talent Nodes одночасно.
    
- Створювати повну World Map з фінальним артом.
    
- Підключати всі Steam Features.
    
- Створювати повний музичний супровід.
    
- Писати весь фінальний сюжет.
    
- Створювати власний сервер.
    
- Встановлювати жорсткі строки релізу без перевірки обсягу робіт.
    

### Основний принцип

Не масштабувати кількість контенту, поки базова архітектура не довела свою працездатність.

## 38. Критерії першої придатної до гри версії

Перший якісний Vertical Slice повинен забезпечувати:

- Стабільний бій.
    
- Зрозумілу шкоду.
    
- Читабельний HP.
    
- Відчутний Hit Feedback.
    
- Зрозумілу винагороду.
    
- Базову прокачку.
    
- Мінімальний інвентар.
    
- Робочий Boss Timer.
    
- Відповідний Save/Load.
    
- Візуальну цілісність.
    
- Відсутність критичних помилок.
    

### Головне питання

Чи хоче гравець пройти ще один поверх і купити наступний апгрейд?

Якщо відповідь негативна, потрібна робота над Core Combat, а не додавання ще десяти систем.

## 39. Критерії завершення повної розробки

### Gameplay

- Основний цикл працює.
    
- Усі затверджені системи реалізовані.
    
- FTUE відповідає канону.
    
- Кампанію можна завершити.
    
- Rebirth працює.
    
- Endgame доступний.
    
- Hero/Pet Systems працюють.
    
- Forge/Equipment/Resonances працюють.
    

### World

- Сім регіонів.
    
- 21 Башта.
    
- Сім Небесних Веж.
    
- Сім Данжів.
    
- Сім Генералів.
    
- Король Демонів.
    
- Infinite Trial.
    

### Technical

- Save/Load.
    
- Stable IDs.
    
- Save Migration.
    
- Data-Driven Content.
    
- Немає критичних помилок.
    
- Стабільна продуктивність.
    
- Масштабований UI.
    

### Art

- Єдиний Style Reference.
    
- Читабельні предмети.
    
- Стихійні VFX.
    
- Читабельні Boss Telegraphs.
    
- Анімовані фони.
    
- Коректні UI Icons.
    
- Перевірені ліцензії.
    

### Steam

- Готовий Release Build.
    
- Протестовано запуск поза Godot.
    
- Підготовлено Store Assets.
    
- Підготовлено опис.
    
- Виконано актуальні Steamworks Requirements.
    
- Завершено релізне тестування.
    

## 40. Milestone Tracking

Використовувати такі контрольні позначки:

|Milestone|Стан|
|---|---|
|M00 — Environment Ready|Not Started|
|M01 — Foundation Ready|Not Started|
|M02 — First Combat|Not Started|
|M03 — Floors 1–20|Not Started|
|M04 — Floors 21–40|Not Started|
|M05 — Systems Slice|Not Started|
|M06 — First Tower 141|Not Started|
|M07 — Rebirth & World|Not Started|
|M08 — First Triad|Not Started|
|M09 — Seven Regions|Not Started|
|M10 — Celestial Towers|Not Started|
|M11 — Endgame & Finale|Not Started|
|M12 — Balancing & QA|Not Started|
|M13 — Steam Release|Not Started|

### Правило оновлення

Після завершення кожного Milestone:

1. Перевірити Definition of Done.
    
2. Перевірити фактичні тести.
    
3. Оновити Task Log.
    
4. Оновити поточний статус.
    
5. Створити Git Commit.
    
6. Лише після цього перейти до наступного Milestone.
    

## 41. Перші конкретні задачі

Це рекомендований початковий Backlog.

### DEV-001

Створити Godot Project.

### DEV-002

Налаштувати VS Code.

### DEV-003

Налаштувати Claude Code.

### DEV-004

Підключити `docs/`.

### DEV-005

Створити Git Repository.

### DEV-006

Створити Main Scene.

### DEV-007

Створити Combat Scene.

### DEV-008

Створити Enemy Definition.

### DEV-009

Додати HP слайма.

### DEV-010

Додати Manual Attack.

### DEV-011

Додати Hold Attack.

### DEV-012

Додати Death State.

### DEV-013

Додати Gold Reward.

### DEV-014

Додати Base Gold Upgrade.

### DEV-015

Створити перший Save/Load Test.

### Важливе правило

Цей Backlog можна уточнити після вибору остаточної структури Godot-проєкту.

Не запускати всі 15 задач одним великим промптом.

## 42. Перший робочий результат

Найближча технічна ціль:

**Один робочий бій зі слаймом у Godot.**

Він повинен демонструвати:

1. Ворог з'являється.
    
2. Гравець натискає.
    
3. Ворог отримує шкоду.
    
4. HP зменшується.
    
5. Ворог помирає.
    
6. Гравець отримує Gold.
    
7. Система переходить до наступного Encounter.
    

Досягнення цієї цілі важливіше за будь-яку кількість декоративних ассетів.

## 43. Заборони для Claude Code

Без погодження розробника заборонено:

- Реалізовувати всю гру одним запитом.
    
- Переписувати існуючий Godot Project без пояснення.
    
- Видаляти працездатні системи.
    
- Створювати дубльовані менеджери.
    
- Змінювати Canon Mechanics.
    
- Змінювати кількість основного контенту.
    
- Змінювати FTUE Unlocks.
    
- Хардкодити Balance Values у UI.
    
- Додавати нові бойові класи.
    
- Створювати нові типи зброї без погодження.
    
- Додавати незатверджені ресурси.
    
- Створювати незалежні несумісні Save Systems.
    
- Змінювати Stable IDs без Migration.
    
- Скидати Permanent Progress після Rebirth.
    
- Дублювати Loot/Rewards.
    
- Пропускати перевірку після складних змін.
    
- Позначати задачі Done без тестування.
    
- Змінювати документацію мовчки.
    
- Вважати незатверджений Balance v1 фінальним.
    
- Самостійно встановлювати дату релізу.
    
- Переходити до Steam Release без стабільного Build.
    

## 44. Залежності між документами

### Roadmap

Визначає порядок роботи.

### Task Log

Фіксує фактично виконану роботу.

### Decisions

Фіксує архітектурні та геймдизайнерські рішення.

### Core Rules

Визначає канонічні обмеження.

### Systems/World/Characters

Визначають технічні й ігрові правила окремих систем.

### Art Direction

Визначає художню мову та правила виробництва ассетів.

### Важлива відмінність

Roadmap не замінює жодну спеціалізовану Bible.

Він лише визначає, коли та в якому порядку відповідні системи реалізовувати.

## 45. Фінальний принцип розробки

Успіх гри залежить не від того, наскільки швидко будуть створені всі файли, а від якості й стабільності основного ігрового циклу.

Пріоритет:

1. Працездатність.
    
2. Правильність механік.
    
3. Відчуття прогресу.
    
4. Читабельність.
    
5. Стабільність збережень.
    
6. Баланс.
    
7. Візуальна цілісність.
    
8. Масштабування.
    
9. Оптимізація.
    
10. Реліз.
    

---

**Статус документа:** Development Roadmap — Draft.

**Стан реальної розробки:** Not Started.

**Основний рушій:** Godot 4.

**Редактор:** VS Code.

**AI-інструмент:** Claude Code.

**Основна платформа:** PC / Steam.

**Найближчий Milestone:** M00 — Environment Ready.

**Перша ігрова ціль:** M02 — First Combat.

**Перший повноцінний зріз:** M03 — Floors 1–20.

**Головне правило:** невеликі задачі, перевірки після кожного кроку, дотримання затвердженої документації та збереження працездатності проєкту.

## 46. Затверджені уточнення плану — 2026-11-04

### Обсяг

- Повний кінцевий реліз зберігає 7 регіонів, 49 сімейств / 147 базових мобів, 14 союзних Героїв і 35 видів петів. Каталоги не скорочені.
- Прототип/демо розвиваються невеликими зрізами. Їхній піднабір не є обіцянкою скороченого фінального релізу.
- Каталог талантів поки має 120 вузлів; практично порівняти 30–40, 100–120 і лише за потреби близько 140. Протокол — Talents §34. Фінальний обсяг OPEN.

### Перший бойовий зріз 1–20

1. Базові удари мобів та читабельна смужка; перевірка attack_period відносно kill time.
2. Навчальна utility_interrupt на Floor 10 в одному з чотирьох слотів.
3. Каст Слизного Короля: успішний Interrupt, пропуск вікна, захист від повторного переривання, базові удари після касту.
4. Метеор на окремому тестовому loadout для перевірки Impact Sync. Це не відкриває Fire-канал чи Метеор без прогресійних умов у звичайному збереженні.
5. Auto Attack після першої перемоги над босом 20; перемикач і постійне збереження відкриття.
6. Візуальна зміна зброї ГГ; незмінний одяг при заміні броні/аксесуарів.

### Колекції та економіка

Прибрати магазин випадкових Chest I/II/III та Hero Rolls. Реалізувати гарантовані квести/досягнення й пряму купівлю конкретних Героїв за Souls, персональні випробування для Sigils та гарантовані Special Pet квести/випробування. Точні ціни, квестові пороги, encounter IDs і кількості Special Essence залишаються задачами Content/Balance v1; до їх заповнення відповідна функція не позначається готовою.

### Ціна й рішення після демо

Ціна релізу та стартова знижка не зафіксовані. Попередньо обговорені $7.99 і 10% — лише історичний орієнтир, не затверджені налаштування. Повернутися до рішення після демо та фестивалів: оцінити число гравців, проходження/повторні запуски демо, відгуки про задоволення й темп, інтерес до купівлі та фактичний стан контенту. Кількість wishlist сама по собі не доводить готовність платити певну ціну.

### Обов'язкові перевірки нових правил

- Рання автоматизація не ламає доходи та темп першого Rebirth.
- Звичайний фарм доступний без ручного Interrupt; HP/DEF/RES мають значення.
- Переривання не скидає накопичений swing і не блокує боса нескінченно.
- Уламки однієї навички не переривають кілька кастів; мертвий target не переносить снаряд на наступного ворога.
- Reduced Motion/VFX та зміна частоти кадрів не змінюють бойові події.
- Є гарантовані джерела кожного Героя, Sigil, спеціального пета та матеріалу його розвитку; повторні claim не дублюють нагороди.
- Профілі талантів не мають недосяжних prerequisites; результати дослідження записуються окремо від припущень.
