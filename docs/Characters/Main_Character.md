---

status: draft  
document_type: main-character  
source: GDD v2.3, Combat Bible v1.2, Equipment Bible v1.2, Talent Tree Bible v1.1, Lore & Art Bible v2.2  
content_status: Content v1  
balance_status: Balance v1  
updated: 2026-11-04
tags:

- characters
    
- main-character
    
- combat
    
- equipment
    
- progression
    
- godot
    

revision: approved-changes-2026-11-04
---

# MAIN CHARACTER — Головний Герой

> Редакція 2026-11-04: затверджені зміни за [Decisions](../Development/Decisions.md) мають пріоритет над суперечними правилами попередніх Word Bible. Оновлено документацію; реалізацію та ігровий баланс не перевірено.

> Повна специфікація Головного Героя: сюжетна роль, бойові характеристики, атаки, 12 слотів екіпірування, два стихійні канали, чотири активні слоти, резонанси, рівні, таланти, взаємодія з Героями та вихованцями, Rebirth і збереження прогресу.
> 
> Джерела: GDD v2.3, Combat System Design Bible v1.2, Resources, Equipment & Accessories Bible v1.2, Talent Tree & Progression Bible v1.1, Story, Lore & Art Bible v2.2.
> 
> Структура персонажа та затверджені правила — Canon. Числові характеристики й коефіцієнти — Balance v1. Фінальна зовнішність, анімації й окремі художні деталі потребують затвердження.

## 1. Загальна концепція

Головний Герой — центральний персонаж, яким розвивається гравець.

За сюжетом він є Новим Обранцем, молодим воїном, що отримав найщільніший уламок духовної спадщини Прадавнього Героя.

На початку гри протагоніст не розуміє повної природи своєї сили.

Його супроводжує Дух Полеглого Героя, який поступово відновлює власні спогади та допомагає розібратися у світі.

### Унікальна властивість ГГ

Головний Герой може підтримувати два стабільні стихійні канали завдяки особливому духовному ядру.

Це дозволяє:

- Змінювати стихії через екіпірування.
    
- Використовувати різні бойові спеціалізації.
    
- Формувати подвійні резонанси.
    
- Взаємодіяти зі стихією союзного Героя.
    
- Отримувати потрійні резонанси.
    
- Використовувати моностихійні білди.
    
- Перебудовувати персонажа під слабкості ворогів.
    

### Канонічне обмеження

ГГ не має фіксованого бойового класу.

Немає обов'язкового вибору Warrior / Mage / Archer, який назавжди визначає доступні стихії або зброю.

Білд формується спорядженням, талантами, навичками, Soul Progression і союзниками.

## 2. Роль у бойовій системі

Головний Герой:

- Є основним керованим персонажем.
    
- Завдає шкоди кліком.
    
- Завдає шкоди утриманням ЛКМ.
    
- Після відповідного сюжетного відкриття використовує Auto Attack.
    
- Має чотири активні бойові слоти.
    
- Отримує шкоду від ворогів.
    
- Має власні HP, DEF і RES.
    
- Може отримувати Stun, Silence та інші статуси.
    
- Використовує спорядження з 12 слотів.
    
- Формує Primary і Secondary Element Channels.
    
- Отримує XP та підвищує рівень.
    
- Розвивається через Gold Upgrades.
    
- Використовує Run Talent Tree.
    
- Посилюється через Soul Skills, Relics і Rebirth.
    

### Формат управління

Бойова система — 2D Clicker / Incremental Action RPG.

Гравець не пересуває ГГ по арені через WASD.

Основна взаємодія відбувається через:

- Натискання на ворога.
    
- Утримання кнопки атаки.
    
- Кнопки активних навичок.
    
- Перемикання відповідних режимів.
    
- Налаштування білдів.
    

Не створювати повноцінну систему вільного руху персонажа без окремого рішення.

## 3. Базові характеристики

### 3.1. Основні характеристики

|Характеристика|Призначення|
|---|---|
|ATK|Основна атакувальна сила|
|Max HP|Максимальне здоров'я|
|Current HP|Поточне здоров'я|
|DEF|Базовий фізичний захист|
|Physical RES / Mitigation|Зменшення фізичної шкоди|
|Crit Rate|Імовірність критичного удару|
|Crit DMG|Бонус критичної шкоди|
|Attack Speed|Частота відповідних атак|
|Skill Damage|Посилення активних навичок|
|Cooldown Recovery|Прискорення відновлення навичок|
|Elemental Damage|Посилення відповідних стихійних пакетів|
|Elemental Penetration|Робота проти позитивного стихійного RES|
|Resonance Damage|Посилення дозволених резонансів|
|DoT Damage|Посилення періодичної шкоди|
|Combo Gain|Швидкість накопичення Combo|
|HP Regen|Відновлення здоров'я|

### 3.2. Сім стихійних RES

ГГ має окремий захист від:

1. Fire.
    
2. Water.
    
3. Nature.
    
4. Light.
    
5. Dark.
    
6. Lightning.
    
7. Wind.
    

Фізичний захист обробляється окремо.

### 3.3. RES Cap

Рекомендований звичайний Elemental RES Cap для ГГ:

75% — Balance v1.

Це не True Elemental Immunity.

ГГ не отримує абсолютного імунітету до стихії лише тому, що накопичив багато RES через спорядження.

### 3.4. Принцип характеристик

Базові ATK, HP і DEF ростуть від рівня ГГ.

Екіпірування, таланти та інші модифікатори застосовуються поверх базових характеристик.

Не зберігати лише фінальне ATK як єдине джерело даних персонажа.

## 4. Рівень Головного Героя

ГГ отримує XP від перемог над відповідними ворогами.

### Формула XP — Balance v1

`XP_to_next(L) = floor(50 × 1.13^(L−1) × (1 + 0.025 × floor((L−1)/10)))`

Де L — поточний рівень.

### Формули базових характеристик — Balance v1

`BaseATK(L) = 10 × 1.025^(L−1)`

`BaseHP(L) = 100 × 1.03^(L−1)`

`BaseDEF(L) = 5 × 1.02^(L−1)`

### Початкові параметри Lv1

- Base ATK: 10.
    
- Base HP: 100.
    
- Base DEF: 5.
    
- XP для наступного рівня: 50.
    

### Контрольні значення

|Level|Base ATK|Base HP|Base DEF|
|---|---|---|---|
|1|10.0|100.0|5.0|
|10|12.5|130.5|6.0|
|25|18.1|203.3|8.0|
|50|33.5|425.6|13.2|
|75|62.2|891.2|21.6|
|100|115.3|1 865.9|35.5|
|150|396.1|8 179.9|95.6|

### Важливі правила

- Hero XP союзного Героя — окрема шкала.
    
- Pet XP — окрема постійна шкала.
    
- Рівень ГГ скидається після Rebirth.
    
- Поточний XP ГГ також скидається.
    
- Фінальні характеристики залежать від усіх чинних модифікаторів.
    

Не встановлювати новий максимальний рівень ГГ без погодження.

## 5. Джерела сили ГГ

Сила персонажа формується кількома незалежними системами.

### Run Progression

- GG Level.
    
- Gold Upgrades.
    
- Run Talents.
    
- Тимчасові бойові ефекти.
    

### Equipment Progression

- 12 слотів.
    
- Rarity.
    
- Rank.
    
- Upgrade.
    
- Main Stats.
    
- Affixes.
    
- Elemental Enchantment.
    
- Named/Mythic Traits.
    

### Permanent Progression

- Total Souls Collected.
    
- Soul Power.
    
- Soul Skills.
    
- Soul Relics.
    
- Інші явно затверджені постійні бонуси.
    

### Team Contribution

- Один активний союзний Герой.
    
- До двох активних вихованців.
    
- Reaction Focus.
    
- Дозволені Hero/Pet Bonuses.
    

### Принцип

Жодне джерело сили не повинно застосовуватися двічі лише тому, що згадується в кількох документах.

## 6. Ручна атака — Manual Attack

Manual Attack — базова форма бою з першого поверху.

### Управління

Гравець натискає на ворога ЛКМ.

Кожен дозволений клік створює базовий удар.

### Характеристики

На шкоду впливають:

- Base ATK.
    
- ATK%.
    
- Attack Coefficient.
    
- Weapon Stats.
    
- Crit.
    
- Physical Damage Modifiers.
    
- Elemental Channels.
    
- Elemental Weapon Packets.
    
- Target RES.
    
- Manual Talent Bonuses.
    
- Soul Power.
    

### Важливе правило

Ручний удар не повинен повністю ігнорувати Physical або Elemental RES ворога.

### Частота

Має існувати контроль допустимої частоти атак.

Не дозволяти програмно генерувати необмежену кількість ударів без дотримання Attack Cadence.

Точні часові межі визначає Combat/Balance Config.

## 7. Hold Attack

Hold Attack дозволяє завдавати повторюваних ударів утриманням ЛКМ.

### Канон

- Доступний із початку гри.
    
- Не вимагає постійного фізичного спаму миші.
    
- Використовує обмежену частоту.
    
- Отримує бонуси Manual/Hold.
    
- Може розвивати Combo.
    
- Не є Auto Attack Unlock.
    

### Важлива відмінність

Hold Attack працює, коли гравець утримує кнопку.

Auto Attack — окрема механіка, яка може працювати без постійного утримання.

### Баланс

Manual/Hold повинен залишатися цінним для активного гравця навіть після відкриття Auto Attack.

## 8. Auto Attack

### Умова відкриття

Базова Auto Attack відкривається після першої перемоги над Зональним босом на поверсі 20 Башти 01-I. Відкриття постійне, зберігається після Rebirth; доступний перемикач увімкнення/вимкнення. Вхід у 01-II більше не є умовою відкриття.

### Постійність

Відкриття зберігається після Rebirth.

### Початкова сила — Balance v1

Базовий Auto Direct Hit:

приблизно 50% відповідного Manual Direct Hit.

### Модифікатори

Auto Attack може посилюватися через:

- Gold Upgrades.
    
- Equipment.
    
- Attack Speed.
    
- Talent Tree.
    
- Soul Skills.
    
- Hero/Team Synergies.
    

### Обмеження

- Не відкривати Auto Attack на Floor 10.
    
- Не відкладати Auto Attack до Guardian 141 або входу в 01-II.
    
- Не скидати Unlock після Rebirth.
    
- Не дозволяти автоматичним ударам обходити Combat Caps.
    
- Не плутати Auto Attack з Auto Progress Башт.
    

## 9. Combo System

Combo підтримує активний Manual/Hold Playstyle.

### Джерела розвитку

- Manual/Hold Hits.
    
- Combo Gain Modifiers.
    
- Talent Tree.
    
- Відповідні Elemental Bonuses.
    
- Дозволені Active Skills.
    

### Приклади взаємодії

Вітер:

+10% Combo Gain — Balance v1, якщо базовий бонус Wind активний.

Manual/Combo Talents:

Можуть посилювати частоту накопичення, Combo Cap і відповідні удари.

### Обмеження

- Combo не повинно нескінченно множити шкоду.
    
- Combo Caps визначаються бойовою системою та талантами.
    
- Немає підстав вважати, що Auto Attack автоматично має всю ту саму Combo-поведінку без явного правила.
    
- Точну базову формулу Combo потрібно брати з Combat/Talent Config.
    

## 10. Чотири активні бойові слоти

ГГ має рівно чотири Active Skill Slots.

### Можливі типи навичок

- Elemental Active Skills.
    
- Active Soul Skills.
    
- Active Talent Skills.
- Навчальна utility_interrupt.
    

### Каталог кандидатів

- 14 базових стихійних активних навичок.
    
- 4 Active Soul Skills.
    
- 3 Active Talent Skills.
- 1 навчальна utility_interrupt.
    

Разом 22 кандидати з урахуванням utility_interrupt; одночасно екіпіровано максимум чотири навички.

### Канон

- Активними одночасно є максимум чотири екіпіровані навички.
    
- Кожна використовує відповідний cooldown.
    
- Навички займають спільні слоти.
    
- Talent Skills не створюють окрему додаткову панель.
    
- Soul Skills не створюють п'ятий слот.
    
- Доступність залежить від Unlock Conditions.
    
- Mutations не створюють новий слот.
    

### Типи ефектів

- Burst.
    
- DoT.
    
- Debuff.
    
- Buff.
    
- Tempo.
    
- Resonance.
    
- Defense / Utility.

- Interrupt (переривання касту активної здібності ворога/боса).

### Візуальне виконання навичок ГГ (Projectile Impact Sync)

- Активні навички типу падіння або снаряда (наприклад, **Метеор**) мають видиму фазу підльоту в ціль на бойовій сцені.
- Нанесення шкоди, спрацювання `Interrupt` по смужці касту ворога та поява візуального імпакту відбуваються в момент фактичного зіткнення снаряда з ворогом.
    

## 11. Сім стихій ГГ

Головний Герой може використовувати всі сім стихій.

|Стихія|Роль|Базовий бонус Balance v1|
|---|---|---|
|Fire|Burst / DoT|+8% Skill Damage; Fire DoT Duration +5%|
|Water|Flow / Utility|+8% Cooldown Recovery|
|Nature|DoT / Growth|+12% DoT Damage|
|Light|Crit / Purity|+6% Crit Rate для Elemental/Resonance|
|Dark|Execute / Corruption|+12% Crit DMG; +5% шкоди цілям нижче 30% HP|
|Lightning|Speed / Multi-hit|+8% Attack Speed для Manual/Hold/Auto|
|Wind|Tempo / AoE|+10% Combo Gain; +10% AoE Coverage|

### Принцип

Стихія — не фіксований клас персонажа.

Вибір стихій визначається екіпіруванням і відповідними порогами.

### Anti-Stack

Базовий бонус стихії активується, якщо вона присутня хоча б в одному активному каналі ГГ.

Якщо Primary і Secondary мають одну стихію, її базовий бонус не подвоюється.

Замість Core Resonance застосовується Dual Alignment.

Повні правила:

[Elements](../Systems/Elements.md).

## 12. Дванадцять слотів екіпірування

ГГ має рівно 12 слотів.

### 12.1. Основна броня — 5 слотів

1. Helmet.
    
2. Chest.
    
3. Gloves.
    
4. Pants.
    
5. Boots.
    

Призначення:

- Виживання.
    
- Основні defensive stats.
    
- Частково offensive stats.
    
- Primary Element Channel.
    

### 12.2. Озброєння та допоміжне спорядження — 3 слоти

6. Weapon.
    
7. Shield / Defensive Off-hand.
    
8. Cloak.
    

Призначення:

- Direct Damage.
    
- Attack Style.
    
- Defense.
    
- Utility.
    
- Boss Damage.
    
- Skill Modifiers.
    

Ці три слоти не створюють нового Core/Hero Resonance Channel.

### 12.3. Аксесуари — 4 слоти

9. Amulet.
    
10. Ring.
    
11. Belt.
    
12. Earrings.
    

Призначення:

- Build Specialization.
    
- Crit.
    
- Attack Speed.
    
- Elemental Damage.
    
- Skill Damage.
    
- Resonance Damage.
    
- Secondary Element Channel.
    

### Контроль кількості

`5 Armor + 3 Armament + 4 Accessories = 12 Slots`

Не додавати 13-й слот для сюжетного Прадавнього Клинка.

## 13. Primary Element Channel

Primary Element Channel формується основною бронею.

### Умова

Щонайменше чотири з п'яти слотів броні повинні мати зачарування однієї стихії.

`Primary Threshold = 4/5`

### Приклад

- Helmet: Fire.
    
- Chest: Fire.
    
- Gloves: Fire.
    
- Pants: Fire.
    
- Boots: Water.
    

Результат:

Primary Element = Fire.

### Неповний поріг

Якщо є лише 3/5 предметів із Fire Enchantment:

Primary Fire Channel не активується.

Предмети все ще дають власні характеристики.

Не можна активувати канал лише через один потужний Legendary або Mythic предмет.

## 14. Secondary Element Channel

Secondary Element Channel формується аксесуарами.

### Умова

Щонайменше три з чотирьох аксесуарів мають зачарування однієї стихії.

`Secondary Threshold = 3/4`

### Приклад

- Amulet: Water.
    
- Ring: Water.
    
- Belt: Water.
    
- Earrings: Light.
    

Результат:

Secondary Element = Water.

### Неповний поріг

Якщо лише 2/4 аксесуарів мають Water:

Secondary Water Channel не активується.

### Важливі правила

- Primary і Secondary розраховуються незалежно.
    
- Для кожного каналу зберігається свій Elemental Contribution.
    
- Обидва канали можуть бути різними.
    
- Обидва канали можуть бути однаковими.
    
- Неповний канал не утворює Core Resonance.
    

## 15. Weapon Elemental Damage

Стихійна зброя може додавати окремий Elemental Damage Packet.

### Приклад 1

ГГ:

- Primary: Fire.
    
- Secondary: Water.
    
- Weapon: Dark.
    

Результат:

- Core Resonance: Fire + Water.
    
- Зброя завдає додаткового Dark Damage.
    
- Dark Weapon не створює третього каналу.
    
- Dark Weapon не створює нового Hero/Triad Resonance.
    

### Приклад 2

ГГ:

- Primary: Dark.
    
- Secondary: Water.
    
- Weapon: Dark.
    

Результат:

- Core Resonance: Dark + Water.
    
- Dark Weapon отримує дозволені бонуси відповідної стихії.
    

### Обмеження

- Зброя не створює третій стихійний канал ГГ.
    
- Зброя не може автоматично формувати потрійний резонанс.
    
- Стихія зброї не замінює вроджену стихію союзного Героя.
    

## 16. Dual Alignment

Якщо два активні канали ГГ мають однакову стихію:

`Primary = Secondary`

Замість Core Resonance активується Dual Alignment.

### Balance v1

- +10% Damage відповідної стихії.
    
- +5% Elemental Penetration для неї.
    

### Правила

- Елементальні внески обох каналів зберігаються.
    
- Core Resonance між однаковими стихіями не утворюється.
    
- Базовий бонус стихії не подвоюється.
    
- Немає нового окремого каналу.
    

Dual Alignment дозволяє створювати вузькоспеціалізовані mono-element білди.

## 17. Core Resonance

Якщо Primary та Secondary активні і різні:

`Primary != Secondary`

Формується Core Resonance.

### Канон

- Core Resonance використовує дві різні стихії ГГ.
    
- Серед семи стихій існує 21 можлива неупорядкована пара.
    
- Ефекти визначає Combat Bible.
    
- Базовий Internal Cooldown: 1.0 с — Balance v1.
    
- Окремі резонанси можуть мати довший ICD.
    

### Приклад

Primary: Fire.

Secondary: Water.

Результат:

Core Resonance = Steam.

### Обмеження

- Немає Core Resonance, якщо один із каналів неактивний.
    
- Немає Core Resonance між двома однаковими стихіями.
    
- Attack Speed не може автоматично обнулити Resonance ICD.
    
- Не створювати зайві резонанси через Elemental Weapon.
    

Повний каталог:

[Resonances](../Systems/Resonances.md).

## 18. Активний союзний Герой

У бою може перебувати максимум один активний союзний Герой.

### Відмінності від ГГ

Союзний Герой:

- Атакує автономно.
    
- Має окремий Hero DPS.
    
- Має одну незмінну вроджену стихію.
    
- Має шість власних слотів екіпірування.
    
- Не має окремої шкали HP.
    
- Може отримувати відповідні контрольні ефекти.
    
- Може використовувати Active Skill та Ultimate за власними правилами.
    

### Взаємодія

Активний Герой може:

- Посилювати загальний DPS.
    
- Утворювати Hero Resonance.
    
- Брати участь у Triple Resonance.
    
- Активувати Elemental Alignment.
    

### Обмеження

- Союзний Герой не додає четвертого стихійного каналу.
    
- Спорядження союзного Героя не створює нових Primary/Secondary Channels.
    
- Герой, відправлений в експедицію, не може бути активним у бою.
    

## 19. Hero Resonance та Reaction Focus

Якщо союзний Герой має стихію, відмінну від доступних каналів ГГ, може виникнути Hero Resonance.

### Три різні стихії

Приклад:

- Primary: Water.
    
- Secondary: Nature.
    
- Hero: Fire.
    

Можливі Hero Resonance:

- Fire + Water.
    
- Fire + Nature.
    

Гравець обирає один через Reaction Focus.

### Обраний Focus

Focus = Water:

Hero Resonance = Steam.

Focus = Nature:

Hero Resonance = Wildfire.

### Канон

- Одночасно працює лише один обраний Hero Resonance.
    
- Core Resonance залишається активним.
    
- Hero Resonance має власний ICD.
    
- Базовий Hero Resonance ICD: 1.5 с — Balance v1.
    
- Reaction Focus не змінює стихію союзного Героя.
    

### Важлива умова

Вибір між двома Hero Resonance існує лише тоді, коли обидва канали ГГ активні й різні, а Герой має третю стихію.

Для інших конфігурацій не створювати неіснуючі альтернативи.

## 20. Elemental Alignment

Якщо стихія активного Героя збігається з одним із каналів ГГ, застосовується Elemental Alignment.

### Balance v1

- +12% до внеску відповідної стихії.
    
- +8% Hero Damage.
    

### Приклад

- Primary: Water.
    
- Secondary: Nature.
    
- Hero: Water.
    

Результат:

- Core Resonance: Water + Nature.
    
- Elemental Alignment для Water.
    
- Не створюється новий Hero Resonance між Water і Water.
    

### Обмеження

Elemental Alignment не дорівнює Triple Resonance.

Не запускати Hero Resonance між однаковими стихіями.

## 21. Triple Resonance

Якщо виконуються всі умови:

- Primary активний.
    
- Secondary активний.
    
- Активний союзний Герой присутній.
    
- Усі три стихії різні.
    

Активується один Triple Resonance.

### Канон

- Усього існує 35 унікальних комбінацій.
    
- Triple Resonance є пасивним модифікатором.
    
- Він працює паралельно з Core та обраним Hero Resonance.
    
- Не створює третій незалежний активний resonance proc.
    
- Reaction Focus не змінює саму комбінацію трьох стихій.
    

### Приклад

Fire + Water + Nature.

Core Resonance визначається двома стихіями ГГ.

Hero Resonance визначається Reaction Focus.

Triple Resonance залишається тією самою комбінацією з трьох стихій.

Повні 35 ефектів:

[Resonances](../Systems/Resonances.md).

## 22. Pure Alignment

Повне моностихійне вирівнювання:

`Primary = Secondary = Hero Element`

### Balance v1

- +25% Damage відповідної стихії.
    
- +10% Elemental Penetration цієї стихії.
    
- +10% Hero Damage.
    

### Канон

У повному Pure Alignment:

- Не активується Double Resonance.
    
- Не активується Triple Resonance.
    
- Використовується відповідна Pure Alignment механіка.
    

### Принцип

Pure Alignment має бути конкурентною альтернативою білдам із кількома стихіями.

Не додавати автоматично всі ефекти Dual Alignment та Elemental Alignment поверх Pure Alignment, якщо таке накопичення не дозволене бойовою специфікацією.

## 23. Сім типів основної зброї

У ГГ є сім затверджених типів зброї.

|Тип|Основна бойова ідентичність|
|---|---|
|Шипований ланцюг / Батіг|Attack Speed, Skill / DoT|
|Важкий молот / Булава|ATK, Boss Damage|
|Бойова коса|Crit DMG, Elemental Damage|
|Посох окультиста|Elemental Damage, Skill Damage|
|Спис / Partisan|ATK, Crit Rate|
|Кинджал / Dirk|Attack Speed, Crit Rate|
|Одноручний меч|ATK, Attack Speed|

### Канон

Кожен тип зброї має два гарантовані Main Stats.

Типи зброї відрізняються через:

- Основні характеристики.
    
- Допустимі Affix Pools.
    
- Бойову ідентичність.
    

### Важливі заборони

- Не створювати восьмий стандартний тип зброї без погодження.
    
- Прадавній Клинок Відсічення не є новим стандартним типом.
    
- Вибір зброї не створює постійного класу ГГ.
    

Точні Roll Bands:

[Equipment](../Systems/Equipment.md).

## 24. Спорядження та розвиток предметів

Предмети мають кілька шарів сили.

### Rarity

Шість рівнів:

1. Common.
    
2. Uncommon.
    
3. Rare.
    
4. Epic.
    
5. Legendary.
    
6. Mythic.
    

### Rank

Rank 0–12.

Rank 0 — базовий стан.

Rank 1–12 — основна довгострокова шкала розвитку.

### Upgrade

`+0 ... +30`

Покращення має гарантований успіх за затвердженими правилами Кузні.

### Main Stats

- Основна зброя та інше armament: 2 гарантовані Main Stats.
    
- Броня: 2 гарантовані Main Stats.
    
- Аксесуари: 3 гарантовані Main Stats.
    

### Affixes

Додаткові характеристики з дозволених пулів.

### Elemental Enchantment

Впливає на стихійний білд.

### Named / Mythic Traits

Можуть змінювати окремі бойові взаємодії.

### Головне правило

Rarity, Rank, Upgrade, Main Stat Roll та Affixes не повинні застосовувати один і той самий множник двічі.

Повні формули й рецепти:

[Equipment](../Systems/Equipment.md)

[Crafting](../Systems/Crafting.md)

## 25. Основна математична модель шкоди

Використовувати Combat Bible як джерело істини.

### Base Direct Hit

`BaseDirect = FlatATK × (1 + ATK%) × AttackCoefficient`

### Physical Packet

`PhysicalPacket = BaseDirect × PhysicalShare × CritMult × PhysicalModifiers × PhysicalResistanceMult`

### Elemental Packet

`ElementPacket_i = BaseDirect × ElementShare_i × (1 + ElementBonus_i) × CritMult × ElementResistanceMult_i`

### Важливі правила

- Physical та Elemental Damage рахуються як окремі пакети.
    
- Elemental Damage не повинен автоматично видаляти Physical Damage.
    
- Skill Packets використовують відповідні коефіцієнти.
    
- DoT критує лише тоді, коли це дозволяє конкретна механіка.
    
- RES перевіряється для відповідного типу пакета.
    
- True Immunity обробляється до звичайного розрахунку RES.
    

### Загальна обробка атаки

1. Визначити базові характеристики.
    
2. Визначити Attack Coefficient.
    
3. Сформувати Physical і Elemental Packets.
    
4. Застосувати ATK та Skill Modifiers.
    
5. Перевірити Crit, якщо дозволено.
    
6. Перевірити Resonance Proc.
    
7. Застосувати Triple Modifiers.
    
8. Перевірити True Immunity.
    
9. Застосувати Phase RES, Shred та Penetration.
    
10. Застосувати відповідні умовні модифікатори.
    
11. Показати кінцеву шкоду та VFX.
    

Фінальний порядок визначає:

[Combat](../Systems/Combat.md).

## 26. Захист ГГ та отримання шкоди

Вороги атакують Головного Героя.

### Джерела захисту

- Base HP.
    
- Base DEF.
    
- Physical Mitigation.
    
- Сім Elemental RES.
    
- Equipment.
    
- Talent Tree.
    
- Buffs.
    
- Shields.
    
- Soul Skills.
    
- Дозволені Hero/Pet Bonuses.
    

### Умови програшу

Гравець може програти:

- Через смерть ГГ.
    
- Через закінчення таймера боса.
    

### Канон

- DEF та RES не повинні змішуватися в одне непрозоре значення.
    
- Щит не означає повного імунітету.
    
- Не можна створювати нескінченні захисні цикли без перевірки.
    
- Повна True Elemental Immunity не є звичайним бонусом спорядження ГГ.
    

### Відновлення HP

Можливі джерела:

- HP Regen.
    
- Навички.
    
- Таланти.
    
- Відповідні Hero/Pet Effects.
    

Точні коефіцієнти відновлення повинні визначатися відповідними системами, а не задаватися довільно в контролері персонажа.

## 27. Контрольні ефекти

ГГ може отримувати відповідні бойові статуси.

### Stun

- Тимчасово блокує атаки.
    
- Тимчасово блокує активні навички.
    

Balance v1:

- Тривалість 2–3 с.
    
- Після завершення — захист від повторного Stun протягом щонайменше 6 с.
    

### Silence / Skill Lock

- Базові атаки залишаються доступними.
    
- Активні навички тимчасово заблоковані.
    

Balance v1:

2–3 с.

### Root

Не є повним аналогом Stun.

Має обмежений вплив на відповідні бойові дії та анімації.

### Healing Reduction

Тимчасово зменшує ефективність лікування.

### RES Curse

Тимчасово знижує відповідний RES ГГ.

### Вимоги

- Статуси мають бути видимими в HUD.
    
- Сильний контроль босів потребує telegraph.
    
- Не допускати нескінченних stun-lock циклів.
    
- Не скасовувати базові атаки під час Silence, якщо конкретна механіка цього не передбачає.
    

## 28. Run Talent Tree

Базовий каталог містить 120 унікальних вузлів талантів; фінальний розмір дерева перевіряється експериментально за Talents §34.

### Основні групи

- Central Ring: 14.
    
- Manual / Combo: 13.
    
- Auto / Hero / Pets: 13.
    
- Skills / Resonance: 13.
    
- Elemental Sectors: 42.
    
- Resonance Bridges: 21.
    
- Global Keystones: 4.
    

### Відкриття

Floor 100 Башти 01-I під час першого проходження.

### Основні правила

- Talent Points — run-based.
    
- Вузли мають конкретні Node ID.
    
- Перед придбанням перевіряються prerequisites.
    
- Два Elemental Keystone максимум.
    
- Один Global Keystone максимум.
    
- Три Active Talent Skills використовують чотири загальні слоти ГГ.
    

### Presets

Доступно до трьох пресетів.

Усі використовують спільний пул TP поточного run.

Лише активний пресет надає бойові бонуси.

### Rebirth

- Фактичні Node Ranks скидаються.
    
- Earned/Unspent TP скидаються.
    
- Відкриті Preset Slots зберігаються.
    
- Preset Templates і Purchase Order зберігаються.
    

Базовий каталог 120 вузлів:

[Talents](../Systems/Talents.md).

## 29. Soul Skills

Soul Skills — постійна прогресія за Available Souls.

### Active Soul Skills

Існують чотири:

1. Берсерк-Драйв.
    
2. Розрив Резонансу.
    
3. Злам Часу.
    
4. Абсолютний Фокус.
    

### Passive Soul Skills

Існують десять постійних пасивних Soul Skills.

### Загальні правила

- Купуються за Available Souls.
    
- Зберігаються після Rebirth.
    
- Не зменшують Total Souls Collected.
    
- Active Soul Skills займають чотири загальні слоти.
    
- Підпорядковуються Cooldown/Combat Caps.
    

### Soul Relics

Існують 14 постійних Soul Relics.

Soul Relics:

- Не займають 12 слотів спорядження.
    
- Зберігаються після Rebirth.
    
- Не створюють нові стихійні канали.
    

Повна система:

[Talents](../Systems/Talents.md).

## 30. Soul Power

Постійна сила ГГ залежить від усіх отриманих Souls.

### Формула — Balance v1

`SoulPowerMult = 1 + 0.10 × TotalSoulsCollected`

### Два лічильники

**Total Souls Collected**

Історична кількість усіх Souls.

**Available Souls**

Поточна валюта для покупок.

### Приклад

Гравець отримав 100 Souls.

Soul Power:

`1 + 0.10 × 100 = 11`

Множник:

×11.

Якщо гравець витрачає 70 Available Souls:

- Total Souls Collected залишається 100.
    
- Available Souls зменшується на 70.
    
- Soul Power залишається ×11.
    

### Обмеження

Витрати Souls ніколи не повинні зменшувати історичний Soul Power.

### Балансний ризик

Лінійне накопичення +10% від бази за Soul може надмірно прискорювати пізні Rebirth.

Формула залишається Balance v1 і потребує довгострокових симуляцій.

## 31. Rebirth — Переродження ГГ

### Відкриття

Після першої перемоги над Guardian 141 Башти 01-I.

### Добровільність

Rebirth виконується за рішенням гравця.

### Перша винагорода

Перше повне очищення 01-I до Floor 141:

16 Souls без додаткових бонусів — Balance v1.

### Під час Rebirth

1. Розраховується Soul Score поточного run.
    
2. Визначається Souls Earned.
    
3. Нагорода видається рівно один раз.
    
4. Скидається Run Progress.
    
5. Зберігається Meta/World Progress.
    
6. Починається новий забіг.
    

### Що скидається у ГГ

- Поточний Level.
    
- Поточний XP.
    
- Gold.
    
- Gold Upgrade Levels.
    
- Поточні Talent Points.
    
- Actual Talent Node Ranks.
    
- Тимчасові Buffs.
    
- Поточні Combat Cooldowns.
    
- Run Position.
    
- Поточні Run State Values.
    

### Що зберігається

- Total Souls Collected.
    
- Available Souls.
    
- Soul Skills.
    
- Soul Relics.
    
- Відкриті системи.
    
- Auto Attack Unlock.
    
- Відкриті Preset Slots.
    
- Preset Templates.
    
- Сюжетні перемоги.
    
- World Map Progress.
    
- Герої та Ascension.
    
- Вихованці й постійна Pet Progression.
    
- Дозволені постійні ресурси та рецепти.
    
- Epic–Mythic Gear за правилами Rebirth Seal.
    

Повний розрахунок:

[Progression](../Systems/Progression.md)

[Economy](../Systems/Economy.md)

## 32. Rebirth Seal спорядження

### Common / Uncommon / Rare

Після Rebirth зникають.

### Epic / Legendary / Mythic

Залишаються, але отримують тимчасове послаблення Rebirth Seal.

### Balance v1

|Rarity|Сила одразу після Rebirth|Орієнтир повного відновлення|
|---|---|---|
|Epic|≈30%|Floor 80|
|Legendary|≈25%|Floor 120|
|Mythic|≈20%|Floor 141|

### Що предмет зберігає

- Rarity.
    
- Rank.
    
- Upgrade Level.
    
- Main Stats.
    
- Affixes.
    
- Elemental Enchantment.
    
- Named/Mythic Traits.
    

### Важливі правила

- Rebirth Seal не перегенеровує предмет.
    
- Один і той самий предмет не дублюється.
    
- Не можна отримати дві копії через Save/Load.
    
- Запечатаний предмет не повинен автоматично надавати повну endgame-силу на Floor 1.
    
- Точна крива відновлення — Balance v1.
    

## 33. Взаємодія з двома вихованцями

ГГ може мати до двох активних вихованців.

### Можливі ролі

- Combat.
    
- Support.
    
- Economy.
    

### Вплив

Вихованці можуть:

- Завдавати власну шкоду.
    
- Підсилювати характеристики.
    
- Застосовувати відповідні ефекти.
    
- Надавати економічні бонуси.
    

### Канон

- Pet Collection постійна.
    
- Pet Level/Stars зберігаються після Rebirth.
    
- Pet Element не створює нового Resonance Channel.
    
- Вихованці не змінюють Primary/Secondary Channel.
    
- Активні вихованці не повинні перекривати бойові кнопки.
    

Докладніше:

[Pets](Pets.md).

## 34. FTUE Головного Героя

Поступове відкриття систем:

|Поверх|Новий функціонал ГГ|
|---|---|
|1|Manual/Hold Combat|
|2|Gold Upgrades|
|10|Inventory та Equipment|
|20|Bestiary + Auto Attack після перемоги|
|40|Daily Tasks|
|60|Quests та Reputation|
|70|Звичайний прогрес; магазин випадкових скринь вилучено|
|80|Forge I|
|100|Talent Tree|
|115|Pets|
|130|Перший союзний Герой|
|141|World Map та Rebirth|
|Перша перемога над босом 20 у 01-I|Auto Attack|

### Важливі правила

- Перший предмет гарантований на Floor 10.
    
- Floor 80 не видає безкоштовний Element Crystal автоматично.
    
- Floor 100 відкриває Talent Tree.
    
- Floor 115 гарантує перше яйце.
    
- Floor 130 відкриває першого союзного Героя.
    
- Auto Attack уже доступна після боса 20; Floor 141 не є умовою відкриття.
    

## 35. Бойовий інтерфейс ГГ

### Основний HUD

Відображає:

- Ім'я або позначення ГГ.
    
- Рівень.
    
- XP.
    
- Current HP.
    
- Max HP.
    
- Поточний поверх.
    
- Gold.
    
- Активні бойові навички.
    
- Cooldowns.
    
- Status Effects.
    
- Primary Element.
    
- Secondary Element.
    
- Active Hero Element.
    
- Reaction Focus.
    
- Активні резонанси.
    
- Стан Auto Attack.
    

### Композиція бойової сцени

- Центр — головний ворог.
    
- Праворуч — ГГ та один активний союзний Герой.
    
- Ліворуч — статистика й допоміжний інтерфейс.
    
- Унизу — чотири активні слоти.
    
- Вихованці — окремий декоративний контейнер над нижньою панеллю.
    

### Elemental UI

Біля панелі навичок показувати:

- Primary Element.
    
- Secondary Element.
    
- Core Resonance.
    
- Hero Resonance.
    
- Triple Resonance або відповідний Alignment State.
    

### Build Preview

Після зміни спорядження попередньо показувати:

- Нові характеристики.
    
- Який канал активується.
    
- Який канал зникає.
    
- Чи зміниться Core Resonance.
    
- Чи зміниться Hero Resonance.
    
- Чи зміниться Triple Resonance.
    
- Чи стане актуальним Alignment.
    

Це дозволяє змінювати білд без прихованих наслідків.

## 36. Візуальна концепція ГГ

Сюжетний образ — молодий воїн, який поступово відкриває справжнє походження власної сили.

### Затверджені основи

- Dark Fantasy.
    
- Середньовічне фентезі.
    
- Духовна спадщина Прадавнього Героя.
    
- Елементальна магія.
    
- Спорядження різної якості.
    
- Візуальні стихійні ефекти.
    
- Невеликі декоративні бойові анімації.
    

### Анімації для реалізації

Рекомендований виробничий перелік:

- Idle.
    
- Manual Attack.
    
- Hold Attack.
    
- Auto Attack.
    
- Skill Cast.
    
- Hit Reaction.
    
- Stun.
    
- Silence State.
    
- Victory.
    
- Defeat.
    
- Rebirth Transition.
    

Це список виробничих станів, а не затверджений каталог конкретних анімацій.

### Не визначено остаточно

- Власне ім'я ГГ.
    
- Точна зовнішність.
    
- Фінальний дизайн обличчя.
    
- Зачіска.
    
- Стартовий костюм.
    
- Портрет.
    
- Візуальна заміна тільки зброї; броня, аксесуари, щит і плащ не змінюють вигляд ГГ.
    
- Фінальний набір spritesheets.
    

Не вигадувати ці елементи як затверджений Canon.

### Рекомендований виробничий підхід для Godot (Production Proposal)

- Базовий спрайт Головного Героя рекомендується розділяти на 4–5 шарів під `Skeleton2D` (тулуб із ногами, голова, передня рука зі зброєю, задня рука/щит, плащ) для плавної анімації удару та дихання.
- 12 слотів спорядження відображаються іконками; тільки активна зброя змінює видимий предмет на ГГ в бою й вікні персонажа. Броня, аксесуари, щит і плащ не змінюють одяг/силует. Стихійна аура каналів зберігається як бойовий індикатор. Сім типів зброї збережені; відповідність weapon_visual_id визначає Art Direction.

## 37. Godot Data Architecture

Назви нижче є рекомендованим технічним контрактом. Вони не створюють нових ігрових механік.

### 37.1. MainCharacterRunState

Поля:

- character_id.
    
- run_id.
    
- level.
    
- xp.
    
- current_hp.
    
- gold.
    
- gold_upgrade_levels.
    
- combo_state.
    
- active_status_effects.
    
- active_skill_slots.
    
- cooldown_state.
    
- active_talent_preset_id.
    

### 37.2. CharacterBaseStats

- base_atk.
    
- base_hp.
    
- base_def.
    
- level_scaling_config.
    

### 37.3. CharacterDerivedStats

- final_atk.
    
- max_hp.
    
- def.
    
- physical_res.
    
- elemental_res[7].
    
- crit_rate.
    
- crit_damage.
    
- attack_speed.
    
- skill_damage.
    
- cooldown_recovery.
    
- elemental_damage_modifiers.
    
- elemental_penetration.
    
- resonance_modifiers.
    

Derived Stats обчислюються заново при зміні стану.

Не використовувати їх як головне джерело істини SaveData.

### 37.4. MainCharacterEquipment

Рівно 12 Equipment Slot References.

Групи:

- armor_slots[5].
    
- armament_slots[3].
    
- accessory_slots[4].
    

### 37.5. CharacterElementChannels

- primary_element.
    
- primary_active.
    
- primary_power.
    
- secondary_element.
    
- secondary_active.
    
- secondary_power.
    
- alignment_state.
    

### 37.6. CharacterCombatState

- manual_attack_state.
    
- hold_attack_state.
    
- auto_attack_enabled.
    
- combo_value.
    
- active_skill_slots[4].
    
- status_effects.
    
- current_target_id.
    

### 37.7. CharacterMetaState

- total_souls_collected.
    
- available_souls.
    
- unlocked_soul_skills.
    
- purchased_soul_relics.
    
- permanent_unlock_flags.
    
- unlocked_talent_preset_slots.
    

### 37.8. CharacterProgression

- level.
    
- xp.
    
- gold_upgrades.
    
- earned_tp.
    
- spent_tp.
    
- equipped_preset.
    
- current_run_best_floor.
    

## 38. Порядок оновлення характеристик

При зміні спорядження:

1. Перевірити валідність Item Slot.
    
2. Оновити Equipment References.
    
3. Перерахувати Armor Element Count.
    
4. Перерахувати Accessory Element Count.
    
5. Оновити Primary/Secondary Channels.
    
6. Перевірити Alignment.
    
7. Перевірити Core/Hero/Triple Resonances.
    
8. Перерахувати Main Stats та Affixes.
    
9. Додати дозволені Run Talent Bonuses.
    
10. Додати Permanent Soul Bonuses.
    
11. Додати дозволені Hero/Pet Contributions.
    
12. Застосувати Caps.
    
13. Оновити Derived Stats.
    
14. Оновити Combat HUD і Build Preview.
    

### Тригери оновлення

- Level Up.
    
- Equipment Change.
    
- Rank/Upgrade Change.
    
- Enchantment Change.
    
- Talent Purchase.
    
- Talent Reset.
    
- Talent Preset Switch.
    
- Active Hero Change.
    
- Reaction Focus Change.
    
- Pet Change.
    
- Soul Skill Purchase.
    
- Rebirth.
    

Не допускати накопичення дубльованих бонусів після багаторазового перевдягання предметів.

## 39. Збереження та завантаження

### SaveData

Повинні зберігатися:

- Run Progress.
    
- Current Character Level/XP.
    
- Current Equipment IDs.
    
- Item Instances.
    
- Talent State.
    
- Skill Loadout.
    
- Permanent Unlocks.
    
- Soul Progress.
    
- Rebirth Count.
    
- Story Progress.
    

### Після Load

Необхідно:

- Перевірити Item IDs.
    
- Перевірити кількість слотів.
    
- Перерахувати активні стихійні канали.
    
- Перевірити Skill Loadout.
    
- Перевірити Talent Prerequisites.
    
- Перевірити актуальний Rebirth Seal.
    
- Перерахувати Derived Stats.
    
- Оновити UI.
    

### Важливий принцип

Не довіряти збереженим фінальним DPS/HP, якщо склад спорядження або правила балансу могли змінитися.

Дані Character Derived Stats повинні коректно відновлюватися з базових джерел.

## 40. Перевірки — основний персонаж

### Бій

- Manual Attack працює з першого поверху.
    
- Hold Attack працює з першого поверху.
    
- Hold Attack використовує Attack Cadence.
    
- Auto Attack заблокований до першої перемоги над босом 20 Башти 01-I.
    
- Auto Attack Unlock зберігається після Rebirth.
    
- Auto Attack підкоряється бойовим обмеженням.
    
- Є чотири активні слоти.
    
- Навички використовують відповідні cooldown.
    
- Stun блокує необхідні дії.
    
- Silence не блокує звичайні атаки.
    
- Смерть ГГ завершує поточний бій за правилами режиму.
    

### Характеристики

- Level Up збільшує базові ATK/HP/DEF.
    
- XP використовує правильну шкалу.
    
- Герой та вихованці мають окрему прогресію.
    
- Застосовуються Physical та сім Elemental RES.
    
- Не дублюються характеристики екіпірування.
    
- Derived Stats оновлюються після зміни білдів.
    

### Екіпірування

- Рівно 12 слотів ГГ.
    
- П'ять слотів основної броні.
    
- Три слоти armament.
    
- Чотири слоти аксесуарів.
    
- Сім затверджених типів зброї.
    
- Усі предмети перевіряють відповідність слоту.
    
- Rarity/Rank/Upgrade застосовуються один раз.
    
- Стихійна зброя не створює нового каналу.
    

### Стихії

- Primary активується лише при 4/5.
    
- Secondary активується лише при 3/4.
    
- Неповний поріг не активує канал.
    
- Однакова стихія не подвоює базовий бонус.
    
- Різні канали формують Core Resonance.
    
- Однакові канали використовують Dual Alignment.
    
- Третя стихія союзного Героя може дати Triple Resonance.
    
- Reaction Focus не запускає два Hero Resonances одночасно.
    
- Повний mono-build використовує Pure Alignment.
    
- Pet Element не формує канал.
    
- True Immunity не обходиться Penetration/Shred.
    

### Прогресія

- Talent Tree відкривається на Floor 100.
    
- Герой відкривається на Floor 130.
    
- Rebirth відкривається після Guardian 141.
    
- Rebirth добровільне.
    
- GG Level скидається.
    
- Gold скидається.
    
- Run Talents скидаються.
    
- Soul Skills зберігаються.
    
- Soul Relics зберігаються.
    
- Total Souls Collected не зменшується.
    
- Epic–Mythic Gear зберігається з Rebirth Seal.
    
- World Progress зберігається.
    

### UI

- Видимі HP ГГ.
    
- Видимий GG Level.
    
- Є XP/Gold Indicators.
    
- Є чотири кнопки активних навичок.
    
- Показані Primary/Secondary Elements.
    
- Показаний Reaction Focus.
    
- Показані активні Resonance/Alignment States.
    
- Build Preview оновлюється перед заміною предмета.
    
- Пети не перекривають інтерактивні кнопки.
    

Усі перевірки залишаються невиконаними до реальних тестів у Godot.

## 41. Балансні ризики

### MC01 — Growth Curve

Level Scaling, Gold Upgrades та Soul Power можуть створити надто стрімке зростання ATK.

### MC02 — Manual vs Auto

Auto Attack не повинен автоматично робити ручну гру беззмістовною.

### MC03 — Mono vs Multi-Element

Pure Alignment, Dual Alignment та Triple Resonance повинні залишатися конкурентними альтернативами в різних умовах.

### MC04 — Equipment Scaling

Rarity, Rank, Upgrade та Affixes не повинні формувати неконтрольовані мультиплікативні ланцюги.

### MC05 — Survivability

HP, DEF, RES, Healing і Shields повинні дозволяти захисні білди без нескінченного виживання.

### MC06 — Boss Immunity

Гравець повинен мати можливість бачити сигнатурну імунність Генерала та відповідно змінювати білд.

### MC07 — Rebirth Seal

Збережене Mythic спорядження не повинно повністю пропускати ранню прогресію нового run.

### MC08 — Soul Power

Довгострокове накопичення Souls потребує симуляцій десятків Rebirth.

## 42. Заборони для Claude Code

Без погодження розробника заборонено:

- Створювати ГГ фіксований клас.
    
- Додавати WASD Movement у базовий бій.
    
- Додавати понад 12 Equipment Slots.
    
- Додавати восьмий стандартний тип зброї.
    
- Додавати понад два Elemental Channels ГГ.
    
- Змінювати Primary Threshold 4/5.
    
- Змінювати Secondary Threshold 3/4.
    
- Створювати резонанс лише через стихійну зброю.
    
- Створювати стихійний канал через пета.
    
- Додавати понад чотири Active Skill Slots.
    
- Додавати додаткові слоти для Active Soul Skills.
    
- Дозволяти два одночасні Hero Resonances без затвердженої механіки.
    
- Перетворювати Triple Resonance на неконтрольований третій активний proc.
    
- Дублювати базовий бонус однакової стихії.
    
- Ігнорувати True Immunity Генералів.
    
- Самовільно змінювати Soul Power Formula.
    
- Скидати Soul Skills та Soul Relics під час Rebirth.
    
- Знищувати Epic–Mythic Gear під час Rebirth.
    
- Видавати Auto Attack до першої перемоги над босом 20 Башти 01-I.
    
- Вважати Balance v1 остаточним без плейтестів.
    
- Вигадувати фінальну зовнішність ГГ як затверджений Canon.
    

## 43. Пов'язані документи

- [Головні правила](../02_Core_Rules.md)
    
- [Огляд гри](../01_Game_Overview.md)
    
- [Бойова система](../Systems/Combat.md)
    
- [Стихії](../Systems/Elements.md)
    
- [Резонанси](../Systems/Resonances.md)
    
- [Екіпірування](../Systems/Equipment.md)
    
- [Кузня](../Systems/Crafting.md)
    
- [Економіка](../Systems/Economy.md)
    
- [Прогресія](../Systems/Progression.md)
    
- [Таланти](../Systems/Talents.md)
    
- [Союзні Герої](Heroes.md)
    
- [Вихованці](Pets.md)
    
- [Регіони](../World/Regions.md)
    
- [Башти](../World/Towers.md)
    
- [Вороги](../World/Enemies.md)
    
- [Експедиції](../World/Expeditions.md)
    
- [Художній напрям](../Art/Art_Direction.md)
    

### Пріоритет джерел

- Lore & Art Bible v2.2 — походження та сюжетна роль ГГ.
    
- GDD v2.3 — загальна інтеграція систем, FTUE та Rebirth.
    
- Combat Bible v1.2 — бойова логіка, damage packets, елементальні канали, резонанси, навички та caps.
    
- Equipment Bible v1.2 — 12 слотів, зброя, броня, аксесуари, Enchantment та Rebirth Seal.
    
- Talent Tree Bible v1.1 — GG Level, XP, 120 талантів, Soul Skills та Presets.
    
- Economy Bible v1.2 — Gold Upgrades, Souls, Rebirth Rewards та баланс.
    
- Heroes & Pets Bible v1.2 — взаємодія з союзними Героями й вихованцями.
    

У випадку суперечності використовувати актуальне спеціалізоване джерело та останні затверджені рішення.

---

**Статус документа:** Markdown-версія на основі фінальних Design Bible.

**Статус реалізації:** не реалізовано.

**Статус контенту:** Content v1.

**Статус числового балансу:** Balance v1.

**Головний Герой:** Новий Обранець.

**Equipment Slots:** 12.

**Primary Element Threshold:** 4/5 Armor.

**Secondary Element Threshold:** 3/4 Accessories.

**Active Skill Slots:** 4.

**Основних типів зброї:** 7.

**Основний принцип:** Головний Герой не має постійного бойового класу; його сила та ігровий стиль формуються спорядженням, двома стихійними каналами, талантами, союзниками та постійною Soul-прогресією.

## 44. Узгодження нових механік — 2026-11-04

Навчальна utility_interrupt відкривається на Floor 10, займає один із чотирьох слотів і не потребує стихії/TP. Базова Auto Attack відкривається після першої перемоги над босом 20, зберігається після Rebirth. Доступний перемикач Auto.

Interrupt перевіряється за Combat §9.4: звичайний swing непереривний; багатократна навичка має максимум одне успішне переривання на активацію. Снаряд прив'язаний до конкретної цілі та не переноситься на нового ворога. Декоративні Tween/VFX не керують доступністю бойових подій.

Зовнішній вигляд предметів змінюється лише для зброї; правила в Art Direction §64. Профіль талантів зберігає власний profile_id, базовий каталог має 120 вузлів.
