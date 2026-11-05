---

status: draft  
document_type: crafting-system  
source: Crafting & Forge Recipe Bible v1.2  
balance_status: Balance v1  
updated: 2026-10-15  
tags:

- game-system
    
- crafting
    
- forge
    
- equipment
    
- economy
    
- godot
    

---

# CRAFTING & FORGE SYSTEM — Кузня та рецепти

> Технічна специфікація створення предметів, підвищення Rank, Upgrade, Synthesis, Enchantment, Reroll, Refinement, Named Blueprints і матеріальних конверсій.
> 
> Основне джерело: Crafting & Forge Recipe Bible v1.2.
> 
> Механіки та обмеження — Canon. Ціни, кількості матеріалів, шанси та бонусні коефіцієнти — Balance v1, якщо не затверджені окремим рішенням.

## 1. Призначення системи

Кузня забезпечує створення та довгострокове покращення спорядження Головного Героя.

Основні функції:

- Створення звичайного спорядження.
    
- Випадковий або контрольований Rank.
    
- Підвищення Rank 0–12.
    
- Upgrade +0–30.
    
- Синтез 3→1.
    
- Стихійне зачарування I–V.
    
- Зняття та заміна стихій.
    
- Affix Reroll.
    
- Affix Lock.
    
- Refinement.
    
- Розбирання предметів.
    
- Переплавлення матеріалів.
    
- Створення іменних предметів.
    
- Відкриття постійних креслень.
    

Кузня повинна давати гравцю можливість поступово створювати потрібний білд, але високорівневі предмети мають вимагати проходження відповідного контенту.

Не можна отримати всі найкращі предмети тільки за Gold.

## 2. Основні терміни

### Rarity

Якість предмета:

Common → Uncommon → Rare → Epic → Legendary → Mythic.

### Rank

Головна довгострокова прогресія предмета.

- Початковий Rank 0.
    
- Максимальний Rank 12.
    
- Чотири стадії по три Rank.
    

### Upgrade Level

Окреме числове покращення предмета.

- Мінімум +0.
    
- Максимум +30.
    
- Не замінює Rank.
    

### Soul Relic

Постійне Soul-покращення без слота екіпірування.

Не є предметом звичайного спорядження.

### Named Artifact

Іменний предмет зі слотом, Rarity, Rank, Upgrade та унікальною властивістю.

### Regional Blueprint

Постійне креслення, яке відкривається після першого очищення відповідної Тріади Печатей.

### Enhanced Named Blueprint

Постійне креслення, яке відкривається через спеціальний ритуал трьох однакових іменних предметів.

Regional Blueprint та Enhanced Named Blueprint — різні категорії.

## 3. Чотири рівні Кузні

### Forge I — Коваль

**Відкриття:** поверх 80 першої Башти Ув'язнення 01-I.

Доступно:

- Рецепти Common–Epic.
    
- Крафт із випадковим Rank.
    
- Rank Up.
    
- Upgrade +0–30.
    
- Synthesis 3→1.
    
- Salvage.
    
- Enchantment I.
    

Уточнення FTUE:

- Craft, Upgrade, Synthesis та Salvage доступні одразу.
    
- Enchantment I показується як доступний рецепт.
    
- Для застосування Enchant необхідні матеріали.
    
- Гравець НЕ отримує гарантовані безкоштовні Element Crystals на 80-му поверсі.
    

### Forge II — Арканіст

**Відкриття:** після відкриття першої Небесної Вежі за прогресом першої Башти 141.

Доступно:

- Affix Reroll.
    
- Affix Lock.
    
- Refinement.
    
- Enchantment II–III.
    
- Переплавлення матеріалів до Legendary.
    
- Крафт за доступними кресленнями.
    

Forge II не є першою можливістю зачарувати предмет: Enchant I доступний уже у Forge I.

### Forge III — Майстер Печатей

**Відкриття:** перемога над двома різними Генералами.

Доступно:

- Контрольований вибір цільового Rank.
    
- Гарантоване отримання вибраного доступного Rank за повну вартість.
    
- Enchantment IV–V.
    
- Зняття стихійного зачарування.
    
- Заміна стихії.
    

Контрольований Rank не гарантує високоякісних Affix rolls.

### Forge IV — Архіковаль

**Відкриття:** перемога над п'ятьма різними Генералами.

Доступно:

- Розширені іменні рецепти.
    
- Автоматизація операцій Кузні.
    
- −10% Gold-вартості Craft.
    
- −10% Gold-вартості Reroll.
    

Знижка Forge IV не застосовується автоматично до Refinement.

Не застосовувати знижку Forge IV до матеріалів, Crystals або Souls.

## 4. Основні матеріали

### 4.1. Руда та метали

Шість якостей:

|Якість|Руда|Оброблений метал|
|---|---|---|
|Common|Залізна руда|Залізний злиток|
|Uncommon|Очищена руда|Загартована сталь|
|Rare|Лазурна руда|Лазурний сплав|
|Epic|Рунічна руда|Рунічний сплав|
|Legendary|Зоряна руда|Зорекований метал|
|Mythic|Прадавня руда|Первісний сплав|

Назви матеріалів належать до Content v1.

Ієрархія та роль матеріалів — Canon.

### 4.2. Регіональні трофеї

Рецепти можуть вимагати матеріали конкретних сімей ворогів.

Технічна категорія:

`REGION_TROPHY(region_id, quality)`

У грі існують 49 сімейних трофеїв із затверджених регіональних каталогів.

Якість і ID трофея зберігаються окремо.

Не створювати випадковий абстрактний «регіональний матеріал» замість конкретного трофея.

### 4.3. Guardian Cores

Спеціальні матеріали 21 Стража Башт Ув'язнення.

Технічна категорія:

`PRISON_GUARDIAN_CORE(guardian_id)`

Використовуються:

- Rank 7–10.
    
- Іменні рецепти.
    
- Окремі операції Refinement.
    
- Регіональні креслення.
    

### 4.4. Celestial Commander Cores

Матеріали 42 командирів Небесних Веж.

Технічна категорія:

`CELESTIAL_COMMAND_CORE(commander_id)`

Використовуються для:

- Rank 9–12.
    
- Іменного крафту.
    
- Високорівневих рецептів.
    

### 4.5. General Hearts

Сім унікальних компонентів Генералів.

Використовуються для:

- Rank 11–12.
    
- Mythic crafting.
    
- Enhanced Named recipes.
    

General Hearts не є звичайними Guardian Cores.

### 4.6. Element Crystals

Сім окремих стихійних матеріалів:

- Fire Crystal.
    
- Water Crystal.
    
- Nature Crystal.
    
- Light Crystal.
    
- Dark Crystal.
    
- Lightning Crystal.
    
- Wind Crystal.
    

Використовуються для Enchant I–V та пов'язаних операцій.

Не плутати Element Crystals із валютою Crystals.

### 4.7. Forge Dust

Отримується через Salvage.

Має якість Common–Mythic.

Використовується для Reroll, Refinement та каталізаторів.

## 5. Формування вартості

Базові числові таблиці розраховані для Common Armor.

Для інших якостей і категорій використовуються множники.

### 5.1. Rarity Cost Multiplier — Balance v1

|Rarity|Cost ×|
|---|---|
|Common|1.00|
|Uncommon|1.20|
|Rare|1.60|
|Epic|2.40|
|Legendary|4.00|
|Mythic|7.50|

### 5.2. Category Cost Multiplier — Balance v1

|Категорія|Cost ×|
|---|---|
|Основна броня / плащ|1.00|
|Щит|1.10|
|Основна зброя|1.20|
|Аксесуари|1.35|
|Named Craft|1.50|

### 5.3. Базова формула

`BaseOperationCost × RarityMultiplier × CategoryMultiplier`

Кількості звичайних матеріалів округлюються вгору.

Не множити кількість спеціальних Boss Cores та Mythic Ore/Metal автоматично, якщо рецепт визначає їх як окрему фіксовану вимогу.

Усі ці коефіцієнти — Balance v1.

Спеціальні рецепти можуть використовувати власні явні витрати. Не застосовувати повторно той самий множник, якщо він уже врахований у вартості рецепта.

## 6. Створення предметів

### 6.1. Загальна процедура

1. Гравець вибирає тип предмета.
    
2. Вибирає Rarity.
    
3. За потреби вибирає регіон або доступний рецепт.
    
4. Система перевіряє матеріали та відкритий Forge Level.
    
5. Визначається доступний Rank Range.
    
6. Показується майбутній результат або його ймовірності.
    
7. Після підтвердження списуються матеріали.
    
8. Генерується предмет.
    
9. Зберігається новий стан інвентарю.
    

### 6.2. Forge I–II: Random Rank

Гравець може визначити:

- Тип предмета.
    
- Rarity.
    
- Дозволений Rank Range.
    
- Від 0 до 5 каталізаторів.
    

Rank генерується випадково в межах доступного діапазону.

### 6.3. Каталізатори — Balance v1

|Кількість|Додаткові матеріали|Шанс верхньої третини Rank|
|---|---|---|
|0|Немає|20%|
|1|1 Rare Dust|26%|
|2|2 Rare Dust|32%|
|3|3 Rare + 1 Epic Dust|38%|
|4|4 Rare + 2 Epic Dust|44%|
|5|5 Rare + 3 Epic Dust|50%|

Каталізатори не розширюють максимальний доступний Rank.

Шанси всіх можливих результатів повинні давати 100%.

Гравець бачить імовірності до підтвердження крафту.

### 6.4. Forge III–IV: Controlled Rank

Гравець може вибрати конкретний доступний Rank.

Результат гарантовано отримує обраний Rank після оплати повної вартості.

Однак:

- Affixes залишаються випадковими.
    
- Main Stat rolls залишаються випадковими.
    
- Потрібні матеріали повинні бути доступні.
    
- Сюжетні вимоги не обходяться.
    

## 7. Базові рецепти Common Rank 0

Усі наведені кількості — Balance v1.

`Metal Q`, `Ore Q`, `Trophy Q` означають матеріали відповідної якості та дозволеного походження.

### 7.1. Сім типів зброї

|Зброя|Metal|Ore|Trophy|
|---|---|---|---|
|Шипований ланцюг / Батіг|7|2|5|
|Важкий молот / Булава|12|5|4|
|Бойова коса|9|3|6|
|Посох окультиста|6|4|8|
|Спис / Partisan|9|4|5|
|Кинджал / Dirk|6|2|4|
|Одноручний меч|8|3|5|

### 7.2. Інші одинадцять слотів

|Слот|Metal|Ore|Trophy|
|---|---|---|---|
|Шолом|5|3|4|
|Нагрудник|11|5|6|
|Рукавички|4|2|4|
|Штани|9|4|5|
|Черевики|6|3|5|
|Щит|10|5|5|
|Плащ|5|3|7|
|Амулет|5|2|8|
|Перстень|4|2|6|
|Пояс|5|3|6|
|Сережки|4|2|7|

Типи гарантованих Main Stats визначає [Equipment](Equipment.md).

Rank Up оплачується окремо.

## 8. Rank Up 0–12

Підвищення Rank завжди успішне на 100%.

Один перехід підвищує Rank рівно на один рівень.

### 8.1. Таблиця витрат Rank — Balance v1

Ціни наведені для базового Common Armor.

|Перехід|Gold|Матеріали|
|---|---|---|
|R0→R1|12 000|12 Common Ore, 8 Common Metal, 3 Common Trophy|
|R1→R2|18 000|18 Common Ore, 12 Uncommon Metal, 5 Common Trophy|
|R2→R3|28 000|24 Common Ore, 16 Uncommon Metal, 7 Uncommon Trophy|
|R3→R4|50 000|22 Uncommon Ore, 14 Rare Metal, 8 Uncommon Trophy|
|R4→R5|80 000|30 Uncommon Ore, 21 Rare Metal, 10 Rare Trophy|
|R5→R6|130 000|36 Uncommon Ore, 26 Rare Metal, 12 Rare Trophy + 1 тематичний Zone Boss Trophy|
|R6→R7|400 000|34 Rare Ore, 19 Epic Metal, 14 Rare Trophy + 1 Guardian Core|
|R7→R8|800 000|43 Rare Ore, 27 Epic Metal, 18 Epic Trophy + 2 Guardian Cores|
|R8→R9|1 800 000|51 Rare Ore, 34 Epic Metal, 3 Legendary Metal + 1 Commander Core|
|R9→R10|6 500 000|65 Epic Ore, 38 Legendary Metal, 22 Epic Trophy + 2 Commander Cores|
|R10→R11|18 000 000|70 Epic Ore, 42 Legendary Metal, 2 Mythic Ore + 1 General Heart|
|R11→R12|50 000 000|80 Legendary Ore, 50 Legendary Metal, 4 Mythic Ore, 2 Mythic Metal + 2 General Hearts|

Для іншої Rarity/категорії застосовуються відповідні множники до Gold та звичайних матеріалів.

Кількості спеціальних Boss Cores і Mythic матеріалів не масштабуються автоматично.

### 8.2. Збереження характеристик

Rank Up не змінює:

- Item ID.
    
- Rarity.
    
- Upgrade Level.
    
- Типи Main Stats.
    
- Affix IDs.
    
- Element Enchant.
    
- Roll Fraction характеристик.
    

### 8.3. Roll Fraction

Кожна характеристика має збережену позицію в дозволеному діапазоні:

`roll_fraction ∈ [0, 1]`

Після зміни Rank:

`NewStat = NewMin + RollFraction × (NewMax − NewMin)`

Хороший початковий roll повинен залишатися хорошим після підвищення Rank.

Не застосовувати Rank Bonus двічі.

## 9. Upgrade Level +0–30

Upgrade покращує числові характеристики предмета.

- Максимум +30.
    
- Успіх 100%.
    
- Не змінює Rarity.
    
- Не змінює Rank.
    
- Не змінює Affix Pool.
    
- Не знищує предмет.
    

### 9.1. Формула Gold — Balance v1

`GoldBase = round(200 × 1.35^(TargetLevel − 1))`

Базова ціна для Common Armor.

### 9.2. Upgrade +1–10

|Target|Gold|Materials|
|---|---|---|
|+1|200|2 Common Ore|
|+2|270|2 Common Ore|
|+3|365|3 Common Ore|
|+4|492|3 Common Ore|
|+5|664|3 Common Ore|
|+6|897|4 Common Ore|
|+7|1 211|4 Common Ore|
|+8|1 634|4 Common Ore|
|+9|2 206|5 Common Ore|
|+10|2 979|5 Common Ore|

### 9.3. Upgrade +11–20

|Target|Gold|Ore|Additional|
|---|---|---|---|
|+11|4 021|4 Rare|1 Uncommon Metal|
|+12|5 429|4 Rare|1 Uncommon Metal|
|+13|7 329|5 Rare|1 Uncommon Metal|
|+14|9 894|5 Rare|1 Uncommon Metal|
|+15|13 357|6 Rare|1 Uncommon Metal|
|+16|18 032|6 Rare|2 Uncommon Metal|
|+17|24 343|7 Rare|2 Uncommon Metal|
|+18|32 863|7 Rare|2 Uncommon Metal|
|+19|44 365|8 Rare|2 Uncommon Metal|
|+20|59 892|8 Rare|2 Uncommon Metal|

### 9.4. Upgrade +21–30

|Target|Gold|Ore|Additional|
|---|---|---|---|
|+21|80 855|8 Epic|2 Rare Metal|
|+22|109 154|8 Epic|2 Rare Metal|
|+23|147 358|9 Epic|2 Rare Metal|
|+24|198 933|9 Epic|2 Rare Metal|
|+25|268 559|10 Epic|3 Rare Metal|
|+26|362 555|10 Epic|3 Rare Metal|
|+27|489 450|11 Epic|3 Rare Metal|
|+28|660 757|11 Epic|3 Rare Metal|
|+29|892 022|12 Epic|4 Rare Metal|
|+30|1 204 230|12 Epic|4 Rare Metal|

### 9.5. Підсилення характеристик

Balance v1:

- +1.2% Main Stat Power за Upgrade Level.
    
- Максимум +36% на +30 до відповідної бази.
    

Для розрахунку сили предмета використовувати формулу Equipment Bible.

Не застосовувати Upgrade Bonus двічі.

## 10. Synthesis 3→1

Три предмети однакового підтипу та Rarity перетворюються на один предмет наступної якості.

Приклад:

`3 Rare Daggers → 1 Epic Dagger`

### 10.1. Вимоги

- Однаковий тип предмета.
    
- Однакова Rarity.
    
- Для зброї — однаковий підтип.
    
- Для аксесуарів — однаковий слот.
    
- Не перевищувати Mythic.
    

### 10.2. Результат

- Rarity підвищується на один рівень.
    
- Rank визначається випадково в дозволеному діапазоні.
    
- Upgrade Level = +0.
    
- Main Stats генеруються заново.
    
- Affixes генеруються заново.
    
- Попередні Affix Locks та Refinement не переносяться.
    
- Стихійне зачарування не переноситься.
    
- Element Crystals не відшкодовуються.
    

### 10.3. Rank Distribution

Результат отримує Rank між мінімальним і максимальним Rank трьох вхідних предметів включно.

Якщо всі три Rank однакові, результат гарантовано зберігає цей Rank.

Приклади:

`R5 + R5 + R5 → R5 (100%)`

`R2 + R3 + R7 → випадковий R2–R7`

Balance v1 для R2/R3/R7:

|Rank|Шанс|
|---|---|
|R2|10%|
|R3|19%|
|R4|37%|
|R5|19%|
|R6|10%|
|R7|5%|

Розподіл має бути нормалізований до 100%.

Робоча формула ваг:

`weight(r) = exp(−abs(r −mean(input_ranks)) / temperature)`

У прикладі використовується `temperature = 1.5`.

Не змінювати канонічний дозволений діапазон Rank, коригуючи балансні ваги.

### 10.4. Named Items

Named Boss Unique не проходять через звичайний Synthesis.

Для них використовується окремий Blueprint Ritual.

## 11. Enchantment I–V

Стихійне зачарування дозволяє створювати елементальні білди.

Сім стихій:

Fire, Water, Nature, Light, Dark, Lightning, Wind.

### 11.1. Пороги каналів

- 4/5 Armor однієї стихії → Primary Element Channel.
    
- 3/4 Accessories однієї стихії → Secondary Element Channel.
    
- Стихійна зброя не створює третій канал.
    

### 11.2. Рецепти Enchant — Balance v1

**Enchant I**

Доступ: Forge I.

Витрати:

- 1 Element Crystal.
    
- 5 Uncommon Metal.
    
- 500 Gold.
    

Результат: елементальна властивість предмета.

**Enchant II**

Доступ: Forge II.

Витрати:

- 2 Element Crystals.
    
- 8 Rare Metal.
    
- 3 Rare Regional Trophies.
    
- 3 000 Gold.
    

Бонус: +4% Elemental Power предмета.

**Enchant III**

Доступ: Forge II.

Витрати:

- 3 Element Crystals.
    
- 12 Epic Metal.
    
- 5 Epic Regional Trophies.
    
- 15 000 Gold.
    

Бонус: +8% Elemental Power предмета.

**Enchant IV**

Доступ: Forge III.

Витрати:

- 5 Element Crystals.
    
- 16 Legendary Metal.
    
- 1 Commander Core.
    
- 60 000 Gold.
    

Бонус: +12% Elemental Power предмета.

**Enchant V**

Доступ: Forge III.

Витрати:

- 8 Element Crystals.
    
- 2 Mythic Metal.
    
- 1 General Heart.
    
- 250 000 Gold.
    

Бонус: +16% Elemental Power предмета.

Наведені бонуси — Balance v1. Канали й правила активації залишаються незмінними.

Вартість підвищення до кожного Tier оплачується за відповідним рецептом.

### 11.3. Зняття стихії

Доступ: Forge III.

Витрати:

- 2 Crystals (валюта).
    
- 1 Epic Forge Dust.
    

Результат:

- Предмет стає Neutral.
    
- Попередні Element Crystals не повертаються.
    

### 11.4. Заміна стихії

Доступ: Forge III.

Операція:

1. Оплатити зняття старої стихії.
    
2. Оплатити Enchant I нової стихії.
    
3. За потреби підвищити новий Enchant Tier.
    

Попередній Enchant Tier не переноситься безкоштовно.

## 12. Affix Reroll

Доступ: Forge II.

Reroll дозволяє повторно згенерувати звичайні Affixes.

### 12.1. Канон

- Можна заблокувати 0–3 Affixes.
    
- Принаймні один звичайний Affix залишається відкритим.
    
- Заблоковані Affixes не змінюються.
    
- Гарантовані Main Stats не змінюються.
    
- Нові Affixes генеруються з дозволеного Affix Pool.
    
- Mythic Trait та фіксовані Named Effects захищені.
    

### 12.2. Вартість — Balance v1

Приклад для Rare Item:

|Locked|Rare Dust|Crystals|Gold|
|---|---|---|---|
|0|4|1|200|
|1|8|2|400|
|2|16|4|800|
|3|32|8|1 600|

Кожен додатковий Lock подвоює відповідний множник вартості:

×1 / ×2 / ×4 / ×8.

Знижки Gold не зменшують кількість Dust або Crystals.

## 13. Refinement

Доступ: Forge II.

Refinement покращує якість існуючого roll без заміни характеристики.

### 13.1. Правила

- Не змінює тип Main Stat.
    
- Не змінює Affix ID.
    
- Підвищує roll_fraction.
    
- Не погіршує попередній roll.
    
- Не перевищує maximum roll.
    
- Не змінює Mythic Trait або Named Unique Effect.
    

### 13.2. Вартість — Balance v1

|Поточний Roll|Покращення|Матеріали|
|---|---|---|
|0–49%|+10 п.п.|2 Dust Q + 1 Crystal|
|50–79%|+6 п.п.|4 Dust Q + 3 Crystals|
|80–94%|+3 п.п.|8 Dust Q + 6 Crystals + 1 Epic Trophy|
|95–99%|+1 п.п.|16 Dust Q + 10 Crystals + 1 Legendary Component|
|100%|MAX|Refinement недоступний|

Refinement та Reroll повинні мати окремі кнопки, ціни та журнали транзакцій.

## 14. Named Blueprint Ritual

Іменні предмети можуть випадати зі Стражів, Генералів та окремих спеціальних ворогів.

### 14.1. Відкриття креслення

Гравець збирає три однакові Named Items з одним `named_unique_id`.

Предмети можуть мати різні Rank, Upgrade та Affixes.

Ритуал:

1. Перевіряє однаковий unique ID.
    
2. Перевіряє всі три предмети.
    
3. Після підтвердження незворотно витрачає їх.
    
4. Назавжди відкриває відповідний Enhanced Named Blueprint.
    

Це не звичайне підвищення Rarity.

### 14.2. Enhanced Named Craft

Коли креслення відкрите, гравець може створювати покращений іменний предмет за матеріали.

Повторно збирати три Named Items не потрібно.

### 14.3. Основні рецепти — Balance v1

**Prison Guardian Named**

- 12 Epic Metal.
    
- 24 Epic Ore.
    
- 8 Epic Regional Trophies.
    
- 2 відповідні Guardian Cores.
    
- 150 000 Gold.
    

Бонус до базових Main Stats: +10%.

**Celestial Commander Named**

- 16 Legendary Metal.
    
- 30 Epic Ore.
    
- 10 Legendary Trophies.
    
- 2 відповідні Commander Cores.
    
- 800 000 Gold.
    

Бонус до базових Main Stats: +15%.

**General Named**

- 3 Mythic Metal.
    
- 8 Mythic Ore.
    
- 12 Legendary Trophies.
    
- 2 відповідні General Hearts.
    
- 5 000 000 Gold.
    

Бонус до базових Main Stats: +20%.

Ці витрати — робочі рецепти Balance v1.

### 14.4. Обмеження

- Enhanced Named отримує відповідний слот.
    
- Rank генерується або вибирається за доступним Forge Mode.
    
- Affixes та Main Stat Rolls генеруються за правилами предмета.
    
- Named не означає автоматично Mythic.
    
- Лише Mythic має обов'язковий Mythic Trait.
    
- Креслення зберігається після Rebirth.
    

## 15. Регіональні креслення

Існує рівно 12 спеціальних регіональних креслень.

Кожне відповідає одному з 12 слотів ГГ.

### 15.1. Умови відкриття

- У регіонах R1–R5 по два креслення.
    
- У регіонах R6–R7 по одному кресленню.
    
- Потрібно вперше очистити всі три Башти Ув'язнення відповідного регіону.
    
- Креслення відкриваються назавжди.
    
- Rebirth не скидає відкриті креслення.
    
- Повторна Тріада не створює дублікати.
    

Регіональне креслення не вимагає трьох Named Items.

### 15.2. Каталог 12 креслень

|Регіон|Recipe ID|Назва|
|---|---|---|
|R1|REG_R1_GLOVES|Рукавиці Тваневого Ткача|
|R1|REG_R1_BELT|Пояс Морового Вартового|
|R2|REG_R2_SWORD|Креслення Клинка Недр|
|R2|REG_R2_CHEST|Кіраса Жерлового Короля|
|R3|REG_R3_SHIELD|Щит Холодної Течії|
|R3|REG_R3_BOOTS|Чоботи Затонулого Штурмана|
|R4|REG_R4_CLOAK|Плащ Нестерпного Вітру|
|R4|REG_R4_EARRINGS|Сережки Грозових Дзвонів|
|R5|REG_R5_HELMET|Шолом Нічного Сторожа|
|R5|REG_R5_RING|Перстень Забутого Імені|
|R6|REG_R6_PANTS|Поножі Присяги Коріння|
|R7|REG_R7_AMULET|Амулет Семи Клятв|

### 15.3. Додаткові матеріальні вимоги — Balance v1

Це доплата до базового рецепта відповідного слота.

**Регіони R1–R2**

- 8 Epic Regional Trophies.
    
- 6 Epic Metal.
    
- 1 визначений Guardian Core.
    
- 80 000 Gold.
    

**Регіони R3–R4**

- 10 Epic Regional Trophies.
    
- 8 Epic Metal.
    
- 1 визначений Guardian Core.
    
- 125 000 Gold.
    

**Регіони R5–R6**

- 12 Epic Regional Trophies.
    
- 10 Epic Metal.
    
- 1 визначений Guardian Core.
    
- 175 000 Gold.
    

**Регіон R7**

- 12 Legendary Regional Trophies.
    
- 12 Legendary Metal.
    
- 1 визначений Guardian Core.
    
- 300 000 Gold.
    

Рекомендована мінімальна якість результату — Epic (Balance v1).

Конкретні Trophy IDs та Guardian Core IDs визначені реєстром Forge Bible §11.4.

Ця доплата застосовується один раз за створення предмета і не дублюється під час Rank Up, Upgrade або Reroll.

Не вигадувати додатковий унікальний бонус регіонального предмета без окремої специфікації.

## 16. Спеціальні матеріали Стражів

Кожен із 21 Стража має власний спеціальний матеріал.

### 16.1. Перше проходження

Перша сюжетна перемога над конкретним Стражем 141:

- Гарантовано 1 відповідний матеріал.
    
- Один раз на конкретного Стража на збереження.
    

### 16.2. Повторні перемоги

- 40% на рівно 1 відповідний матеріал.
    
- 60% без цього матеріалу.
    
- Незалежний roll.
    
- Звичайні нагороди не замінюються.
    
- Регіональні креслення повторно не видаються.
    

### 16.3. Дані

Зберігати окремо:

- guardian_id.
    
- source_id.
    
- material_id.
    
- claimed_first_clear.
    

Guardian Core не можна заміняти General Heart.

## 17. Сім General Hearts

Список технічних ID:

|material_id|Назва|
|---|---|
|GENERAL_HEART_PLAGUE|Серце Пошесті|
|GENERAL_HEART_VOLCANO|Серце Вулкану|
|GENERAL_HEART_ABYSS|Серце Безодні|
|GENERAL_HEART_STORM|Серце Бурі|
|GENERAL_HEART_SHADOWS|Серце Тіней|
|GENERAL_HEART_CORRUPTION|Серце Скверни|
|GENERAL_HEART_PRINCE|Первісне Серце Князя|

### 17.1. Перша сюжетна перемога

- Рівно 1 відповідний General Heart гарантовано.
    
- Без паралельного Heart RNG.
    

### 17.2. Повторний Echo

- 30% шанс отримати рівно 1 Heart.
    
- 70% шанс отримати 0.
    

### 17.3. Обмеження

- Named Drop Pity не впливає на Hearts.
    
- Звичайні вороги не видають Hearts.
    
- Стражі не видають Hearts.
    
- Експедиції не видають Hearts.
    
- Перша сюжетна перемога не повинна дублювати Heart через Echo.
    

Матеріал Стража 06-III «Серце скверни» і `GENERAL_HEART_CORRUPTION` — різні ресурси з різними ID.

## 18. Sell, Salvage та Auto-Salvage

### Sell

Продаж спорядження за Gold.

Ціна залежить від:

- Rarity.
    
- Rank.
    
- Upgrade Level.
    

Масові продажі не повинні включати Favorite та Equipped предмети.

### Salvage

Розбирання:

- Гарантовано видає Forge Dust відповідної Rarity.
    
- Додатково може повертати приблизно 30–50% звичайних матеріалів, вкладених в Upgrade (Balance v1).
    

Автоматично не повертаються:

- Boss Cores.
    
- Mythic Ore/Metal.
    
- Element Crystals.
    

### Auto-Salvage

Фільтри:

- Rarity.
    
- Rank.
    
- Favorite.
    
- Equipped.
    

Named та Mythic за замовчуванням захищені.

Гравцю доступний журнал останніх 20 операцій Auto-Salvage.

## 19. Переплавлення матеріалів

Дозволені конверсії:

|Вхід|Результат|
|---|---|
|5 Common Ore/Metal|1 Uncommon відповідного виду|
|5 Uncommon|1 Rare|
|5 Rare|1 Epic|
|5 Epic + 1 Boss Trophy|1 Legendary|

Просунута переплавка до Legendary доступна у Forge II.

### Заборона Mythic Conversion

Mythic Ore та Mythic Metal не створюються шляхом переплавлення нижчих якостей.

Заборонено:

`5 Legendary → 1 Mythic`

Mythic матеріали потрібно отримувати через відповідний ігровий контент.

## 20. Scroll Synthesis

Кузня не створює нові сувої зі звичайних матеріалів.

Дозволено лише:

`3 однакові Scroll → 1 Scroll наступної Rarity`

Умови:

- Однаковий type_id.
    
- Однакова Rarity.
    
- Той самий ефект.
    
- Mythic не має вищого рівня.
    

Приклад:

`3 Rare Scroll of Fury → 1 Epic Scroll of Fury`

Заборонено змінювати сімейство сувою під час синтезу.

Сувої зберігаються після Rebirth.

## 21. Репутація та Gold-знижки

### 21.1. Reputation 9

При досягненні Rank 9:

- −15% Gold-вартості Reroll.
    
- −15% Gold-вартості Refinement.
    

Не зменшує кількості матеріалів.

### 21.2. Reputation 10

При досягненні Rank 10:

- −10% Gold-вартості відповідного high-tier Craft.
    

Рецепт повинен мати відповідну позначку:

`eligible_high_tier_crafting = true`

UI не повинен самостійно визначати, який рецепт високорівневий.

### 21.3. Forge IV

- −10% Gold для Craft.
    
- −10% Gold для Reroll.
    
- Не дає власної знижки на Refinement.
    

### 21.4. Комбінування

Знижки застосовуються до Gold_base мультиплікативно, а не додаванням процентних пунктів.

**Forge IV + Reputation 9 для Reroll:**

`FinalGold = GoldBase × 0.90 × 0.85`

**Forge IV + Reputation 10 для eligible Craft:**

`FinalGold = GoldBase × 0.90 × 0.90`

**Refinement з Reputation 9:**

`FinalGold = GoldBase × 0.85`

Forge IV не додає ще 10% знижки до Refinement.

Знижки не впливають на:

- Crystals.
    
- Souls.
    
- Forge Dust.
    
- Element Crystals.
    
- Boss Cores.
    
- Guardian Materials.
    
- General Hearts.
    

## 22. Головні вкладки Кузні

### Craft

- Вибір типу предмета.
    
- Rarity.
    
- Доступний Rank Range.
    
- Каталізатори.
    
- Вартість.
    
- Create ×1 / ×10 / Max.
    

### Rank Up

- Поточний Rank.
    
- Наступний Rank.
    
- Зміна характеристик.
    
- Необхідні матеріали.
    
- Підтвердження операції.
    

### Upgrade

- Поточний +Level.
    
- Майбутній +Level.
    
- Вартість.
    
- Upgrade Once / Max.
    

### Enchantment

- Сім стихій.
    
- Enchant Tiers I–V.
    
- Зняття або заміна стихії.
    

### Synthesis

- Звичайні предмети 3→1.
    
- Сувої 3→1.
    
- Окремий Named Blueprint Ritual.
    

### Reroll / Refinement

- Affix Locks.
    
- Попередній та майбутній результат.
    
- Окремі витрати.
    

### Blueprints

- Відкриті креслення.
    
- Невідкриті креслення.
    
- Regional Blueprint.
    
- Enhanced Named Blueprint.
    

### Salvage

- Ручний розбір.
    
- Auto-Salvage.
    
- Фільтри й журнал.
    

## 23. Дані для реалізації в Godot

### ForgeProgress

- forge_level
    
- defeated_general_ids
    
- opened_towers
    
- known_recipe_ids
    
- unlocked_blueprint_ids
    

### RecipeData

- recipe_id
    
- operation_kind
    
- input_slot
    
- input_weapon_type
    
- output_item_template
    
- target_rarity
    
- allowed_rank_range
    
- ingredients[]
    
- forge_level_required
    
- eligible_high_tier_crafting
    

### IngredientData

- resource_id
    
- min_quality
    
- quantity
    
- consumes_on_success
    
- source_table_key
    

### ItemInstance

- instance_id
    
- template_id
    
- rarity
    
- rank
    
- upgrade_level
    
- element_id
    
- enchant_tier
    
- affixes[]
    
- roll_fraction[]
    
- named_unique_id
    
- rebirth_seal_state
    
- protected
    

### NamedBlueprint

- unique_id
    
- associated_boss_id
    
- source_drop_item_id
    
- recipe_id
    
- learned_permanently
    
- enhanced_stat_coefficient
    

### RegionalBlueprint

- recipe_id
    
- region_id
    
- blueprint_kind
    
- triad_first_clear_flag
    
- output_item_template
    
- output_slot
    
- output_weapon_type
    
- persistent_unlock
    
- ingredients[]
    
- repeatable_craft
    

### SynthesisRule

- category
    
- require_equal_subtype
    
- require_equal_rarity
    
- rank_distribution
    
- output_template
    

## 24. Атомарність операцій

Кузня не повинна дублювати предмети або списувати ресурси без створення результату.

Рекомендований порядок:

1. Validate Operation.
    
2. Validate Forge Level.
    
3. Validate Recipe Unlock.
    
4. Validate Materials.
    
5. Calculate Price Quote.
    
6. Preview Result.
    
7. Confirm Operation.
    
8. Consume Inputs.
    
9. Generate/Update Output.
    
10. Save State.
    
11. Write Transaction Log.
    
12. Refresh UI.
    

Операція має бути атомарною: повторний клік не повинен створювати дублікати.

При Rank Up необхідно зберігати Upgrade, Affixes, Roll Fractions та Enchant.

## 25. Обмеження та заборони

Без погодження розробника заборонено:

- Додавати п'ятий рівень Кузні.
    
- Змінювати умови відкриття Forge I–IV.
    
- Дозволяти вибір точного Rank до Forge III.
    
- Перевищувати Rank 12.
    
- Перевищувати Upgrade +30.
    
- Робити Rank Up або Upgrade з випадковою невдачею.
    
- Створювати Mythic Ore/Metal із нижчих якостей.
    
- Крафтити нові сувої зі звичайної сировини.
    
- Давати Enchant V без необхідних ресурсів.
    
- Ігнорувати умови Elemental Channels.
    
- Дозволяти понад три Affix Locks.
    
- Погіршувати результат Refinement.
    
- Змінювати Main Stats звичайним Reroll.
    
- Змішувати Named Items зі звичайним Synthesis.
    
- Відкривати регіональні креслення без очищення відповідної Тріади.
    
- Повторно видавати одноразові Blueprint Unlocks.
    
- Зменшувати матеріальні витрати через Gold-знижки.
    
- Плутати Guardian Materials та General Hearts.
    
- Самостійно додавати нові рецепти або бонуси, які суперечать затвердженій специфікації.
    

## 26. Критерії перевірки

### Forge Unlock

- Forge I відкривається на поверсі 80.
    
- Enchant I не видає безкоштовних кристалів.
    
- Forge II доступний після потрібного прогресу першої Небесної Вежі.
    
- Forge III потребує двох різних Генералів.
    
- Forge IV потребує п'яти різних Генералів.
    

### Craft / Rank / Upgrade

- Random Rank має нормалізовані шанси.
    
- Каталізатори не обходять контентні гейти.
    
- Controlled Rank працює після Forge III.
    
- Rank Up має 100% успіх.
    
- Upgrade має 100% успіх.
    
- Rank Up зберігає характеристики та +Level.
    
- Upgrade не перевищує +30.
    
- Витрати не застосовуються двічі.
    

### Synthesis / Enchant

- Synthesis перевіряє exact subtype.
    
- Результат отримує Rank у допустимому діапазоні.
    
- Однакові Rank дають гарантовано однаковий Rank.
    
- Upgrade результату дорівнює +0.
    
- Старе зачарування не переноситься.
    
- Enchant I–V використовує правильні рецепти.
    
- Заміна стихії не зберігає безкоштовно попередній Tier.
    

### Reroll / Refine

- Максимум три Locks.
    
- Принаймні один звичайний Affix відкритий.
    
- Reroll не змінює Main Stats.
    
- Refinement не погіршує roll.
    
- Mythic Trait не змінюється.
    

### Blueprints / Boss Materials

- Три однакові Named відкривають одне постійне креслення.
    
- Регіональні креслення відкриваються окремо від Named Ritual.
    
- Усього 12 регіональних креслень.
    
- Відкриття креслень зберігаються після Rebirth.
    
- Перший Guardian Clear дає гарантований матеріал.
    
- Повторний Guardian Clear має 40% на матеріал.
    
- Перший General Clear дає гарантований Heart.
    
- General Echo має 30% на Heart.
    
- Guardian і General матеріали мають різні ID.
    

### Economy / Save

- Gold-знижки застосовуються мультиплікативно.
    
- Forge IV не знижує Refinement.
    
- Матеріали не дисконтуються.
    
- Операції атомарні.
    
- Подвійний клік не дублює предмети.
    
- Save/Load відновлює Forge Progress та Blueprints.
    

Усі критерії залишаються невиконаними до тестування в Godot.

## 27. Відкриті питання Balance v1

Потребують симуляцій і плейтестів:

- Rarity Cost Multipliers.
    
- Category Cost Multipliers.
    
- Rank 1–12 Material Costs.
    
- Upgrade Gold Curve.
    
- Каталізаторні шанси Rank.
    
- Enchant II–V Elemental Power Bonuses.
    
- Reroll / Refinement Economy.
    
- Enhanced Named Stat Bonuses.
    
- Регіональні матеріальні доплати.
    
- Темп отримання Mythic Ore/Metal.
    
- Частота повторних перемог над Стражами та Генералами, необхідна для іменного крафту.
    

Затверджені шанси спеціальних матеріалів Стражів 40% і General Hearts 30% не змінювати самовільно.

## 28. Пов'язані документи

- [Головні правила](../02_Core_Rules.md)
    
- [Огляд гри](../01_Game_Overview.md)
    
- [Бойова система](Combat.md)
    
- [Стихії](Elements.md)
    
- [Резонанси](Resonances.md)
    
- [Екіпірування](Equipment.md)
    
- [Економіка](Economy.md)
    
- [Прогресія](Progression.md)
    
- [Вороги та матеріали](../World/Enemies.md)
    
- [Вежі та відкриття контенту](../World/Towers.md)
    

### Основні джерела істини

- Crafting & Forge Bible v1.2 — рецепти, Кузня, операції.
    
- Equipment Bible v1.2 — характеристики предметів, Affix Pools.
    
- Enemies & Loot Bible v1.2 — джерела матеріалів, Boss Drop і Named Loot.
    
- World & Towers Bible v1.2 — відкриття Тріад, регіонів та веж.
    
- Economy & Balance Bible v1.2 — економіка та симуляції.
    
- Combat Bible v1.2 — дія стихій, резонансів та бойових ефектів.
    

Повний реєстр 21 Стража, 42 командирів і 7 Генералів із конкретними іменними предметами та матеріалами залишається в Crafting Bible §11 і Enemies Bible до перенесення його в тематичні документи Obsidian.

Не генерувати пропущені дані реєстру самостійно.

---

**Статус документа:** підготовлений на основі Crafting & Forge Recipe Bible v1.2.

**Статус реалізації:** не реалізовано.

**Статус числового балансу:** Balance v1, потребує перевірки.

**Головне правило:** реалізація Кузні повинна відповідати затвердженим рецептам і прогресії, не дозволяючи обходити сюжетні та матеріальні обмеження.