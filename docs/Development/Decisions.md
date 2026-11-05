---

status: draft  
document_type: decision-log  
source: GDD v2.3, specialized Design Bibles, approved decisions 2026-10-14  
authority: approved-decisions-register  
updated: 2026-11-04
tags:

- development
    
- decisions
    
- canon
    
- balance
    
- godot
    
- claude-code
    

revision: approved-changes-2026-11-04
---

# DECISIONS LOG — Реєстр затверджених рішень

> Редакція 2026-11-04: затверджені зміни за [Decisions](Decisions.md) мають пріоритет над суперечними правилами попередніх Word Bible. Оновлено документацію; реалізацію та ігровий баланс не перевірено.

> Реєстр чинних геймдизайнерських і технічних рішень для 2D Dark Fantasy Clicker / Incremental Action RPG.
> 
> Призначення: не допускати повторного обговорення вже закритих питань, суперечностей між системами та несанкціонованих змін з боку AI-асистента.
> 
> Основні джерела: GDD v2.3; World & Towers Bible v1.2; Economy & Balance Bible v1.2; Combat Bible v1.2; Equipment Bible v1.2; Crafting Bible v1.2; Heroes & Pets Bible v1.2; Enemies & Loot Bible v1.2; Talent Tree Bible v1.1; Story, Lore & Art Bible v2.2.
> 
> Особливий пріоритет: погоджені уточнення від 14.10.2026, внесені до фінальних Design Bible.
> 
> **Важливо:** цей файл фіксує рішення, але не замінює детальні правила спеціалізованих документів.

## 1. Призначення Decisions Log

Цей документ відповідає на питання:

- Які рішення вже ухвалено?
    
- Яке правило зараз діє?
    
- Які старі варіанти більше не використовуються?
    
- Які цифри остаточні, а які ще балансні?
    
- Що Claude Code може реалізувати без додаткового погодження?
    
- Які питання потребують рішення розробника?
    
- Які документи потрібно синхронізувати після зміни правила?
    

### Основний принцип

Не змінювати канонічну механіку лише тому, що іншу реалізувати простіше.

Якщо виникає суперечність, потрібно звернутися до цього реєстру та відповідної спеціалізованої Bible.

## 2. Статуси рішень

|Status|Значення|
|---|---|
|APPROVED_CANON|Затверджена механіка або обмеження|
|APPROVED_CONTENT_V1|Погоджений поточний контент, який можна уточнювати окремими рішеннями|
|BALANCE_V1|Робочі числові параметри, потрібні плейтести|
|PROPOSED|Пропозиція, яку ще не затверджено|
|OPEN|Невирішене питання, необхідне погодження|
|SUPERSEDED|Старе рішення, замінене новим|
|REJECTED|Варіант, який вирішено не використовувати|

### Головне правило

Рішення зі статусом APPROVED_CANON не можна замінювати пропозицією PROPOSED. Нове пряме погодження розробника може замінити попередній Canon; зміни 2026-11-04 зафіксовані нижче.

BALANCE_V1 не означає остаточного числового балансу.

OPEN не дає Claude Code дозволу вигадувати відсутню механіку.

## 3. Формат нового рішення

Кожне майбутнє рішення записувати в такій структурі:

**Decision ID:** DEC-XXX.

**Status:** APPROVED_CANON / BALANCE_V1 / OPEN / інший.

**Date:** дата фактичного рішення, якщо відома.

**Category:** Combat / World / Economy / Progression / Art / Development / інше.

**Decision:** точне формулювання.

**Reason:** навіщо прийняте рішення, якщо обґрунтування відоме.

**Supersedes:** попереднє рішення, якщо існує.

**Affected Documents:** список документів.

**Implementation Impact:** що потрібно змінити в Godot.

**Validation:** як перевірити дотримання рішення.

### Не вигадувати історію рішень

Якщо точна дата затвердження невідома, зазначати версію джерела, а не придумувати дату.

## 4. Індекс чинних рішень

|ID|Рішення|Status|
|---|---|---|
|DEC-001|Жанр і базовий формат керування|APPROVED_CANON|
|DEC-002|Сім стихій|APPROVED_CANON|
|DEC-003|Два канали ГГ: 4/5 і 3/4|APPROVED_CANON|
|DEC-004|Подвійні та потрійні резонанси|APPROVED_CANON|
|DEC-005|Союзний Герой і пети|APPROVED_CANON|
|DEC-006|Слоти екіпірування|APPROVED_CANON|
|DEC-007|Сім типів зброї|APPROVED_CANON|
|DEC-008|Чотири активні навички ГГ|APPROVED_CANON|
|DEC-009|True Immunity Генералів|APPROVED_CANON|
|DEC-010|Географія світу|APPROVED_CANON|
|DEC-011|Структура Башт Ув'язнення|APPROVED_CANON|
|DEC-012|Небесні Вежі й командири|APPROVED_CANON|
|DEC-013|Відкриття Небесних Веж 5–7|APPROVED_CANON|
|DEC-014|Стихійні Данжі|APPROVED_CANON|
|DEC-015|Етапи Вежі Випробувань|APPROVED_CANON|
|DEC-016|Відкриття Auto Attack|APPROVED_CANON|
|DEC-017|FTUE першої Башти|APPROVED_CANON|
|DEC-018|Forge I та Enchant I|APPROVED_CANON|
|DEC-019|Спеціальні матеріали Стражів|APPROVED_CANON|
|DEC-020|General Hearts|APPROVED_CANON|
|DEC-021|Три слоти експедицій|APPROVED_CANON|
|DEC-022|Перша навчальна розвідка|APPROVED_CANON|
|DEC-023|Репутація 3/7/9/10|APPROVED_CANON|
|DEC-024|Якість експедицій I–V|APPROVED_CANON|
|DEC-025|Gold Discounts|APPROVED_CANON|
|DEC-026|Базовий каталог 120 Talent Nodes; фінальний обсяг за DEC-042|BASELINE / OPEN|
|DEC-027|Talent Points за boss ID|APPROVED_CANON|
|DEC-028|Rebirth Reset / Keep|APPROVED_CANON|
|DEC-029|Soul Currency Model|APPROVED_CANON|
|DEC-030|Hero/Pet Progression|APPROVED_CANON|
|DEC-031|Постійні сюжетні події|APPROVED_CANON|
|DEC-032|Архітектура та порядок розробки|APPROVED_CANON / DEVELOPMENT PLAN|
|DEC-033|Steam — premium single-player|APPROVED_CANON|
|DEC-034|Ядро числового балансу|BALANCE_V1|
|DEC-035|Art Production Parameters|OPEN|
|DEC-038|Гарантовані Герої та прямі покупки|APPROVED_CANON / BALANCE_V1|
|DEC-039|Hero Sigils із випробувань|APPROVED_CANON / BALANCE_V1|
|DEC-040|Вилучення купівлі скринь; гарантовані Special Pets|APPROVED_CANON / CONTENT_V1|
|DEC-041|Візуально змінюється лише зброя ГГ|APPROVED_CANON|
|DEC-042|Експерименти з обсягом талантів|APPROVED_TEST_PLAN / OPEN|
|DEC-043|Повний реліз 49/147 та 14 Героїв|APPROVED_CANON|
|DEC-044|Ціна за результатами демо|OPEN|
|DEC-045|Уточнення Interrupt та раннє навчання|APPROVED_CANON / BALANCE_V1|
|DEC-036|Enemy Action / Cast Bar та механіка Interrupt|APPROVED_CANON|
|DEC-037|Візуальна доставка навичок (Impact Sync) та процедурна анімація|APPROVED_CANON|

## 5. DEC-001 — Жанр та управління

**Status:** APPROVED_CANON.

**Source:** GDD v2.3; Combat Bible v1.2.

### Decision

Гра є 2D Clicker / Incremental Action RPG у стилі Dark Fantasy.

Головний Герой:

- Атакує кліком.
    
- Може утримувати ЛКМ для повторних ударів.
    
- Використовує Auto Attack після відкриття.
    
- Має активні навички.
    
- Не пересувається вільно через WASD.
    

### Rejected Variants

- Повноцінний WASD Action RPG.
    
- 3D Action Game замість 2D Clicker.
    
- Вільне переміщення по відкритій 3D-карті.
    

### Implementation Rule

Бойові сцени будувати навколо Encounter State, а не Character Movement Controller для вільного переміщення.

## 6. DEC-002 — Сім стихій

**Status:** APPROVED_CANON.

**Source:** Combat Bible v1.2.

### Decision

У грі існує рівно сім Первісних Стихій:

1. Fire.
    
2. Water.
    
3. Nature.
    
4. Light.
    
5. Dark.
    
6. Lightning.
    
7. Wind.
    

### Rejected Variants

- П'ять базових стихій.
    
- Восьма стихія без нового рішення.
    
- Окрема Ice Element як восьма основна стихія.
    

### Implementation Rule

Використовувати один стабільний реєстр із семи Element IDs.

Ice, Poison, Burn та інші тематичні ефекти не створюють автоматично нову Основну Стихію.

## 7. DEC-003 — Два стихійні канали ГГ

**Status:** APPROVED_CANON.

**Source:** Combat Bible v1.2; Equipment Bible v1.2.

### Decision

Головний Герой має два основні стихійні канали.

**Primary Element Channel:**

4 із 5 основних частин броні мають відповідне зачарування однієї стихії.

**Secondary Element Channel:**

3 із 4 аксесуарів мають відповідне зачарування однієї стихії.

### Обмеження

- 3/5 броні недостатньо для Primary.
    
- 2/4 аксесуарів недостатньо для Secondary.
    
- Стихійна зброя не створює третього каналу.
    
- Пет не створює нового каналу.
    
- Союзний Герой надає свою вроджену стихію, але не перетворює ГГ на персонажа з трьома власними каналами.
    

### Supersedes

Попередні робочі пороги, які не відповідають 4/5 і 3/4.

### Test

Пороги 3/5 і 2/4 повинні залишати відповідні канали неактивними.

## 8. DEC-004 — Double / Triple Resonance

**Status:** APPROVED_CANON.

**Source:** Combat Bible v1.2.

### Decision

- 21 унікальний подвійний резонанс.
    
- 35 унікальних потрійних резонансів.
    
- Core Resonance утворюється з двох різних каналів ГГ.
    
- Hero Resonance утворюється зі стихії союзного Героя та одного вибраного каналу ГГ.
    
- Reaction Focus визначає лише один активний Hero Resonance.
    
- Triple Resonance є пасивним модифікатором трьох різних стихій.
    

### Однакові стихії

Якщо Primary і Secondary однакові:

Dual Alignment замість Core Resonance.

Якщо Primary, Secondary та Hero Element однакові:

Pure Alignment замість Double/Triple Resonances.

### Заборона

Не створювати додатковий Triple Proc як третю незалежну активну реакцію.

### Balance v1

Точні бонуси Alignment та Internal Cooldowns належать до Combat Balance Config.

## 9. DEC-005 — Активні супутники

**Status:** APPROVED_CANON.

**Source:** Heroes & Pets Bible v1.2.

### Decision

Одночасно в бою:

- Один активний союзний Герой.
    
- До двох активних вихованців.
    

### Герой

- Самостійно атакує.
    
- Має одну незмінну стихію.
    
- Не має окремої HP Bar.
    
- Може отримувати Stun/Silence за Combat Rules.
    

### Пети

- Надають Combat/Support/Economy Bonuses.
    
- Їхні стихії не створюють Resonance Channels.
    

### Rejected Variants

- Три активні союзні Герої.
    
- Чотири активні вихованці.
    
- Додатковий канал від Pet Element.
    

## 10. DEC-006 — Слоти спорядження

**Status:** APPROVED_CANON.

**Source:** Equipment Bible v1.2; Heroes & Pets Bible v1.2.

### Головний Герой

Рівно 12 слотів:

- 5 Armor.
    
- 3 Armament.
    
- 4 Accessories.
    

### Союзний Герой

Рівно 6 слотів:

- 1 Weapon.
    
- 3 Armor.
    
- 2 Accessories.
    

### Геройське Enchantment Restriction

Герой використовує тільки спорядження без активного стихійного зачарування.

### Implementation Rule

Валідатор Hero Equipment не дозволяє зачаровані предмети.

Слоти Героя не включаються до 12 слотів ГГ.

## 11. DEC-007 — Сім типів зброї

**Status:** APPROVED_CANON.

**Source:** Equipment Bible v1.2.

### Decision

Сім затверджених класів основної зброї:

1. Батіг / Ланцюг.
    
2. Молот / Булава.
    
3. Коса.
    
4. Посох.
    
5. Спис.
    
6. Кинджал.
    
7. Одноручний меч.
    

### Обмеження

Не створювати восьмий стандартний Weapon Type через:

- Візуальний лук союзного Героя.
    
- Сюжетний Прадавній Клинок.
    
- Назву іменного Mythic предмета.
    

### Відкрита сумісність

Потрібно окремо погодити технічне відображення візуальної зброї деяких Героїв у семи стандартних Weapon Types.

До погодження не змінювати каталог зброї.

## 12. DEC-008 — Активні слоти ГГ

**Status:** APPROVED_CANON.

**Source:** Combat Bible v1.2; Talent Tree Bible v1.1.

### Decision

ГГ має рівно чотири активні слоти.

У них можуть використовуватися:

- Elemental Skills.
    
- Active Soul Skills.
    
- Active Talent Skills.
- Навчальна utility_interrupt — робоча пропозиція за DEC-045, у тих самих чотирьох слотах.
    

### Обмеження

- Три активні Talent Skills не додають три нові кнопки.
    
- Чотири Active Soul Skills не додають чотири нові кнопки.
    
- Немає п'ятого слота.
    
- Hero Ultimate має окремий інтерфейс.
    

## 13. DEC-009 — True Elemental Immunity

**Status:** APPROVED_CANON.

**Source:** Combat Bible v1.2; Enemies & Loot Bible v1.2.

### Decision

Кожен Генерал має True Immunity рівно до однієї сигнатурної стихії.

Окремі спеціальні Trial Anomalies теж можуть мати True Immunity до однієї стихії.

### Обмеження

- RES Shred не обходить True Immunity.
    
- Penetration не обходить True Immunity.
    
- Високий RES не є тотожним True Immunity.
    
- Генерал не отримує автоматично імунітет до всіх семи стихій.
    
- Physical Damage не обнуляється тільки через Elemental Immunity.
    

### Implementation Rule

True Immunity перевіряється окремо від звичайних RES.

Не імітувати абсолютний імунітет просто RES = 100%.

## 14. DEC-010 — Географія

**Status:** APPROVED_CANON.

**Source:** World & Towers Bible v1.2; Lore & Art Bible v2.2.

### Decision

Світ складається з одного великого континенту.

Він має:

- Сім регіонів.
    
- Узбережжя.
    
- Півострови.
    
- Прибережні острови.
    
- Річки.
    
- Гори.
    
- Сім поселень.
    

### Важливе уточнення

«Сім Архіпелагів» — історична або поетична назва, а не сім фізично окремих континентів.

### R4

Небо Буревіїв — наземні високогірні плато.

Літаючі острови відсутні.

### Rejected Variants

- Сім окремих континентів.
    
- Повноцінний відкритий світ із WASD Movement.
    
- Літаючі острови R4.
    

## 15. DEC-011 — Башти Ув'язнення

**Status:** APPROVED_CANON.

**Source:** World & Towers Bible v1.2.

### Decision

- Сім регіонів.
    
- Три Башти Ув'язнення на регіон.
    
- Рівно 21 Башта.
    
- 141 поверх у кожній.
    

### Zone Boss Floors

20, 40, 60, 80, 100, 120, 140.

### Guardian

Floor 141.

### Triad

Три очищені Башти одного регіону формують завершену Тріаду Печатей.

### Обмеження

Перемога над Стражем 141 не знищує відповідний Палець Короля Демонів.

Це відбувається після сюжетної перемоги над Генералом.

## 16. DEC-012 — Небесні Вежі

**Status:** APPROVED_CANON.

**Source:** World & Towers Bible v1.2.

### Decision

- Сім Небесних Веж.
    
- 666 поверхів кожна.
    
- Шість командирів на Вежу.
    
- Сім Генералів загалом.
    

### Commander Floors

100, 200, 300, 400, 500, 600.

### General Floor

666.   
    

### Commander Priority

На поверсі командира він замінює Zone Boss.

### Обмеження

Не створювати Commander + Zone Boss як дві незалежні повноцінні нагородні зустрічі на одному поверсі.

## 17. DEC-013 — Гейти Небесних Веж 5–7

**Status:** APPROVED_CANON.

**Approved Date:** 2026-10-14 для уточнених гейтів 5/6.

**Source:** GDD v2.3 §23; World & Towers Bible v1.2 §11.

### Небесна Вежа 5

Усі умови одночасно:

- Щонайменше чотири повністю очищені Тріади.
    
- Reputation Rank ≥6.
    
- Щонайменше три різні сюжетно переможені Генерали.
    

### Небесна Вежа 6

Усі умови одночасно:

- Щонайменше п'ять повністю очищених Тріад.
    
- Reputation Rank ≥8.
    
- Щонайменше чотири різні сюжетно переможені Генерали.
    

### Небесна Вежа 7

- Шість інших сюжетно переможених Генералів.
    
- Відповідний сюжетний доступ до R7.
    

### Implementation Rule

Умови Веж 5/6 об'єднані оператором AND.

### Заборона

- Не використовувати OR.
    
- Не враховувати повторне Echo як нового унікального Генерала.
    
- Не вважати частково пройдену Тріаду завершеною.
    
- Не обходити гейти через розвідку Данжу.
    

### Test

Для Вежі 5:

Чотири Тріади, Rep 6, але лише два Генерали → Locked.

Для Вежі 6:

П'ять Тріад, чотири Генерали, але Rep 7 → Locked.

## 18. DEC-014 — Стихійні Данжі

**Status:** APPROVED_CANON.

**Source:** World & Towers Bible v1.2.

### Decision

Рівно сім стихійних Данжів.

Кожен має:

- 10 бойових поверхів.
    
- 10 рівнів складності.
    
- Elite на Floor 5.
    
- Elemental Boss на Floor 10.
    

### Unlock

Відповідний Данж відкривається після першої завершеної регіональної розвідки.

### Важливий виняток

R1 має тематичні Water/Nature елементи, але відкриває Wind Dungeon.

### Заборона

Не змінювати відповідність Dungeon/Region автоматично за основним кольором регіону.

## 19. DEC-015 — Infinite Trial Tower

**Status:** APPROVED_CANON.

**Source:** GDD v2.3; World & Towers Bible v1.2.

### Decision

У грі є одна нескінченна Вежа Випробувань.

### Стани

**Sealed**

Після першого Guardian 141 Башти 01-I:

Вежа видима, але недоступна.

**Awakened**

Після першої сюжетної перемоги над Генералом:

Рання стадія доступна.

**True Infinite**

Після першої перемоги над Королем Демонів:

Відкривається повна стадія.

### Нагороди

Повторний фарм не створює нескінченні Souls і TP.

### Supersedes

Старі правила, за якими Trial була повністю доступна одразу після Guardian 141 або лише після Demon King без ранньої стадії.

## 20. DEC-016 — Auto Attack

**Status:** APPROVED_CANON, редакція 2026-11-04; правило 2026-10-14 замінено.

**Source:** погодження розробника 2026-11-04; Combat §4.

### Decision

Базова Auto Attack відкривається після першої перемоги над Зональним босом на поверсі 20 Башти 01-I. Відкриття постійне, зберігається після Rebirth; доступний перемикач увімкнення/вимкнення. Вхід у 01-II більше не є умовою відкриття.

### Balance v1

Manual/Hold доступні з початку. Початкова сила Auto Hit ≈50% Manual Hit збережена для тестів. Орієнтир до автоматизації 30–60 хв, без штучної затримки. Не плутати Auto Attack з Auto Progress.

### Test

До перемоги над босом 20 → Auto Locked. Після першої перемоги → Auto Unlocked. Після Rebirth → Auto Unlocked.

## 21. DEC-017 — FTUE першої Башти

**Status:** APPROVED_CANON.

**Source:** GDD v2.3.

### Decision

|Floor|Подія|
|---|---|
|1|Manual/Hold Combat|
|2|Gold Upgrades|
|10|Перший предмет та utility_interrupt|
|20|Bestiary + Auto Attack після перемоги; навчальний каст боса|
|40|Daily Tasks|
|60|Quests / Reputation|
|70|Звичайний прогрес; магазин випадкових скринь вилучено|
|80|Forge I|
|100|Talent Tree / перший TP|
|115|Перше гарантоване яйце|
|130|Перший союзний Герой — Сільва|
|141|World Map / Rebirth / Expeditions / Celestial 1|

### Додатково

Після Floor 141:

Trial Tower видима, але заблокована.

### Обмеження

- Не дарувати Element Crystals на Floor 80.
    
- Не відкривати Auto Attack на Floor 10.
    
- Не робити першу експедицію звичайною довгою розвідкою.
    
- Не видавати First-Clear Rewards повторно після Rebirth.
    

## 22. DEC-018 — Рання Кузня та Enchant I

**Status:** APPROVED_CANON.

**Approved Date:** 2026-10-14.

**Source:** GDD v2.3 §23; Economy Bible v1.2 §16.

### Decision

Forge I відкривається на Floor 80 Башти 01-I.

Одразу працюють відповідні:

- Craft.
    
- Upgrade.
    
- Synthesis.
    
- Salvage.
    

Enchant I стає доступним у переліку рецептів.

### Але

Enchant I потребує відповідних Element Crystals.

На Floor 80 безкоштовні Element Crystals не видаються.

### Наслідок

Гравець може бачити рецепт раніше, ніж отримає необхідний матеріал.

Це нормальна поведінка.

### Заборона

Не додавати стартові Element Crystals, щоб штучно зробити Enchant I доступним одразу.

## 23. DEC-019 — Спеціальні матеріали Стражів

**Status:** APPROVED_CANON.

**Approved Date:** 2026-10-14.

**Source:** GDD v2.3 §23; World & Towers Bible v1.2 §11.

### Decision

Кожен із 21 Стража 141 має власний спеціальний матеріал.

### First Story Clear

- 100% на один відповідний матеріал.
    
- Рівно одна одиниця.
    
- Один раз за Save для конкретного Guardian ID.
    

### Repeat Guardian Clear

- 40% на один відповідний матеріал.
    
- 60% на нуль.
    
- Незалежний roll.
    

### Додаткові правила

- Не замінює звичайний Gold/XP/Gear/Loot.
    
- Не дублює регіональні креслення.
    
- Не є General Heart.
    
- Не використовує Named Soft Pity.
    

### Required Save State

- guardian_id.
    
- first_clear_claimed.
    
- source_id.
    
- claim_event_id.
    

### Test

First Clear → 1 гарантований матеріал.

Повторний Clear → окремий 40% roll.

Reload не повторює First-Clear Reward.

## 24. DEC-020 — General Hearts

**Status:** APPROVED_CANON.

**Approved Date:** 2026-10-14.

**Source:** GDD v2.3 §23; Economy Bible v1.2 §16.

### Decision

Існує сім окремих General Heart Materials.

### First Story General Clear

- 100% на один відповідний Heart.
    
- Рівно одна одиниця.
    
- Один раз за Save для конкретного General ID.
    
- Немає паралельного Heart RNG під час тієї самої першої сюжетної перемоги.
    

### General Echo

- 30% на один відповідний Heart.
    
- 70% на нуль.
    
- Незалежний roll.
    

### Заборонені джерела

- Normal Enemies.
    
- Elite.
    
- Zone Boss.
    
- Prison Guardian.
    
- Звичайні експедиції.
    

### Додаткові правила

- General Heart не є Named Drop.
    
- Named Soft Pity не застосовується.
    
- Echo не відновлює сюжетно вбитого Генерала.
    
- First Story Reward і Echo Reward не можуть видаватися одночасно.
    

### Test

First Story General Clear → рівно 1 Heart.

Echo → 30% шанс на 1 Heart.

100 Echo не повинні перетворюватися на 100 гарантованих Hearts через помилку стану.

## 25. DEC-021 — Три слоти експедицій

**Status:** APPROVED_CANON.

**Source:** GDD v2.3; Heroes & Pets Bible v1.2.

### Decision

Рівно три слоти експедицій.

### Slot 1

Після першого Guardian 141 Башти 01-I.

### Slot 2

Після першого очищення трьох Башт Ув'язнення.

### Slot 3

Після першої сюжетної перемоги над будь-яким Генералом.

### Обмеження

- Reputation не відкриває слоти.
    
- Немає четвертого слота.
    
- Слоти залишаються відкритими після Rebirth.
    

## 26. DEC-022 — Перша навчальна розвідка

**Status:** APPROVED_CANON.

**Approved Date:** 2026-10-14.

**Source:** GDD v2.3 §23; World & Towers Bible v1.2 §11.

### Decision

Після першого Guardian 141 Башти 01-I гравець отримує доступ до першої навчальної регіональної розвідки.

### Особливості

- Вона миттєва.
    
- Використовує відкритий слот експедицій.
    
- Гарантовано видає базову нагороду.
    
- Гарантовано відкриває відповідний Dungeon.
    
- Працює один раз за Save.
    

### Наступні регіони

Звичайні Scout Expeditions мають відповідну тривалість.

Вони також гарантовано відкривають власні Данжі після завершення.

### Persistent Flags

- tutorial_scout_completed.
    
- scout_completed[region_id].
    
- dungeon_discovered[region_id].
    

### Заборона

Не застосовувати миттєву тривалість до всіх наступних експедицій.

## 27. DEC-023 — Бонуси Репутації

**Status:** APPROVED_CANON.

**Approved Date:** 2026-10-14.

**Source:** GDD v2.3 §23; Economy Bible v1.2 §16.

### Повна таблиця

|Rank|Reputation XP|Затверджений бонус|
|---|---|---|
|3|1 500|+10% базових ресурсів експедицій|
|7|20 000|−10% тривалості звичайних експедицій|
|9|50 000|−15% Gold Reroll/Refinement|
|10|80 000|−10% Gold eligible high-tier craft|

### Rank 3

Бонус збільшує гарантовану базову кількість ресурсів звичайної експедиції.

Не збільшує Bonus Valuable Roll на 10 процентних пунктів.

### Rank 7

Зменшує базову тривалість звичайної Targeted/Unknown Expedition.

Не робить сюжетні Scout Expeditions миттєвими автоматично.

### Rank 9

Застосовується лише до Gold-компонента:

- Reroll.
    
- Refinement.
    

### Rank 10

Застосовується лише до Gold-компонента рецептів із визначеним прапорцем `eligible_high_tier_crafting`.

Не додає новий Affix Slot.

Не підвищує Affix Cap.

### Заборона

Reputation не відкриває додаткові Expedition Slots.

## 28. DEC-024 — П'ять рівнів якості експедицій

**Status:** APPROVED_CANON.

**Approved Date:** 2026-10-14.

**Source:** GDD v2.3 §23; Economy Bible v1.2 §16.

### Decision

|Reputation Rank|Expedition Quality|Bonus Valuable Roll|
|---|---|---|
|1–2|I|5%|
|3–4|II|10%|
|5–6|III|15%|
|7–8|IV|20%|
|9–10|V|25%|

### Головне правило

Кожна звичайна експедиція гарантовано видає базовий пакет ресурсів.

Bonus Valuable Roll:

- Один додатковий шанс.
    
- Не замінює базову винагороду.
    
- Не гарантує Hero або Mythic Reward.
    
- Не обходить Story Unlocks.
    

### Типи експедицій

- Targeted.
    
- Unknown.
    

### Стандартні тривалості

- 30 хв.
    
- 2 год.
    
- 8 год.
    

### Заборонені винагороди

- General Hearts.
    
- Souls.
    
- Talent Points.
    
- Нелегальні Mythic Materials.
    
- Обхід сюжетних умов.
    

## 29. DEC-025 — Gold Discounts

**Status:** APPROVED_CANON.

**Approved Date:** 2026-10-14.

**Source:** Economy Bible v1.2 §16.

### Decision

Gold Discounts застосовуються мультиплікативно.

Вони не додаються як процентні пункти.

### Forge IV

−10% Gold:

- Eligible Crafting.
    
- Reroll.
    

Forge IV сама по собі не дає знижку Refinement.

### Reputation 9

−15% Gold:

- Reroll.
    
- Refinement.
    

### Reputation 10

−10% Gold:

- Eligible High-Tier Crafting.
    

### Приклад Reroll

Forge IV + Reputation 9:

`GoldFinal = GoldBase × 0.90 × 0.85`

### Приклад Eligible Craft

Forge IV + Reputation 10:

`GoldFinal = GoldBase × 0.90 × 0.90`

### Не дисконтуються

- Materials.
    
- Souls.
    
- Crystals.
    
- Guardian Cores.
    
- General Hearts.
    

### Implementation Rule

Прапорець `eligible_high_tier_crafting` задається в Recipe Data.

Не визначати eligibility на основі тексту кнопки в UI.

## 30. DEC-026 — Talent Tree

**Status:** APPROVED_CANON.

**Source:** Talent Tree Bible v1.1.

### Decision

Базовий каталог має 120 унікальних Talent Node IDs; фінальний релізний обсяг визначається експериментами DEC-042.

### Структура

|Група|Вузли|
|---|---|
|Central Ring|14|
|Manual / Combo|13|
|Auto / Hero / Pets|13|
|Skills / Resonance|13|
|Seven Elemental Sectors|42|
|Resonance Bridges|21|
|Global Keystone|4|
|**Разом**|**120**|

### Keystone Limits

- Максимум два Elemental Keystone.
    
- Максимум один Global Keystone.
    

### Active Talent Skills

Три Active Skills — кандидати на загальні чотири слоти ГГ.

### Presets

Максимум три.

Preset Slots зберігаються після Rebirth.

Фактично придбані Run Talent Ranks скидаються.

### Обмеження

Пресети не обходять:

- Prerequisites.
    
- TP Costs.
    
- Keystone Caps.
    

## 31. DEC-027 — Talent Points

**Status:** APPROVED_CANON для правил видачі та унікальності; окремі числові значення підлягають Balance Tests.

**Source:** Talent Tree Bible v1.1; Economy Bible v1.2.

### Decision

TP — run-based ресурс.

### First Run 01-I

|Подія|TP|
|---|---|
|Floor 100|1|
|Floor 120|1|
|Floor 140|1|
|Guardian 141|2|
|**Разом**|**5**|

### Після відкриття дерева

За унікальний Boss ID один раз у поточному run:

- Prison Zone Boss: 1 TP.
    
- Prison Guardian: 2 TP.
    
- Celestial Zone Boss: 1 TP.
    
- Celestial Commander: 2 TP.
    
- General: 4 TP.
    

### Trial Milestones — Balance v1

- Floor 50: +1 TP.
    
- Floor 100: +1 TP.
    
- Floor 200: +1 TP.
    
- Floor 300: +1 TP.
    

Максимум +4 TP за run із Trial.

### Заборони

- Повторна перемога над тим самим Boss ID у поточному run не дає другий TP.
    
- Direct Challenge не видає повторний TP.
    
- Checkpoint Farming не створює нескінченні TP.
    
- TP не купуються за реальні гроші.
    

## 32. DEC-028 — Rebirth Reset / Keep

**Status:** APPROVED_CANON для структури збереження; числові Seal Multipliers — BALANCE_V1.

**Source:** GDD v2.3; Equipment Bible v1.2; Talent Tree Bible v1.1; Economy Bible v1.2.

### Rebirth відкривається

Після першого Guardian 141 Башти 01-I.

### Скидається

- GG Level.
    
- GG XP.
    
- Gold.
    
- Gold Upgrades.
    
- Run Talent Points.
    
- Фактичні Ranks Run Talents.
    
- Run Floor Position.
    
- Відповідний тимчасовий бойовий стан.
    
- Hero Level.
    
- Hero XP.
    
- Common/Uncommon/Rare Gear за правилами Rebirth.
    

### Зберігається

- Total Souls Collected.
    
- Available Souls.
    
- Soul Skills.
    
- Soul Relics.
    
- Постійні Unlock Flags.
    
- Story General Kills.
    
- World Map Progress.
    
- Dungeon Discoveries.
    
- Hero Collection.
    
- Hero Ascension.
    
- Pet Collection.
    
- Pet Levels.
    
- Pet XP.
    
- Pet Quality.
    
- Pet Stars.
    
- Дозволені Epic–Mythic Items.
    
- Permanent Preset Unlocks.
    
- Збережені Talent Preset Templates.
    
- Відкриті рецепти.
    
- Інший прямо визначений Persistent Progress.
    

### Rebirth Seal

Epic/Legendary/Mythic Gear зберігається з тимчасовим ослабленням.

Точні відсотки й пороги розпечатування — Balance v1.

### Заборона

Не застосовувати Rebirth Reset до всіх полів SaveData одним універсальним очищенням.

## 33. DEC-029 — Soul Currency Model

**Status:** APPROVED_CANON для моделі Total/Available; точний коефіцієнт сили — BALANCE_V1.

**Source:** Talent Tree Bible v1.1; Economy Bible v1.2.

### Два показники

**Total Souls Collected**

Усі історично зібрані Souls.

**Available Souls**

Поточна кількість для покупок.

### Головне правило

Витрата Available Souls не зменшує Total Souls Collected.

### Soul Power — Balance v1

`SoulPowerMult = 1 + 0.10 × TotalSoulsCollected`

### First Rebirth — Balance v1

16 Souls без додаткових бонусів.

### Заборона

Не використовувати старий показник приблизно 252 Souls за перше очищення 141.

Він замінений актуальною робочою економікою.

## 34. DEC-030 — Hero/Pet Progression

**Status:** APPROVED_CANON.

**Source:** Heroes & Pets Bible v1.2.

### Герої

- Рівно 14.
    
- Два на кожну стихію.
    
- Максимум один активний.
    
- Шість Gear Slots.
    
- Одна незмінна стихія.
    
- Hero Level і XP скидаються після Rebirth.
    
- Hero Ascension залишається.
    

### Вихованці

- Рівно 35 видів.
    
- 21 базовий вид.
    
- Сім Legendary.
    
- Сім Mythic.
    
- Максимум два активні.
    
- Pet Level/XP/Quality/Stars зберігаються після Rebirth.
    

### Синтез

Три однакові Pet Species однакової якості → один Pet Instance наступної якості.

Лише Common → Uncommon → Rare → Epic.

### Інкубатор

Миттєвий.

### Заборони

- Epic → Legendary синтезом.
    
- Legendary → Mythic синтезом.
    
- Новий Resonance Channel від Pet Element.
    

## 35. DEC-031 — Постійний сюжетний прогрес

**Status:** APPROVED_CANON.

**Source:** World & Towers Bible v1.2.

### Постійні події

- Перша перемога над Guardian 141 Башти 01-I.
    
- Відкриття World Map.
    
- Перша навчальна Scout Expedition.
    
- Виявлення Dungeon.
    
- Перше очищення Triad.
    
- Отримання Regional Blueprint.
    
- Перша сюжетна перемога над Генералом.
    
- Знищення відповідного Пальця.
    
- Відкриття Trial.
    
- Перемога над Королем Демонів.
    

### Основне правило

Ці події мають Persistent Flags.

Після Rebirth вони не повторюють сюжетні винагороди.

### General Echo

Переможений Генерал може бути повторно викликаний через Echo.

Це не відновлює його сюжетну присутність.

### Atomic Rewards

One-Time Rewards повинні видаватися атомарно та бути захищені від повторного Claim.

## 36. DEC-032 — Архітектура та порядок розробки

**Status:** APPROVED_CANON для data-driven підходу з GDD; конкретні назви файлів і план задач — DEVELOPMENT PLAN.

**Source:** GDD v2.3; Roadmap.

### Основна архітектурна вимога

Геймплей має бути Data-Driven.

Дані ворогів, предметів, Башт, Героїв, вихованців, Loot і Balance повинні бути відокремлені від UI.

### Порядок Vertical Slice

З GDD v2.3:

1. Combat Slice 0–20.
    
2. Slice 20–40.
    
3. Forge.
    
4. Talent Tree.
    
5. Pets.
    
6. Heroes.
    
7. Reaction Focus.
    
8. Campaign Expansion.
    
9. Endgame Expansion.
    

### Development Plan

Додаткові етапи:

- Project Setup.
    
- Save/Load Foundation.
    
- Git.
    
- Tests.
    
- Art Prototype.
    
- Steam Build Preparation.
    

Ці етапи — організація розробки, а не нові правила гри.

### Важливе обмеження

Не реалізовувати всю гру одним великим AI-запитом.

## 37. DEC-033 — Модель релізу Steam

**Status:** APPROVED_CANON.

**Source:** GDD v2.3.

### Decision

- PC.
    
- Steam.
    
- Premium Single-Player First.
    
- Без продажу випадкового вмісту скринь за реальні гроші або внутрішньоігрові валюти. Звичайний бойовий лут зберігається.
    

### Пізніші інтеграції

- Steam Achievements.
    
- Steam Cloud.
    
- Персональні рекорди.
    
- Інші функції після стабілізації Core Build.
    

### Не входить автоматично в MVP

Глобальний конкурентний Leaderboard без серверної перевірки результатів.

### Юридичні деталі

Податки, Steamworks Forms, комерційні ліцензії та інші вимоги треба перевіряти за чинними правилами на момент релізу.

Цей реєстр не замінює офіційних вимог платформи.

## 38. DEC-034 — Числовий баланс

**Status:** BALANCE_V1.

**Source:** Economy & Balance Bible v1.2; Combat Bible v1.2; GDD v2.3.

### Не є остаточно затвердженими числами

- 16 Souls за перший Rebirth.
    
- +10% базової шкоди за кожну історично отриману Soul.
    
- 35% AFK Reward Efficiency.
    
- Enemy HP Growth.
    
- Enemy ATK Growth.
    
- Boss HP Multipliers.
    
- Boss Timers як балансні цілі.
    
- Relative Manual/Auto DPS.
    
- Частина Damage/Resonance ICD та Caps.
    
- Gear Upgrade Costs.
    
- Rebirth Seal Strength.
    
- Rebirth Seal Recovery Floors.
    
- Прямі ціни Героїв у Souls.
    
- Темп гарантованих Hero/Pet нагород.
    
- Named Drop Rates.
    
- Pet/Hero Damage Coefficients.
    
- Expedition Resource Yield.
    
- Expedition Hero XP.
    
- Інші параметри, позначені Balance v1.
    

### Важлива відмінність

Не кожне число автоматично є BALANCE_V1.

Наприклад:

- 7 стихій — Canon.
    
- 141 поверх — Canon.
    
- Пороги 4/5 та 3/4 — Canon.
    
- 40% Repeat Guardian Material — погоджене правило.
    
- 30% Echo General Heart — погоджене правило.
    

### Принцип

Коригування Balance v1 потребує відповідного тесту та запису рішення.

Не змінювати значення приховано всередині Combat Script.

## 39. DEC-035 — Художні параметри

**Status:** OPEN / PRODUCTION TBD.

**Source:** Art Direction.

### Уже затверджено

- Stylized 2D Dark Fantasy.
    
- Чіткі силуети.
    
- Високий контраст.
    
- Багатошарові 2D-фони.
    
- Виразні Elemental VFX.
    
- Читабельні Boss Telegraphs.
    
- Єдина художня мова.
    

### Ще потрібно визначити

- Фінальна техніка малювання.
    
- Товщина контурів.
    
- Рівень деталізації.
    
- Базова роздільна здатність.
    
- Розмір спрайтів.
    
- Розмір Inventory Icons.
    
- Конкретні шрифти.
    
- Фінальні UI Colors.
    
- Рівень анімаційної складності.
    
- Остаточний Character Design ГГ.
    
- Фінальні Style References.
    

### Заборона

Не вважати незатверджений AI Concept Art фінальним стилем усієї гри.

## 39A. DEC-036 — Enemy Action / Cast Bar та механіка Interrupt

**Status:** APPROVED_CANON для механіки та UI; таймінги заповнення — BALANCE_V1.

**Date:** 2026-10-24.

**Category:** Combat / Enemies / UI.

### Decision

Під смужкою HP кожного ворога на бойовій сцені розміщується смужка поточної дії (`EnemyCastBar`) із текстовою назвою дії всередині:

1. **Базова атака (`SWING_UNINTERRUPTIBLE`):**
   - Використовується всіма звичайними ворогами (`Normal Enemy`, `Elite Enemy`) та босами між здібностями.
   - Заповнюється за `attack_period`, підібраним відносно kill time; 5–7 с не є загальним стандартом для всіх мобів.
   - Підпис усередині смужки: `«Атака»`.
   - Дія не може бути перервана гравцем. Після заповнення ворог завдає базової шкоди ГГ.
2. **Каст активної навички (`SKILL_INTERRUPTIBLE`):**
   - Використовується босами (`Zone Boss`, `Prison Guardian`, `Celestial Commander`, `General`, `Demon King`), коли вони активують навичку чи контроль (наприклад, `Stun`, `Silence`, важкий удар).
   - Підпис усередині смужки змінюється на назву навички (наприклад, `«Оглушення»`).
   - Якщо під час заповнення цієї смужки по босу влучає активна навичка ГГ із властивістю переривання (`can_interrupt = true`), каст боса миттєво збивається, шкода/ефект навички боса не наноситься, а на смужці відображається стан `«ПЕРЕРВАНО!»`.

### Affected Documents

- 01_Game_Overview.md
- 02_Core_Rules.md
- Systems/Combat.md
- World/Enemies.md
- Characters/Main_Character.md
- Art/Art_Direction.md

## 39B. DEC-037 — Візуальна доставка навичок (Impact Sync) та процедурна анімація

**Status:** APPROVED_CANON.

**Date:** 2026-10-24.

**Category:** Combat / Art / Animation.

### Decision

1. **Синхронізація удару навичок зі снарядами (Projectile Impact Sync):**
   - Навички спрямованого удару або падіння зверху (зокрема вогняна навичка «Метеор») повинні візуально прилітати у ворога на сцені (через `Tween` за `0.20–0.30` с — Balance v1).
   - Розрахунок шкоди, перевірка `Interrupt`, поява Damage Numbers та Hit Reaction ворога виконуються строго в момент візуального влучання снаряда по цілі.
2. **Процедурна анімація звичайних мобів:**
   - Звичайні вороги (`Normal` / `Elite`) не потребують ручної скелетної порізки кінцівок; їхні спрайти оживляються програмно через вершинний шейдер дихання та `Tween`-деформації (`Squash & Stretch` при отриманні удару та випад уперед при атаці).
   - Пошарова скелетна анімація (`Skeleton2D` на 4–5 шарів) використовується для Головного Героя.

## 40. Відкриті питання — реєстр

Питання нижче не мають статусу APPROVED_CANON.

|ID|Питання|Статус|Основний документ|
|---|---|---|---|
|OPEN-001|Фінальний стиль 2D-графіки|OPEN|Art Direction|
|OPEN-002|Hero Weapon Compatibility|OPEN|Equipment / Heroes|
|OPEN-003|Фінальна Hero XP Curve та BaseDPS|BALANCE_V1|Heroes|
|OPEN-004|Pet XP Curve та Essence Yield|BALANCE_V1|Pets|
|OPEN-005|Остаточні Expedition Resource Yields|BALANCE_V1|Expeditions / Economy|
|OPEN-006|Тривалість регіональних Scout Expeditions|BALANCE_V1|Expeditions|
|OPEN-007|Точні Hero Skills із неповним числовим описом|OPEN|Heroes|
|OPEN-008|5★ Ultimate Evolutions усіх Героїв|OPEN|Heroes|
|OPEN-009|Ціни прямої купівлі Героїв, Sigil/Special Essence yields і квестові пороги|OPEN / BALANCE_V1|Economy / Heroes / Pets|
|OPEN-010|Довгостроковий Soul Power Scaling|BALANCE_V1|Economy / Progression|
|OPEN-011|Остаточний Rebirth Seal Curve|BALANCE_V1|Equipment / Economy|
|OPEN-012|Фінальні Boss DPS/HP Curves|BALANCE_V1|Combat / Economy|
|OPEN-013|Точні Attack Speed/Recovery/RES Caps|BALANCE_V1|Combat|
|OPEN-014|Фінальна петова Pair Priority|OPEN|Pets|
|OPEN-015|Точні 5★ Pet Bonus Stacking Rules|BALANCE_V1|Pets|
|OPEN-016|Фінальні Art Asset Formats і Dimensions|OPEN|Art Direction|
|OPEN-017|Технічна політика Hero XP під час активної експедиції через Rebirth|OPEN|Heroes / Expeditions|
|OPEN-018|Точні умови виявлення координат Небесних Веж 2–4|OPEN|Towers / Expeditions|

### Правило для OPEN

Claude Code не повинен мовчки переводити OPEN у APPROVED_CANON.

Якщо відкрите питання блокує реалізацію:

1. Зафіксувати блокер.
    
2. Показати можливі варіанти.
    
3. Пояснити наслідки.
    
4. Отримати рішення розробника.
    
5. Записати новий Decision ID.
    
6. Оновити відповідний документ.
    

## 41. Замінені правила — Superseded Registry

Ця таблиця потрібна, щоб Claude Code не повертався до застарілих версій документації.

|Старий варіант|Чинне правило|Status|
|---|---|---|
|П'ять базових стихій|Сім стихій|SUPERSEDED|
|3/5 броні для Primary|4/5 броні|SUPERSEDED|
|2/4 аксесуарів для Secondary|3/4 аксесуарів|SUPERSEDED|
|Auto Attack на Floor 10 або лише після входу в 01-II|Перша перемога над босом 20 Башти 01-I (редакція 2026-11-04)|SUPERSEDED|
|Trial повністю доступна одразу після 141|141 Reveal → General Access → King Full|SUPERSEDED|
|Приблизно 252 Souls за першу Башту|16 Souls — Balance v1|SUPERSEDED|
|Offline Cap 12 год|24 год|SUPERSEDED|
|Enchant I отримує подаровані Element Crystals на Floor 80|Рецепт доступний без безкоштовних кристалів|SUPERSEDED|
|Умови Веж 5/6 можна виконати частково|Усі три гейти обов'язкові, AND|SUPERSEDED|

### Важлива примітка

Ця таблиця не означає, що старі версії Word потрібно видаляти.

Вони можуть залишатися архівними.

Але Claude Code має користуватися чинними специфікаціями.

## 42. Правило зміни вже затвердженого рішення

Якщо розробник вирішив змінити Canon:

1. Знайти поточний Decision ID.
    
2. Встановити причину зміни.
    
3. Створити новий Decision ID.
    
4. Позначити старе рішення SUPERSEDED.
    
5. Вказати, що його замінило.
    
6. Оновити спеціалізовану Bible/Markdown.
    
7. Оновити залежні документи.
    
8. Визначити вплив на Godot.
    
9. Додати потрібну Save Migration.
    
10. Виконати Regression Tests.
    

### Заборона

Не редагувати історію так, ніби попереднє рішення ніколи не існувало.

## 43. Правило зміни Balance v1

Числовий баланс можна уточнювати після тестування.

### Для кожної зміни зафіксувати

- Параметр.
    
- Старе значення.
    
- Нове значення.
    
- Причину зміни.
    
- Дані тесту.
    
- Затвердження.
    
- Версію Balance Config.
    

### Приклад формату

**Decision ID:** BAL-001.

**Status:** BALANCE_V1.

**Parameter:** Boss HP Multiplier.

**Old Value:** із поточного Balance Config.

**New Value:** не визначено до плейтесту.

**Reason:** потрібно перевірити доступний DPS для запланованої тривалості бою.

**Source:** Economy Bible.

### Важлива відмінність

Зміна числа Boss HP не повинна автоматично змінювати кількість поверхів Башти.

Зміна Soul Reward не повинна автоматично скасовувати Rebirth.

Балансні числа й структурний канон потрібно зберігати окремо.

## 44. Decision Authority

### Розробник

Може:

- Затверджувати нові рішення.
    
- Змінювати Canon.
    
- Погоджувати Balance.
    
- Вибирати Art Direction.
    
- Визначати архітектурні пріоритети.
    

### Claude Code

Може:

- Читати чинні рішення.
    
- Реалізовувати вже затверджене.
    
- Виявляти суперечності.
    
- Пропонувати рішення.
    
- Пояснювати ризики.
    
- Оновлювати документацію після погодження.
    

### Claude Code не може самостійно

- Змінювати кількість регіонів.
    
- Змінювати прогресію Башт.
    
- Додавати нові стихії.
    
- Змінювати гейти.
    
- Змінювати First-Clear Rewards.
    
- Створювати нові механіки, що суперечать канону.
    
- Оголошувати власні припущення затвердженими рішеннями.
    

## 45. Протокол перевірки перед реалізацією

Перед реалізацією будь-якої системи Claude Code повинен:

1. Визначити назву системи.
    
2. Знайти її документ.
    
3. Перевірити відповідні DEC IDs.
    
4. Перевірити статуси.
    
5. Визначити всі OPEN Questions.
    
6. Визначити Balance v1 Parameters.
    
7. Перевірити наявний код.
    
8. Підготувати короткий план.
    
9. Вказати файли для зміни.
    
10. Не починати спірну реалізацію без погодження.
    

### Якщо рішення APPROVED_CANON

Реалізувати точно.

### Якщо параметр BALANCE_V1

Використовувати відповідне значення з єдиного Balance Config, позначаючи його як робоче.

### Якщо питання OPEN

Запропонувати варіанти та отримати рішення.

### Якщо старе рішення SUPERSEDED

Не використовувати його.

## 46. Система синхронізації документації

Після зміни рішення перевірити:

- 02_Core_Rules.md
    
- Відповідний Systems File
    
- Відповідний World File
    
- Відповідний Characters File
    
- Art_Direction.md, якщо потрібно
    
- Roadmap.md, якщо змінився обсяг роботи
    
- Task_Log.md, якщо вже змінено код
    
- Save Migration, якщо змінилося збереження
    
- Tests, якщо змінилася очікувана поведінка
    

### Приклад

Якщо змінюється Guardian Material Chance:

- Decisions.
    
- World/Enemies.
    
- World/Towers.
    
- Systems/Economy.
    
- Systems/Crafting, якщо змінюється доступність матеріалу.
    
- Reward Tests.
    

Не змінювати лише один файл, якщо правило дублюється у кількох специфікаціях.

## 47. Технічні інваріанти

Незалежно від реалізації повинно бути правдою:

### World

- Рівно сім регіонів.
    
- Рівно 21 Prison Tower.
    
- Рівно сім Celestial Tower.
    
- Рівно сім Elemental Dungeon.
    

### Combat

- Рівно сім Elements.
    
- Рівно 21 Double Resonance.
    
- Рівно 35 Triple Resonance.
    
- Не більше чотирьох Active Skill Slots ГГ.
    

### Equipment

- 12 слотів ГГ.
    
- Шість слотів союзного Героя.
    
- Сім типів зброї.
    
- Primary Threshold 4/5.
    
- Secondary Threshold 3/4.
    

### Characters

- 14 Heroes.
    
- 35 Pet Species.
    
- Один активний Герой.
    
- Два активні пети.
    

### Progression

- Базовий каталог 120 Talent Nodes; фінальний обсяг OPEN за DEC-042.
    
- Один TP Reward за конкретного Boss ID у поточному run.
    
- One-Time Story Rewards не дублюються.
    
- Permanent Unlocks переживають Rebirth.
    

### Economy

- Guardian Special Material First Clear = 1.
    
- Repeat Guardian = 40% на 1.
    
- General Story Heart = 1.
    
- General Echo Heart = 30% на 1.
    
- Named Pity не впливає на ці Special Material Rolls.
    

## 48. Перевірка Decisions Log

- Усі DEC IDs унікальні.
    
- Для кожного рішення є Status.
    
- Для кожного рішення вказане джерело.
    
- Відомі дати затвердження не вигадані.
    
- Балансні значення не позначені автоматично Canon.
    
- Open Questions не приховані.
    
- Старі правила мають SUPERSEDED.
    
- Немає двох одночасно чинних суперечливих рішень.
    
- Рішення відповідають спеціалізованим Bible.
    
- Зміна Canon створює новий Decision Record.
    
- Залежні документи синхронізуються.
    
- Claude Code не змінює рішення без погодження.
    

## 49. Пов'язані документи

- [Головні правила](../02_Core_Rules.md)
    
- [Огляд гри](../01_Game_Overview.md)
    
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
    
- [Main Character](../Characters/Main_Character.md)
    
- [Heroes](../Characters/Heroes.md)
    
- [Pets](../Characters/Pets.md)
    
- [Art Direction](../Art/Art_Direction.md)
    
- [Roadmap](Roadmap.md)
    
- [Task Log](Task_Log.md)
    

### Пріоритет спеціалізованих Bible

- GDD — загальна концепція та FTUE.
    
- Combat — стихії, резонанси, damage formula.
    
- Equipment — слоти, Rarity/Rank/Upgrade.
    
- Forge — рецепти, крафт, Reroll/Refine.
    
- Talent Tree — 120 вузлів, TP, Soul Skills.
    
- Enemies — вороги, Bosses, Loot.
    
- Heroes & Pets — союзники, інкубатор, експедиції.
    
- Economy — числова економіка, Souls, AFK.
    
- World & Towers — географія, Башти, Данжі, сюжетні гейти.
    
- Lore & Art — сюжет і художня ідентичність.
    

Цей реєстр містить погоджені обмеження, але точні алгоритми потрібно брати з відповідного джерела.

## 50. Підсумок

Система рішень розділяє:

**Що затверджено:**

Структура світу, бойова система, канали стихій, розміри контенту, відкриття функцій, Rebirth, матеріали Стражів/Генералів, Репутація та експедиції.

**Що ще балансується:**

HP/DPS, Soul Power, AFK, прямі ціни Героїв, частина Drop Rates, економічні криві, Rebirth Seal та інші Balance v1 Parameters.

**Що ще потрібно погодити:**

Фінальні творчі деталі, художній стиль, окремі недостатньо визначені здібності, Weapon Compatibility союзних Героїв та конкретні технічні рішення реалізації.

---

**Статус документа:** Decision Register — Draft.

**Останні погоджені джерела:** GDD v2.3 та Design Bible v1.2 / Talent Tree v1.1.

**Дата головних фінальних уточнень:** 2026-10-14.

**Нові рішення:** записуються окремими DEC IDs.

**Старі рішення:** не видаляються, а позначаються SUPERSEDED.

**Головний принцип:** Claude Code може пропонувати зміни, але тільки розробник затверджує новий канон.

## 51. Пакет рішень розробника від 2026-11-04

**Джерело:** пряме погодження пунктів 1–7 і уточнення 7–9 у поточній розмові. Ці рішення мають пріоритет над суперечними правилами попередніх Word Bible. Оновлення документів не означає реалізації в Godot.

### DEC-038 — Гарантовані Герої

**Status:** APPROVED_CANON; ціни/точні квестові умови — OPEN Content/Balance v1.

Ростер 14 збережено. Усі Герої мають гарантоване джерело; дозволені конкретні покупки за Available Souls після сюжетного відкриття, без випадкового персонажа. Сільва на Floor 130 і таємні квестові H08/H10 зберігаються. Steam Achievements не є технічною залежністю нагороди. Heroes §30–31 — детальні правила.

### DEC-039 — Ascension

**Status:** APPROVED_CANON; дохід та складність — BALANCE_V1 / OPEN.

П'ять зірок та персональні Sigils збережено. Джерело — гарантовані повторювані персональні бойові випробування, не дублікати зі скринь. Вартість 1/2/3/5 збережена як початковий баланс. Повторна купівля або одноразовий quest claim не дає Sigil. Heroes §27.

### DEC-040 — Скрині та вихованці

**Status:** APPROVED_CANON; конкретні квестові encounter IDs/нагороди — OPEN Content/Balance v1.

Куповані випадкові Chest I/II/III та їхні pity вилучено. Бойовий випадковий лут і Named Soft Pity збережено. 35 видів петів збережено; всі L01–L07/M01–M07 мають гарантовані видові квести та повторювані джерела розвитку за Pets §20. Герої та потрібні сюжетні підказки не залежать від випадкової експедиції. Economy §20, Expeditions §19–20.

### DEC-041 — Вигляд ГГ

**Status:** APPROVED_CANON.

В бою та у вікні персонажа змінюється тільки зброя. Броня, аксесуари, щит і плащ не змінюють одяг/силует. Статистики та 12 слотів збережено. Стихійні аури залишаються окремими бойовими ефектами. Art Direction §64.

### DEC-042 — Обсяг талантів

**Status:** APPROVED_TEST_PLAN; фінальна кількість OPEN.

DEC-026 зберігає базовий каталог 120 вузлів, але не встановлює незмінний фінальний релізний розмір. Практично порівняти 30–40 та 100–120; близько 140 — додатковий експеримент лише за потреби. ID не видаляються; профілі явно визначають prerequisites/TP/Keystone, зберігають profile_id. Протокол — Talents §34.

### DEC-043 — Повний контент

**Status:** APPROVED_CANON.

49 сімейств / 147 Mob Variants залишаються ціллю кінцевого повного релізу, як і весь ростер 14 Героїв. Демо/прототип — менший зріз. Зменшення повної гри до одного регіону, дев'яти мобів або 3–5 Героїв не затверджено. Enemies §44, Roadmap §46.

### DEC-044 — Ціна

**Status:** OPEN; процес оцінки погоджено.

Фіксована ціна та стартова знижка не затверджені. Повернутися після демо, фестивалів та оцінки реакції/числа гравців і фактичного контенту. Раніше обговорені $7.99/10% не є зобов'язанням.

### DEC-045 — Уточнення DEC-036/037

**Status:** APPROVED_CANON для внесеної розробником основи; додані деталі реалізації — робоча дизайн-пропозиція, нові числові таймінги — BALANCE_V1.

Збережено внесені розробником непереривні базові удари, переривні касти босів та Impact Sync. Додано явний стан непереривної здібності, захист від безперервного Interrupt, збереження прогресу swing, максимум одне успішне переривання на активацію навички, прив'язку снаряда до початкової цілі та незалежність бою від декоративної анімації. Combat §9.4 і Enemies §22.7 задають точний порядок.

На Floor 10 відкривається utility_interrupt у наявному слоті ГГ; без стихії/талантів і без шкоди, CD 12 с — Balance v1. Auto Attack відкривається після боса 20 за оновленим DEC-016. Метеор залишається окремою навичкою зі своїми прогресійними умовами. Візуальні/числові параметри ще не перевірені в Godot.
