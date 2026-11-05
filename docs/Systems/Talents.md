---

status: draft  
document_type: talent-system  
source: Talent Tree & Progression Design Bible v1.1  
balance_status: Balance v1  
updated: 2026-11-04
tags:

- game-system
    
- talents
    
- soul-skills
    
- relics
    
- progression
    
- godot
    

revision: approved-changes-2026-11-04
---

# TALENT TREE & SOUL PROGRESSION — Таланти та Душі

> Редакція 2026-11-04: затверджені зміни за [Decisions](../Development/Decisions.md) мають пріоритет над суперечними правилами попередніх Word Bible. Оновлено документацію; реалізацію та ігровий баланс не перевірено.

> Повна специфікація 120 вузлів дерева талантів, активних талантів, стихійних секторів, Resonance Bridges, Global Keystone, Skill Mutations, Soul Skills, Soul Relics і пресетів.
> 
> Основне джерело: Talent Tree & Progression Design Bible v1.1.
> 
> Загальна прогресія узгоджується з GDD v2.3 та Economy & Balance Bible v1.2.
> 
> Структура чинного базового каталогу та правила Rebirth збережені; фінальна кількість вузлів OPEN за протоколом експериментів (§34). Числові ефекти, ціни, prerequisites і таймінги, позначені в Talent Bible як робочі, — Balance v1.

## 1. Призначення системи

Talent Tree дозволяє створювати спеціалізовані бойові білди.

Головні завдання:

- Розвиток Manual/Hold Attack.
    
- Розвиток Auto Attack, Героїв і вихованців.
    
- Посилення активних навичок.
    
- Розвиток подвійних і потрійних резонансів.
    
- Спеціалізація за сімома стихіями.
    
- Вибір сильних Keystone із компромісами.
    
- Збереження різних білдів через пресети.
    
- Постійна Soul-прогресія між Rebirth.
    

Talent Tree є run-based системою.

Soul Skills та Soul Relics є permanent meta-progression.

Ці дві системи не можна змішувати.

## 2. Канонічна структура дерева

Поточний базовий каталог Talent Tree містить 120 унікальних вузлів. Остаточний розмір релізного дерева обирається після експериментів (§34).

|Група|Кількість|
|---|---|
|Central Ring|14|
|Manual / Combo|13|
|Auto / Hero / Pets|13|
|Skills / Resonance|13|
|Сім стихійних секторів|42|
|Resonance Bridges|21|
|Global Keystone|4|
|**Разом**|**120**|

Структура радіальна.

Усі вузли показуються в інтерфейсі одразу, але невідкриті або недоступні вузли затемнені.

Гравець може переглянути назву, ефект, ціну та prerequisites навіть для заблокованого вузла.

## 3. Категорії вузлів

### Minor

- Багаторівневий вузол.
    
- 1 TP за кожен рівень.
    
- Максимальний рівень залежить від конкретного Node ID.
    

### Notable

- Одноразовий вузол.
    
- Max Rank = 1.
    
- Вартість = 3 TP.
    

### Active Talent

- Одноразове відкриття активної навички.
    
- Max Rank = 1.
    
- Вартість = 3 TP.
    
- Навичка використовує один із чотирьох бойових слотів ГГ.
    

### Elemental Keystone

- Max Rank = 1.
    
- Вартість = 6 TP.
    
- Максимум два активні Elemental Keystone в одному білді.
    

### Resonance Bridge

- Max Rank = 1.
    
- Вартість = 3 TP.
    
- Модифікує одну затверджену пару стихій.
    

### Global Keystone

- Max Rank = 1.
    
- Вартість = 10 TP.
    
- Максимум один активний Global Keystone.
    

## 4. Правила prerequisites

Усі залежності визначаються через конкретні Node ID та мінімальні рівні.

Приклад:

`M08: M07 >= 1 AND C06 >= 1`

Це означає:

- M07 придбано.
    
- C06 має щонайменше один рівень.
    

Обидві умови обов'язкові.

### AND

Усі перелічені умови повинні виконуватися.

### OR

Достатньо виконати одну дозволену альтернативу, якщо вона явно присутня у визначенні вузла.

### Заборонені неоднозначні залежності

Не використовувати:

`A + B >= N`

Якщо незрозуміло, чи йдеться про суму рівнів двох вузлів, або про дві окремі вимоги.

Усі prerequisites потрібно валідовувати до списання TP.

## 5. Central Ring — 14 вузлів

Усі вузли групи C є Minor.

Вартість: 1 TP за рівень.

|ID|Назва|Max|Ефект Balance v1|Prerequisite|
|---|---|---|---|---|
|C01|Початкова Іскра|5|ATK +2%/рів.|Старт|
|C02|Живучість|5|Max HP +3%/рів.|C01 ≥1|
|C03|Точність Удару|5|Crit Rate +0.6 п.п./рів.|C01 ≥2|
|C04|Ритм Атаки|5|Attack Speed +2%/рів.|C03 ≥1|
|C05|Провідник Стихій|5|Elemental Damage +2%/рів.|C01 ≥3|
|C06|Бойова Пам'ять|4|Combo Gain +3%/рів.|C03 ≥2|
|C07|Автоматичне Ядро|5|Auto Damage +3%/рів.|C04 ≥1|
|C08|Союзницька Ланка|5|Hero Damage +3%/рів.|C07 ≥1|
|C09|Наснага Навичок|4|Skill Damage +3%/рів.|C05 ≥1|
|C10|Щит Тіла|5|Physical Mitigation +1 п.п./рів.|C02 ≥2|
|C11|Непохитна Воля|3|Stun Duration −5%/рів.|C10 ≥1|
|C12|Точний Крит|4|Crit DMG +5%/рів.|C03 ≥3|
|C13|Резонансний Слід|4|Resonance Damage +3%/рів.|C09 ≥1|
|C14|Друге Дихання|3|Після перемоги Heal 1.5% Max HP/рів.|C10 ≥2|

### Обмеження Central Ring

- Physical Mitigation використовує загальні бойові cap.
    
- Stun Reduction не створює повний імунітет до контролю.
    
- Heal After Kill не повинен дозволяти нескінченну регенерацію через експлойти.
    
- Кожен рівень вузла оплачується окремо.
    

## 6. Manual / Combo — 13 вузлів

Спеціалізація ручного бою, утримання ЛКМ та Combo.

Позначення вартості:

- Minor: 1 TP/рів.
    
- Notable або Active: 3 TP одноразово.
    

|ID|Назва|Тип / Max|Ефект Balance v1|Prerequisite|
|---|---|---|---|---|
|M01|Перший Замах|Minor 5|Manual/Hold Damage +3%/рів.|C03 ≥1|
|M02|Лічильник Ударів|Minor 5|Combo Gain +4%/рів.|M01 ≥2|
|M03|Шлях Мисливця|Minor 5|Damage проти Normal +3%/рів.|M01 ≥2|
|M04|Різкий Розмах|Minor 4|Manual Crit DMG +5%/рів.|M02 ≥2|
|M05|Стале Утримання|Minor 5|Hold Cadence +2%/рів.|M02 ≥2|
|M06|Точність Поранення|Minor 4|Manual Crit Rate +0.75 п.п./рів.|M04 ≥2|
|M07|Шквал Серій|Notable 1|Кожен 8-й Manual/Hold Hit отримує +35% Damage|M05 ≥2|
|M08|Кривавий Такт|Active 1|350% ATK × (1 + 0.01 × Combo), CD 16 с|M07 ≥1 AND C06 ≥1|
|M09|Тиск На Броню|Minor 4|Manual ігнорує +1% позитивного Physical RES/рів.|M06 ≥2|
|M10|Глибокий Комбо|Minor 5|Combo Cap +4%/рів.|M07 придбано|
|M11|Безперервний Ритм|Notable 1|Hold не скидає Combo при відпусканні ≤0.6 с|M10 ≥2|
|M12|Критичний Розгін|Minor 5|Після Manual Crit +1% Combo Power/рів. на 3 с, без стеків|M09 ≥2|
|M13|Ідеальний Ритм|Notable 1|Кожен 10-й Manual Hit: +100% Crit DMG|M11 ≥1 AND M12 ≥2|

### M08 — Кривавий Такт

Активна навичка Manual-гілки.

- Cooldown: 16 с.
    
- Damage: 350% ATK × (1 + 0.01 × Combo).
    
- Виконується без переміщення ГГ.
    
- Займає один із чотирьох слотів активних навичок.
    

Механіка має враховувати обмеження Combo Contribution із Talent Bible.

### Спеціальний інваріант v1.1

M07 та M11:

- Max Rank = 1.
    
- Cost = 3 TP.
    
- Друга покупка заборонена.
    

## 7. Auto / Hero / Pets — 13 вузлів

Спеціалізація автоматичного бою, союзного Героя, вихованців та допоміжної економіки.

|ID|Назва|Тип / Max|Ефект Balance v1|Prerequisite|
|---|---|---|---|---|
|A01|Механічний Пульс|Minor 5|Auto Damage +3%/рів.|C07 ≥1|
|A02|Сила Союзника|Minor 5|Hero Damage +3%/рів.|A01 ≥2|
|A03|Зв'язок Вихованців|Minor 5|Pet Combat Bonus +2%/рів.|A01 ≥2|
|A04|Швидка Команда|Minor 4|Hero Attack Speed +2%/рів.|A02 ≥2|
|A05|Ефективна Ферма|Minor 5|Gold From Kills +2%/рів.|A03 ≥1|
|A06|Спільний Фронт|Minor 4|Auto + Hero Damage по одній цілі +2%/рів.|A02 ≥2|
|A07|М'яка Турбота|Minor 4|Pet Support/Economy +2%/рів.|A03 ≥2|
|A08|Бойовий Наказ|Active 1|Auto + Hero AS +15% на 7 с, CD 24 с|A04 ≥2 AND A06 ≥1|
|A09|Стабільна Варта|Minor 4|Hero Stun Duration −4%/рів.|A06 ≥2|
|A10|Точкова Синергія|Minor 5|Pet Pair Bonus +3%/рів.|A07 ≥2|
|A11|Формація Оборони|Notable 1|Hero Support/Pet Shield Strength +12%|A09 ≥2|
|A12|Дальній Наказ|Minor 5|Auto + Hero Boss Damage +2%/рів.|A08 ≥1 AND A10 ≥2|
|A13|Командна Мережа|Notable 1|Auto/Hero Damage +25%, Manual Direct −15%|A11 ≥1 AND A12 ≥2|

### A08 — Бойовий Наказ

Активна навичка Auto-гілки.

- Cooldown: 24 с.
    
- Тривалість: 7 с.
    
- Auto Attack Speed +15%.
    
- Hero Attack Speed +15%.
    
- Не підсилює Attack Speed вихованців автоматично.
    
- Займає один зі слотів ГГ.
    

### A13 — Командна Мережа

Це спеціалізація Auto/Hero Build.

Збільшення Auto/Hero Damage компенсується зменшенням Manual Direct Damage.

Не блокувати ручну взаємодію повністю.

### Спеціальний інваріант v1.1

A11:

- Max Rank = 1.
    
- Cost = 3 TP.
    
- Повторна покупка заборонена.
    

## 8. Skills / Resonance — 13 вузлів

Спеціалізація активних навичок, резонансів, стихійної шкоди та RES.

|ID|Назва|Тип / Max|Ефект Balance v1|Prerequisite|
|---|---|---|---|---|
|S01|Шлях Заклять|Minor 5|Skill Damage +3%/рів.|C09 ≥1|
|S02|Точність Резонансу|Minor 5|Resonance Damage +3%/рів.|S01 ≥2|
|S03|Потік Часу|Minor 5|Cooldown Recovery +2%/рів.|S01 ≥2|
|S04|Подвійний Контур|Minor 4|Core Resonance Damage +3%/рів.|S02 ≥2|
|S05|Третій Голос|Minor 4|Triple Effects +2% від бази/рів.|S02 ≥2|
|S06|Ерозія Опору|Minor 5|RES Shred Duration +2%/рів.|S03 ≥2|
|S07|Магічний Бар'єр|Minor 4|Сім Elemental RES +0.75 п.п./рів.|S03 ≥1|
|S08|Стихійний Сплеск|Active 1|Наступний Core/Hero Proc +25% Resonance Power, CD 22 с|S04 ≥1 AND S05 ≥1|
|S09|Зворотний Потік|Minor 4|Elemental Skill Cooldown −0.5%/рів.|S06 ≥2|
|S10|Фокус Реакції|Notable 1|Reaction Focus Switch зберігає попередній DoT; lockout 2 с|S08 придбано|
|S11|Проникна Формула|Minor 4|Elemental Penetration +1%/рів.|S07 ≥2|
|S12|Печать Майстерності|Minor 5|Boss Resonance Damage +2%/рів.|S09 ≥2|
|S13|Мудрець Резонансу|Notable 1|Double +20%, Triple Effects +35%, Physical Direct −15%|S10 ≥1 AND S12 ≥2|

### S08 — Стихійний Сплеск

- Cooldown: 22 с.
    
- Протягом 6 с наступний доступний Core або Hero Resonance Proc отримує +25% Resonance Power.
    
- Після спрацювання бонус витрачається.
    
- Займає один слот ГГ.
    

### S10 — Фокус Реакції

- Не скидає попередній DoT під час Reaction Focus Switch.
    
- Lockout зміни: 2 с.
    
- Max Rank = 1.
    
- Cost = 3 TP.
    

### S13 — Мудрець Резонансу

- Double Resonance: +20%.
    
- Triple Resonance Effects: +35%.
    
- Physical Direct: −15%.
    

Це specialization tradeoff, а не безкоштовне підсилення всіх видів шкоди.

## 9. Три активні талант-навички

Існують рівно три Active Talent Nodes:

|Node|Навичка|Cooldown|Основна роль|
|---|---|---|---|
|M08|Кривавий Такт|16 с|Manual / Combo Burst|
|A08|Бойовий Наказ|24 с|Auto/Hero Tempo|
|S08|Стихійний Сплеск|22 с|Resonance Burst|

### Канонічні правила

- ГГ має чотири загальні активні слоти.
    
- Три активні таланти не додають трьох додаткових кнопок.
    
- Відкриття вузла дозволяє екіпірувати відповідну навичку.
    
- Активна навичка має бути призначена до одного з чотирьох слотів.
    
- Усі активні навички використовують свої звичайні cooldown.
    
- Auto-поведінка навичок може використовувати окрему Automation Policy.
    
- Навички не виконуються поза дозволеним бойовим станом.
    

Automation Policy може враховувати:

- Boss State.
    
- HP Condition.
    
- Resonance Condition.
    

Конкретна поведінка повинна відповідати бойовим правилам.

- Активні талант-навички з прямим ударом (зокрема `M08 — Кривавий Такт`) та відповідні бойові навички можуть мати властивість переривання касту боса (`can_interrupt = true`) згідно з налаштуваннями Combat Config.

## 10. Сім стихійних секторів — 42 вузли

Кожен сектор містить:

- 3 Minor.
    
- 2 Notable.
    
- 1 Elemental Keystone.
    

Разом: 6 вузлів на стихію.

Сім секторів × 6 = 42.

### 10.1. Вогонь — F01–F06

|ID|Назва|Тип / Max|Ефект Balance v1|Prerequisite|
|---|---|---|---|---|
|F01|Тепло Ядра|Minor 5|Fire Damage +3%/рів.|C05 ≥1|
|F02|Жар Попелу|Minor 5|Fire DoT +3%/рів.|F01 ≥2|
|F03|Розпалення|Minor 5|Fire Skill Damage +2%/рів.|F01 ≥2|
|F04|Клеймо Тління|Notable 1|Fire DoT +1 с, якщо дозволяє джерело; 1 раз/proc|F02 ≥3|
|F05|Вибух Горна|Notable 1|Fire Resonance Burst +10%; DoT Tick −5%|F03 ≥3|
|F06|Палаюче Серце|Keystone 1|Fire Damage +30%, Fire DoT +20%, Water Direct −15%|F04 ≥1 AND F05 ≥1|

### 10.2. Вода — W01–W06

|ID|Назва|Тип / Max|Ефект Balance v1|Prerequisite|
|---|---|---|---|---|
|W01|Гнучка Хвиля|Minor 5|Water Damage +3%/рів.|C05 ≥1|
|W02|Приплив Умінь|Minor 5|Cooldown Recovery +1%/рів.|W01 ≥2|
|W03|Стійкість Хвиль|Minor 5|Water RES +1.5 п.п./рів.|W01 ≥2|
|W04|Відлуння Припливу|Notable 1|Після Water Skill наступний Resonance +6% Damage|W02 ≥3|
|W05|Холодна Течія|Notable 1|Water Debuff Duration +12%|W03 ≥3|
|W06|Нескінченний Потік|Keystone 1|Cooldown Recovery +20%, Direct Skill Damage −10%|W04 ≥1 AND W05 ≥1|

### 10.3. Природа — N01–N06

|ID|Назва|Тип / Max|Ефект Balance v1|Prerequisite|
|---|---|---|---|---|
|N01|Шлях Коріння|Minor 5|Nature Damage +3%/рів.|C05 ≥1|
|N02|Токсичний Сік|Minor 5|DoT Damage +3%/рів.|N01 ≥2|
|N03|Міцний Стовбур|Minor 5|Max HP +2%/рів.|N01 ≥2|
|N04|Зерно Розпаду|Notable 1|Nature Delayed Effects +12% Damage|N02 ≥3|
|N05|Зелений Покрив|Notable 1|Nature Proc: Heal 0.5% Max HP, ICD 8 с|N03 ≥3|
|N06|Коріння Світового Дерева|Keystone 1|DoT Damage +35%, Burst Resonance Damage −12%|N04 ≥1 AND N05 ≥1|

### 10.4. Світло — L01–L06

|ID|Назва|Тип / Max|Ефект Balance v1|Prerequisite|
|---|---|---|---|---|
|L01|Промінь Віри|Minor 5|Light Damage +3%/рів.|C05 ≥1|
|L02|Світла Пунктирність|Minor 5|Crit Rate проти босів +0.75 п.п./рів.|L01 ≥2|
|L03|Захисний Ореол|Minor 5|Light RES +1.5 п.п./рів.|L01 ≥2|
|L04|Чистий Удар|Notable 1|Light Resonance Boss Damage +10%|L02 ≥3|
|L05|Печать Спокути|Notable 1|Light Skills: Shield Strength +12%, або Skill Damage +6% без щита|L03 ≥3|
|L06|Суд Світла|Keystone 1|Crit Rate vs Boss +12 п.п.; Crit DMG −10%|L04 ≥1 AND L05 ≥1|

### 10.5. Тьма — D01–D06

|ID|Назва|Тип / Max|Ефект Balance v1|Prerequisite|
|---|---|---|---|---|
|D01|Тіньовий Крок|Minor 5|Dark Damage +3%/рів.|C05 ≥1|
|D02|Глибока Рана|Minor 5|Damage по цілях нижче 40% HP +2%/рів.|D01 ≥2|
|D03|Темний Панцир|Minor 5|Dark RES +1.5 п.п./рів.|D01 ≥2|
|D04|Знак Скверни|Notable 1|Dark DoT Duration +12%|D02 ≥3|
|D05|Лезо Порожнечі|Notable 1|Dark Resonance Low-HP Bonus +10% від базового бонусу|D03 ≥3|
|D06|Апетит Безодні|Keystone 1|Damage проти цілей нижче 40% HP +25%, вище 70% HP −10%|D04 ≥1 AND D05 ≥1|

### 10.6. Блискавка — E01–E06

|ID|Назва|Тип / Max|Ефект Balance v1|Prerequisite|
|---|---|---|---|---|
|E01|Сила Іскри|Minor 5|Lightning Damage +3%/рів.|C05 ≥1|
|E02|Швидка Рука|Minor 5|Attack Speed +2%/рів.|E01 ≥2|
|E03|Імпульс Серії|Minor 5|Multi-hit Skill Damage +2%/рів.|E01 ≥2|
|E04|Провідник Струму|Notable 1|Lightning Chain-Hit Damage +12%|E02 ≥3|
|E05|Заряджене Поле|Notable 1|Lightning Proc: Combo Gain +5% на 4 с|E03 ≥3|
|E06|Перевантаження|Keystone 1|Attack Speed +25%, Single Direct Hit Damage −8%|E04 ≥1 AND E05 ≥1|

**Важливо:** E06 — Keystone із назвою «Перевантаження». Він не є тією самою сутністю, що й активна навичка Lightning «Перевантаження».

Використовувати різні технічні ID.

### 10.7. Вітер — V01–V06

|ID|Назва|Тип / Max|Ефект Balance v1|Prerequisite|
|---|---|---|---|---|
|V01|Потік Повітря|Minor 5|Wind Damage +3%/рів.|C05 ≥1|
|V02|Відлік Бурі|Minor 5|Resonance ICD −1%/рів., до cap|V01 ≥2|
|V03|М'який Порив|Minor 5|Cooldown Recovery +1%/рів.|V01 ≥2|
|V04|Вихор Влади|Notable 1|Wind AoE Radius +15%; проти одиночної цілі Wind Skill Damage +5%|V02 ≥3|
|V05|Точний Подих|Notable 1|Wind Attack Speed Buff Duration +15%|V03 ≥3|
|V06|Око Бурі|Keystone 1|Resonance ICD −12%, AoE +20%, Physical Direct −10%|V04 ≥1 AND V05 ≥1|

## 11. Обмеження Elemental Keystone

Усього 7 Elemental Keystone:

- F06 — Палаюче Серце.
    
- W06 — Нескінченний Потік.
    
- N06 — Коріння Світового Дерева.
    
- L06 — Суд Світла.
    
- D06 — Апетит Безодні.
    
- E06 — Перевантаження.
    
- V06 — Око Бурі.
    

Одночасно можна активувати не більше двох.

### Правила

1. Третій Elemental Keystone в одному пресеті заблокований.
    
2. Можна вкладати TP у різні стихійні Minor та Notable за виконаних prerequisites.
    
3. Придбання Keystone не створює стихійного каналу.
    
4. Keystone працює лише в межах визначеного ефекту.
    
5. Негативні tradeoff-модифікатори обов'язково застосовуються.
    
6. Keystone не дозволяє обходити True Elemental Immunity.
    

## 12. Resonance Bridges — 21 вузол

Кожен Bridge модифікує один із 21 затверджених Double Resonance.

### Загальні правила

- Один Bridge на одну неупорядковану пару стихій.
    
- Max Rank = 1.
    
- Cost = 3 TP.
    
- Для придбання потрібні Minor Rank ≥1 обох відповідних секторів.
    
- Придбання не вимагає тимчасово екіпірувати відповідні стихії.
    
- Бойовий ефект працює лише тоді, коли пара справді активна.
    
- Для Hero Resonance враховується обраний Reaction Focus.
    
- Bridge не створює додатковий proc.
    
- Bridge не обходить Internal Cooldown.
    

### Повний каталог

|ID|Резонанс|Ефект Bridge — Balance v1|Prerequisite|
|---|---|---|---|
|B01|Пар (Steam)|Burst +8%; Shred Duration +0.3 с|F01 ≥1 AND W01 ≥1|
|B02|Дике Полум'я|Spread Efficiency +10%; без додаткового proc на нових цілях|F01 ≥1 AND N01 ≥1|
|B03|Сонячний Спалах|Resonance Damage +8%|F01 ≥1 AND L01 ≥1|
|B04|Пекельне Клеймо|Execute Bonus +2 п.п. для цього ефекту|F01 ≥1 AND D01 ≥1|
|B05|Плазма|Single Target Arc-Hit +5% від бази|F01 ≥1 AND E01 ≥1|
|B06|Вогняний Шторм|Tempo Buff Duration +8%|F01 ≥1 AND V01 ≥1|
|B07|Цвітіння|Seed Detonation Damage +8%|W01 ≥1 AND N01 ≥1|
|B08|Очищення|Bonus Hit +8%; без додаткового Barrier Removal|W01 ≥1 AND L01 ≥1|
|B09|Безодній Приплив|DoT Duration +8%|W01 ≥1 AND D01 ≥1|
|B10|Електроліз|Echo-Hit Damage +8%|W01 ≥1 AND E01 ≥1|
|B11|Штормовий Туман|Crit/Tempo Buff +0.5 с|W01 ≥1 AND V01 ≥1|
|B12|Священне Відродження|Radiant Seed Damage +10%|N01 ≥1 AND L01 ≥1|
|B13|Розклад|Rot Stack Duration +10%|N01 ≥1 AND D01 ≥1|
|B14|Живий Струм|Vine-Hit Damage +10%|N01 ≥1 AND E01 ≥1|
|B15|Споровий Шторм|Перенесена хмара зберігає +10% залишкової тривалості|N01 ≥1 AND V01 ≥1|
|B16|Анігіляція|Resonance Damage +8%, ICD залишається 2.0 с|L01 ≥1 AND D01 ≥1|
|B17|Небесний Суд|Boss Bonus +3 п.п.|L01 ≥1 AND E01 ≥1|
|B18|Сяючий Потік|Skill Buff Duration +0.5 с|L01 ≥1 AND V01 ≥1|
|B19|Чорний Імпульс|Hero Buff Duration +0.5 с|D01 ≥1 AND E01 ≥1|
|B20|Порожній Шторм|Boss Low-HP Bonus +2 п.п.; без Execute босів|D01 ≥1 AND V01 ≥1|
|B21|Буревій|Chain-Hit +10% Resonance Power|E01 ≥1 AND V01 ≥1|

### Bridge Validation

Придбання та використання — дві різні перевірки.

**Purchase Check:**

Відповідні два Minor вузли мають Rank ≥1.

**Combat Check:**

Відповідна пара стихій реально утворює дозволений активний резонанс.

### Обмеження

- Bridge не змінює базову назву резонансу.
    
- Не створює нової пари стихій.
    
- Не створює 22-й Double Resonance.
    
- Не створює 36-й Triple Resonance.
    
- Не обходить True Immunity.
    
- Не змінює Resonance ICD, якщо цього прямо не дозволяє ефект.
    

Повний каталог резонансів:

[Resonances](Resonances.md).

## 13. Global Keystone — 4 вузли

Усі Global Keystone мають:

- Max Rank = 1.
    
- Cost = 10 TP.
    
- Усього може бути активний один Global Keystone.
    

|ID|Назва|Ефект Balance v1|Prerequisite|
|---|---|---|---|
|G01|Чистий Елементаліст|Physical Damage −80%, Elemental +20%, Resonance +20%|C05 ≥3 AND S02 ≥3|
|G02|Такт Берсерка|Hero Damage = 0, Manual/Hold +60%, Combo Cap +50%|M07 ≥1 AND M10 ≥3|
|G03|Полководець|Manual Direct −30%, Auto Attack +35%, Hero Damage +35%|A08 ≥1 AND A12 ≥2|
|G04|Архітектор Резонансу|Triple Effects +50% від бази, Skill Damage −15%|S05 ≥3 AND S10 ≥1|

### G01 — Чистий Елементаліст

Спеціалізується на стихіях та резонансах.

Компроміс — значне зниження Physical Damage.

### G02 — Такт Берсерка

Спеціалізується на Manual/Hold Attack.

Hero Damage стає 0, але активний Герой не зникає.

Його вроджена стихія може залишатися доступною для дозволеного Hero/Triad Resonance.

### G03 — Полководець

Спеціалізується на Auto та Hero Damage.

Manual Direct Damage знижується, але ручні атаки не вимикаються.

### G04 — Архітектор Резонансу

Посилює Triple Resonance Effects.

Компроміс — зниження Skill Damage.

### Правило взаємовиключності

Global Keystone взаємовиключні.

Не можна обійти обмеження через перемикання пресетів.

Бонуси неактивного пресета не працюють.

## 14. Combat Caps

Таланти підпорядковуються бойовим обмеженням із Combat Bible.

Орієнтири Balance v1:

- Attack Speed Bonus: Soft Cap +100%.
    
- Cooldown Recovery: Soft Cap +60%.
    
- Elemental Penetration: Soft Cap 40%.
    
- Temporary RES Shred: Soft Cap приблизно 40 п.п.
    
- Resonance ICD: не нижче дозволеної безпечної межі.
    

Не можна створювати:

- Нескінченний Attack Speed.
    
- Нульовий Resonance ICD.
    
- Повне обходження True Immunity.
    
- Нескінченне Healing через proc.
    
- Необмежене зменшення cooldown.
    

Порядок і конкретні обмеження визначає [Combat](Combat.md).

## 15. Skill Mutations — 14 стихійних навичок

Для кожної з 14 базових стихійних навичок передбачено дві Major Mutation.

Разом: 28 варіантів Major Mutation.

### Правила

- Мутація доступна після придбання S10 або відповідного Elemental Notable за правилами Talent Bible.
    
- Для одного скіла одночасно активна максимум одна Major Mutation.
    
- Необрана мутація не впливає на навичку.
    
- Без вибору мутації працює базова версія скіла з Combat Bible.
    
- Mutations не створюють нових стихійних каналів.
    
- Mutations не обходять Resonance Proc Caps.
    
- Конкретні ефекти — Balance v1.
    

### 15.1. Fire

**Метеор**

Mutation A — Тліюче Ядро:

- 35% Burst переводиться в DoT на 4 с.
    

Mutation B — Зіркові Уламки:

- Три додаткові слабкі удари по 35%.
    
- Без неконтрольованого додаткового proc.

Візуальне правило: базовий **Метеор** та додаткові уламки **Mutation B (Зіркові Уламки)** візуально падають зверху по діагоналі на ворога через `Tween`, завдаючи передбачену шкоду в момент удару кожного метеора. Interrupt перевіряється на дозволених влучаннях, але вся активація має бюджет максимум одного успішного переривання; після успіху уламки не збивають наступні касти (Combat §9.4).
    

**Палаюче Клеймо**

Mutation A — Довга Печатка:

- DoT Duration +25%.
    
- Tick Damage −10%.
    

Mutation B — Огняний Відгук:

- Після завершення ефекту Fire Burst +100% ATK.
    

### 15.2. Water

**Припливний Спис**

Mutation A — Прорив Течії:

- RES Shred +3 п.п. проти звичайних ворогів.
    
- Проти босів +1 п.п.
    

Mutation B — Широкий Спис:

- Два слабкі додаткові удари по 35%.
    

**Злива**

Mutation A — Туманна Злива:

- Один додатковий слабкий hit.
    

Mutation B — Лікувальна Злива:

- Після завершення Self-Heal 2% Max HP.
    
- ICD 14 с.
    

### 15.3. Nature

**Шквал Шипів**

Mutation A — Злам Голок:

- Додатково +10% DoT після шквалу.
    

Mutation B — Колюча Серія:

- Шостий бонусний hit завдає 30% damage.
    

**Насіння Руйнування**

Mutation A — Сухе Насіння:

- Detonation через 2 с.
    
- Коефіцієнт шкоди 90% від базового.
    

Mutation B — Отруйне Насіння:

- 20% Burst переводиться в DoT за 5 с.
    

### 15.4. Light

**Промінь Суду**

Mutation A — Прицільний Суд:

- Crit Damage проти босів +15%.
    

Mutation B — Розщеплення:

- Два удари по 55% замість одного променя.
    

**Сяюча Печать**

Mutation A — Захисна Печать:

- Barrier Strength Bonus +3%.
    

Mutation B — Спрямована Печать:

- Skill Damage +3 п.п.
    
- Duration −1 с.
    

### 15.5. Dark

**Розріз Безодні**

Mutation A — Чорна Рана:

- 15% Damage переводиться в DoT за 4 с.
    

Mutation B — Пробивний Розріз:

- Додатково +5% Ignore Positive RES.
    
- Cooldown +2 с.
    

**Прокляття Руйнування**

Mutation A — Довга Скверна:

- Duration +2 с.
    
- Сила ефекту −2 п.п.
    

Mutation B — Проклята Мітка:

- Ціль позначається.
    
- Hero Damage по позначеній цілі +6%.
    

### 15.6. Lightning

**Ланцюгова Блискавка**

Mutation A — Статичний Контур:

- Прискорення hit cadence.
    
- Proc Cap не змінюється.
    

Mutation B — Гримучий Фінал:

- Останній hit отримує +40% damage.
    

**Перевантаження — активна навичка**

Mutation A — Постійний Струм:

- Duration +2 с.
    
- Attack Speed Bonus −5 п.п.
    

Mutation B — Іскровий Ривок:

- Combo Gain +5 п.п.
    
- Cooldown +2 с.
    

### 15.7. Wind

**Циклон**

Mutation A — Широкий Циклон:

- AoE Radius +20%.
    

Mutation B — Шквальний Циклон:

- Один додатковий слабкий tick.
    
- Без додаткового resonance proc.
    

**Крок Бурі**

Mutation A — Біг Вітру:

- Cooldown Recovery +3 п.п.
    
- Duration −1 с.
    

Mutation B — Тиха Буря:

- Hero Attack Speed +6% на час ефекту.
    

## 16. Soul Skills — Permanent Progression

Soul Skills купуються за Available Souls.

Вони зберігаються після Rebirth.

Покупки не зменшують Total Souls Collected.

Існують:

- 4 Active Soul Skills.
    
- 10 Passive Soul Skills.
    

Soul Skills не є звичайними Talent Tree Nodes.

## 17. Чотири Active Soul Skills

### 17.1. Берсерк-Драйв

- Cooldown: 20 с.
    
- Duration: 8 с.
    
- Manual/Hold/Auto Damage +25%.
    
- Hero Damage −10%.
    

### 17.2. Розрив Резонансу

- Cooldown: 25 с.
    
- Активує доступний Core/Hero Resonance із 100% силою.
    
- RES відповідних стихій −10% на 5 с.
    
- Проти босів −6%.
    

### 17.3. Злам Часу

- Cooldown: 30 с.
    
- Зменшує залишковий cooldown активних навичок на 35%.
    

### 17.4. Абсолютний Фокус

- Cooldown: 24 с.
    
- Duration: 7 с.
    
- Обраний Reaction Focus отримує +25% Resonance Damage.
    
- Інші resonance proc тимчасово не запускаються.
    

### 17.5. Ціна Active Soul Skills

Balance v1:

|Порядок|Available Souls|
|---|---|
|Active 1|35|
|Active 2|50|
|Active 3|70|
|Active 4|100|

Відкриваються одноразово.

Активні Soul Skills займають ті самі чотири бойові слоти ГГ, що й інші активні навички.

## 18. Десять Passive Soul Skills

|№|Назва|Ефект за рівень|Max Rank|
|---|---|---|---|
|1|Майстерність Резонансу|Resonance Damage +2%|10|
|2|Точність Героя|Crit Rate +1 п.п.|10|
|3|Смертельний Імпульс|Crit DMG +3%|10|
|4|Мисливець на Владик|Damage vs Zone Boss/Guardian/General +2%|10|
|5|Автоматичне Ядро|Auto Attack Damage +4%|10|
|6|Зв'язок із Героєм|Hero Damage +3%|10|
|7|Провідник Стихій|Elemental Damage +2%|10|
|8|Швидкоплинна Магія|Cooldown Recovery +1.5%|10|
|9|Глибина Скверни|DoT Damage +2%|10|
|10|Пробивний Потік|Elemental Penetration +1%|8|

### Вартість Passive Soul Skills

Balance v1:

Перший рівень:

`10 Available Souls`

Для наступного рівня N:

`PassiveSoulCost(N) = ceil(10 × 1.45^(N−1))`

Soul Skills залишаються придбаними після Rebirth.

Бойові Soft Caps застосовуються до отриманих бонусів.

## 19. Soul Power

Постійний множник Soul Power:

`SoulPowerMult = 1 + 0.10 × TotalSoulsCollected`

### Важливі правила

- Total Souls Collected не зменшується.
    
- Available Souls зменшується при покупках.
    
- Soul Skills не знижують Soul Power.
    
- Soul Relics не знижують Soul Power.
    
- Придбання Talent Presets не знижує Soul Power.
    

### Приклад

Total Souls Collected = 100.

Available Souls = 40.

Soul Power розраховується від 100 Souls.

Якщо витратити 20 Available Souls, Total Souls залишиться 100.

Детальна економіка:

[Economy](Economy.md).

## 20. Soul Relics — 14 постійних реліквій

Soul Relics — permanent meta-progression.

### Канон

- Реліквія купується один раз.
    
- Не займає слот спорядження.
    
- Не має Item Rank.
    
- Не має Item Upgrade.
    
- Не отримує Rarity чи Enchant.
    
- Зберігається через Rebirth.
    
- Не створює додатковий елементальний канал.
    
- Не видає додаткові TP.
    
- Не обходить True Immunity.
    

Кількість одночасно активних придбаних реліквій не обмежена окремим лімітом, але їхні ефекти повинні дотримуватися загальних бойових обмежень.

Назви та числові ефекти цих реліквій мають статус Content / Balance v1.

### Повний каталог

|ID|Реліквія|Souls|Умова|
|---|---|---|---|
|R01|Молот Грому|60|Soul Shop|
|R02|Перо Переродження|65|1 Rebirth|
|R03|Око Мисливця|80|Bestiary: 500 Kills|
|R04|Фіал Відлуння|95|1 Guardian|
|R05|Оберіг Стража|110|1 Guardian|
|R06|Серце Кузні|140|Forge II|
|R07|Підкова Мандрівника|150|2 Expedition Slots|
|R08|Печатка Відродження|200|2 Rebirth|
|R09|Світанкова Лінза|230|Light Tower Progress|
|R10|Чорний Компас|260|Dark Tower Progress|
|R11|Обруч Родючості|275|21 Base Pet Species Discovered|
|R12|Руна Потоку|320|1 General|
|R13|Серце Буревію|450|3 Generals|
|R14|Корона Резонансу|750|5 Generals|

### R01 — Молот Грому

Прив'язка: Lightning.

- Directed Chain-Hit Boss Damage +8%.
    
- Attack Speed −3%.
    

### R02 — Перо Переродження

Прив'язка: Rebirth.

- Після Rebirth +5% Gold Gain до Floor 80.
    
- Не переносить Gold між забігами.
    

### R03 — Око Мисливця

Прив'язка: Boss.

- Після відкриття Bestiary Weakness +5% Damage по відповідній Enemy Family.
    

### R04 — Фіал Відлуння

Прив'язка: Active Skills.

- Перший використаний Active Skill у Boss Fight отримує 10% Cooldown Refund.
    
- Один раз за бій.
    

### R05 — Оберіг Стража

Прив'язка: Defense.

- Після отримання Stun наступний Stun має на 25% меншу тривалість.
    
- ICD 30 с.
    

### R06 — Серце Кузні

Прив'язка: Forge.

- Після Rebirth Epic Armor Unseal отримує +1 ступінь раннього захисного бонусу.
    
- Не змінює Floor Gate.
    

Точне значення «ступеня раннього захисного бонусу» потрібно деталізувати до реалізації, якщо воно не визначене окремими даними.

Не вигадувати власний відсоток.

### R07 — Підкова Мандрівника

Прив'язка: Expeditions.

- +5% гарантованої базової нагороди Target Expedition.
    
- Не покращує Rare Reward Roll.
    

### R08 — Печатка Відродження

Прив'язка: Rebirth.

- +5% Souls Earned під час Rebirth.
    
- Не застосовує Soul Bonus вдруге до Total Souls Collected.
    

### R09 — Світанкова Лінза

Прив'язка: Light.

- Light Boss Skill Damage +8%.
    
- Dark Direct Damage −3%.
    

### R10 — Чорний Компас

Прив'язка: Dark.

- Execute Bonus проти босів +5% від його базового значення.
    
- Max HP −3%.
    

### R11 — Обруч Родючості

Прив'язка: Nature/Pets.

- Pet Economy Bonus +5%.
    
- Pet Combat Bonus −2%.
    

### R12 — Руна Потоку

Прив'язка: Water.

- Water Debuff Duration +0.5 с.
    
- Direct Water Damage −3%.
    

### R13 — Серце Буревію

Прив'язка: Wind.

- Wind Tempo-Buff Duration +10%.
    
- Boss Physical Direct Damage −3%.
    

### R14 — Корона Резонансу

Прив'язка: Triple Resonance.

- +5% від базового числового Triple Resonance Effect.
    
- Не створює окремий новий множник.
    

## 21. Три Talent Presets

Гравець може мати три пресети.

### Preset 1

- Безкоштовний.
    
- Відкривається з Talent Tree.
    
- Активний за замовчуванням.
    

### Preset 2

Balance v1:

- 3 000 Gold.
    
- 30 Available Souls.
    

Після покупки слот назавжди залишається відкритим.

### Preset 3

Balance v1:

- 25 000 Gold.
    
- 120 Available Souls.
    

Після покупки слот назавжди залишається відкритим.

### Спільний пул TP

Існує один TalentPointsEarnedInRun.

Приклад:

Гравець заробив 100 TP.

- Preset 1 може мати розподіл до 100 TP.
    
- Preset 2 може мати свій розподіл до 100 TP.
    
- Preset 3 може мати свій розподіл до 100 TP.
    

Це не означає 300 одночасно активних TP.

Бонуси працюють лише від поточного активного пресета.

### Дані пресета

Кожен пресет зберігає:

- Preset ID.
    
- Назву.
    
- Іконку.
    
- Intended Node Ranks.
    
- Purchase Order.
    
- 4 Active Skill Slot IDs.
    
- Selected Elemental Keystones.
    
- Selected Global Keystone.
    

### Правила перемикання

Перемикання між купленими пресетами безкоштовне поза боєм.

Заборонено перемикати:

- Під час Combat.
    
- Під час Boss Fight.
    
- Під час Active Cooldown.
    
- Під час Stun.
    
- Під час Summon Animation.
    

Cooldown уже екіпірованих навичок не обнуляється.

Нова екіпірована навичка отримує Safe Cooldown із відповідним залишком і мінімумом 2 с.

Не дозволяти перемиканням пресетів обходити Cooldowns або Talent Caps.

## 22. Talent Reset

### 22.1. Перший Reset

Перший Reset у кожному run безкоштовний.

### 22.2. Наступні Reset

Balance v1:

`ResetCostGold = 1000 × (1 + paid_resets)^2`

### 22.3. Правила

- Reset змінює розподіл уже зароблених TP.
    
- Не створює нових TP.
    
- Не дозволяє повторно отримати TP з уже переможеного Boss.
    
- Не скидає постійні Soul Skills.
    
- Не скидає Soul Relics.
    
- Не зменшує Total Souls Collected.
    

Оплата Crystals за звичайний Reset вимкнена за замовчуванням до окремого рішення щодо курсу та балансу.

## 23. Rebirth та Talent Progression

Talent Tree є run-based системою.

### Після Rebirth скидаються

- Earned TP.
    
- Unspent TP.
    
- Придбані Node Ranks.
    
- Фактично активні вузли.
    
- Boss TP Award Flags.
    
- Trial TP Milestone Flags.
    
- Тимчасові Skill Mutations, залежні від Run Talent Tree.
    

### Після Rebirth зберігаються

- Відкритий Talent Tree.
    
- Придбані Talent Preset Slots.
    
- Preset Names.
    
- Preset Templates.
    
- Purchase Order.
    
- Active Soul Skill Unlocks.
    
- Passive Soul Skill Ranks.
    
- Soul Relics.
    
- Total Souls Collected.
    
- Available Souls.
    

### Відновлення шаблону

Після нового Rebirth:

1. Earned TP = 0.
    
2. Actual Node Ranks = 0.
    
3. Intended Rank Map залишається.
    
4. Purchase Order залишається.
    
5. Після отримання TP можна відновлювати вузли rank-by-rank.
    
6. Система перевіряє prerequisites, доступні TP та Keystone Caps.
    
7. Якщо TP не вистачає, решта плану залишається невиконаною.
    

Не допускати негативного TP Balance.

## 24. Talent Tree UI

### 24.1. Радіальна структура

Повинен бути доступний огляд усіх вузлів активного профілю; у базовому каталозі їх 120.

Візуальні групи:

- Central Ring.
    
- Manual / Combo.
    
- Auto / Hero / Pets.
    
- Skills / Resonance.
    
- Сім стихійних секторів.
    
- Resonance Bridges.
    
- Global Keystone.
    

### 24.2. Фільтри

- Central.
    
- Manual.
    
- Auto/Hero.
    
- Skills/Resonance.
    
- Elements.
    
- Bridges.
    
- Global Keystone.
    

21 лінію Resonance Bridges не потрібно одночасно показувати поверх усього дерева.

Їх можна відображати при відповідному фільтрі.

### 24.3. Talent Tooltip

Відображати:

- Node ID.
    
- Назву.
    
- Категорію.
    
- Поточний Rank.
    
- Max Rank.
    
- Effect per Rank.
    
- TP Cost.
    
- Prerequisites.
    
- Статус доступності.
    
- Keystone Cap Warning.
    
- Вплив на відповідні Combat Stats.
    

### 24.4. Skill Loadout

Відображати чотири активні слоти.

Доступні кандидати:

- 14 базових стихійних активних навичок.
    
- 4 Active Soul Skills.
    
- 3 Active Talent Skills.
    

Не всі кандидати автоматично доступні від початку.

### 24.5. Soul Shop

Показувати окремо:

- Total Souls Collected.
    
- Available Souls.
    
- Active Soul Skills.
    
- Passive Soul Skills.
    
- Soul Relics.
    
- Prices.
    
- Prerequisites.
    
- Purchased State.
    

## 25. Технічна реалізація в Godot

### 25.1. TalentNodeDef

Поля:

- id
    
- title_key
    
- group
    
- tier
    
- max_rank
    
- tp_cost_by_rank[]
    
- effects[]
    
- prereqs[]
    
- tags[]
    

### 25.2. TalentGraphDef

Поля:

- all_node_ids[] — динамічний список; 120 у базовому каталозі
    
- edges[]
    
- ui_pos
    
- ui_layer
    
- unlock_rules
    
- bridge_pair
    

### 25.3. TalentRunSave

Поля:

- earned_tp
    
- boss_award_flags
    
- trial_milestone_flags
    
- spent_tp_by_preset
    
- active_preset_id
    
- reset_count
    

### 25.4. TalentPresetSave

Поля:

- purchased
    
- label
    
- intended_rank_map
    
- purchase_order[]
    
- skill_slots[4]
    
- selected_keystones
    

### 25.5. SoulProgressSave

Поля:

- total_souls_collected
    
- available_souls
    
- passive_ranks
    
- active_unlocks
    
- relic_ids[]
    

### 25.6. ProgressionSave

Поля:

- run_gg_level
    
- run_gg_xp
    
- gold_upgrade_levels
    
- rebirth_count
    
- unlock_flags
    
- max_floor
    

### 25.7. Combat Cache

Обчислені бойові модифікатори повинні оновлюватися після:

- Зміни екіпірування.
    
- Перемикання пресета.
    
- Покупки вузла.
    
- Talent Reset.
    
- Зміни активної навички.
    
- Зміни Героя.
    
- Підвищення рівня.
    
- Rebirth.
    

Combat Cache не є джерелом істини в SaveData.

## 26. Валідація Talent Graph

Перед реалізацією UI необхідно перевірити структуру.

### Graph Integrity

- Базовий профіль має 120 унікальних NodeDefinition; експериментальні профілі перевіряються за своїм маніфестом без дублювання ID.
    
- Немає повторних ID.
    
- Усі Prerequisites посилаються на існуючі вузли.
    
- Граф залежностей не містить циклів.
    
- Усі Keystone доступні через валідний шлях.
    
- Ціни відповідають типу вузла.
    
- Max Rank відповідає Talent Bible.
    

### Structure Validation

`14 + 39 + 42 + 21 + 4 = 120`

### v1.1 Notable Regression Checks

Обов'язково перевірити:

- M07: Max Rank 1, Cost 3 TP.
    
- M11: Max Rank 1, Cost 3 TP.
    
- A11: Max Rank 1, Cost 3 TP.
    
- S10: Max Rank 1, Cost 3 TP.
    

Друга покупка кожного з цих вузлів має відхилятися.

## 27. Talent Points Validation

- Перша Башта вперше дає 5 TP.
    
- Після першого відкриття дерева Zone Boss дає 1 TP один раз за run.
    
- Guardian дає 2 TP один раз за run.
    
- Commander дає 2 TP один раз за run.
    
- General дає 4 TP один раз за run.
    
- Boss Repeat не видає повторний TP.
    
- Direct Challenge не видає повторний TP.
    
- Trial Floor 50/100/200/300 дають по 1 TP один раз за run.
    
- Trial TP має максимум +4 за run.
    
- Після Rebirth Boss TP Flags очищуються.
    
- Після Rebirth TP не залишаються доступними.
    

### Теоретичний максимум

За всі 21 Prison Tower в одному run:

189 TP.

За всі сім Celestial Tower:

301 TP.

Разом:

490 TP.

Trial Milestones:

+4 TP.

Повний теоретичний максимум:

**494 TP за run.**

Це математична межа конкретного набору активностей, а не обіцянка доступності всього контенту за один реальний забіг.

## 28. Combat Validation

- Talent Effects відповідають визначеним Node IDs.
    
- Немає подвійного застосування одного ефекту.
    
- Soft Caps працюють.
    
- Третій Elemental Keystone заблокований.
    
- Другий Global Keystone заблокований.
    
- Bridge працює лише для активної пари.
    
- Bridge не створює додатковий proc.
    
- Hero Resonance підкоряється Reaction Focus.
    
- Жоден талант не обходить True Immunity.
    
- Active Talent Skill займає один із чотирьох слотів.
    
- Talent Mutation не створює додатковий елементальний канал.
    
- На одну навичку активна не більш ніж одна Major Mutation.
    
- Немає нескінченного зменшення Cooldown/ICD.
    

## 29. Preset Validation

- Preset 1 безкоштовний.
    
- Preset 2 і 3 купуються один раз.
    
- Усі пресети використовують один спільний Earned TP Pool.
    
- Лише активний пресет дає бонуси.
    
- Preset Swap не працює в Combat.
    
- Preset Swap не обнуляє Cooldowns.
    
- Preset зберігає Purchase Order.
    
- Після Rebirth Preset Template зберігається.
    
- Після Rebirth Actual Ranks скидаються.
    
- Автовідновлення не обходить Prerequisites.
    
- Reset не створює нових TP.
    
- Reset не змінює Soul Relics.
    

## 30. Soul Validation

- Active Soul Skills зберігаються після Rebirth.
    
- Passive Soul Skills зберігають рівні.
    
- Soul Relics зберігаються.
    
- Реліквія не купується повторно.
    
- Total Souls не зменшується при покупці.
    
- Available Souls списуються рівно один раз.
    
- Available Souls не можуть стати від'ємними.
    
- Реліквії не займають Gear Slots.
    
- Реліквії не обходять True Immunity.
    
- R14 не створює окремий додатковий Triple Multiplier.
    

## 31. Балансні ризики

### T01 — Вартість дерева

Потрібно перевірити:

- Скільки TP необхідно для повного розвитку окремих білдів.
    
- Чи можна досягти Global Keystone в потрібному темпі.
    
- Чи достатньо TP на ранніх етапах.
    
- Чи не стає більшість вузлів непотрібною після Rebirth.
    

### T02 — Keystone Balance

Потрібно порівняти:

- Mono Element.
    
- Dual Element.
    
- Triple Resonance.
    
- Manual.
    
- Auto/Hero.
    
- DoT.
    
- Survival.
    

### T03 — Soul Power

Soul Power може накопичуватися значно швидше, ніж росте складність ворогів.

Потрібні багаторазові Rebirth Simulations.

### T04 — Preset Economy

Потрібно перевірити доступність другого й третього пресета за Gold/Souls.

### T05 — Relic Power Budget

Не дозволяти Relic Effects створювати надмірні нескінченні множники.

### T06 — Cooldown / ICD

Сукупні бонуси талантів не повинні дозволяти нульові cooldown.

## 32. Заборони для Claude Code

Без погодження розробника заборонено:

- Додавати нові вузли до базового каталогу без явного експериментального маніфесту або затвердження результатів.
    
- Видаляти існуючі Node IDs.
    
- Мовчки перезаписувати базову структуру 14+39+42+21+4 замість окремого експериментального профілю.
    
- Додавати четверту Active Talent Skill.
    
- Розширювати чотири загальні активні слоти.
    
- Дозволяти понад два Elemental Keystone.
    
- Дозволяти понад один Global Keystone.
    
- Змінювати базові 21 Double Resonance.
    
- Додавати нові Triple Resonance через Talents.
    
- Обходити True Elemental Immunity.
    
- Перетворювати Run Talents на постійні без погодження.
    
- Скидати Soul Skills та Relics при Rebirth.
    
- Скидати придбані Preset Slots при Rebirth.
    
- Дозволяти повторне отримання TP за того самого Boss ID у run.
    
- Зменшувати Total Souls при покупках.
    
- Видавати неперевірені експериментальні таланти за затверджений фінальний каталог; реліквії не змінювати без окремого рішення.
    
- Вважати Balance v1 фінальним без тестування.
    

## 33. Пов'язані документи

- [Головні правила](../02_Core_Rules.md)
    
- [Огляд гри](../01_Game_Overview.md)
    
- [Бойова система](Combat.md)
    
- [Стихії](Elements.md)
    
- [Резонанси](Resonances.md)
    
- [Екіпірування](Equipment.md)
    
- [Кузня](Crafting.md)
    
- [Економіка](Economy.md)
    
- [Прогресія](Progression.md)
    
- [Головний Герой](../Characters/Main_Character.md)
    
- [Герої](../Characters/Heroes.md)
    
- [Вихованці](../Characters/Pets.md)
    
- [Башти](../World/Towers.md)
    

### Пріоритет джерел

- Talent Tree & Progression Bible v1.1 — 120 Node IDs, ціни, prerequisites, пресети, Soul Skills та Soul Relics.
    
- Combat Bible v1.2 — активні навички, бойові формули, резонанси та caps.
    
- Economy & Balance Bible v1.2 — Souls, TP, витрати, Rebirth Economy та тестування.
    
- GDD v2.3 — FTUE, загальна прогресія, Rebirth Reset/Keep.
    
- Heroes & Pets Bible v1.2 — Hero/Pet Progression.
    

Історичні посилання всередині Talent Bible на GDD v2.2 та Economy v1.0 не мають переваги над актуальними фінальними документами.

---

**Статус специфікації:** підготовлена на основі Talent Tree & Progression Design Bible v1.1.

**Усього Talent Nodes:** 120.

**Active Talent Skills:** 3.

**Elemental Keystone:** 7.

**Global Keystone:** 4.

**Resonance Bridges:** 21.

**Soul Skills:** 4 Active + 10 Passive.

**Soul Relics:** 14.

**Статус реалізації:** не реалізовано.

**Статус числового балансу:** Balance v1 — потрібні симуляції та плейтести.

## 34. Практичний експеримент із розміром дерева

**Статус:** план тестування затверджено 2026-11-04; фінальний розмір OPEN. Існуючий каталог містить 120 вузлів, не 140. Усі наявні ID, описи та базова структура збережені.

|Профіль|Призначення|Обсяг|
|---|---|---|
|Compact|Перевірити зрозумілий вибір із меншою кількістю дрібних бонусів|30–40 вузлів|
|Baseline|Перевірити наявний каталог і більш щільний варіант|100–120; чинний повний каталог 120|
|Expanded|Перевірити користь додаткових виборів лише після перших двох тестів|Близько 140; окремі нові вузли ще не спроєктовані|

Не видаляти існуючий каталог заради прототипу і не створювати 20 нових вузлів без потреби. Кожен профіль має `profile_id`, явний перелік node IDs, prerequisites, TP costs, дозволені Keystone і skill mutations. Відключений вузол не може залишатися необхідною передумовою доступного вузла. Для компактного профілю дозволено об'єднання дрібних бонусів зі збереженням ролей і стихійних шляхів; конкретні маніфести — окрема задача прототипу.

Порівнювати профілі на однакових боях, із зіставним сумарним бюджетом сили та темпом TP. Перевірити Manual, Auto/Hero, Skill/Resonance та захисні білди; ранній вибір, середину прогресії та прискорений тест пізніх Keystone. Не робити висновок за відрізком до відкриття дерева на Floor 100.

Вимірювати час першого усвідомленого вибору, розуміння наслідків, частку невикористаних вузлів, різноманітність дієвих білдів, частоту скидань через непорозуміння, час у меню та бажання спробувати інший білд. Чергувати порядок профілів між тестувальниками; записувати версію збірки та число учасників, не робити висновок за одним відгуком.

Критерій вибору — достатня різноманітність і зрозумілі рішення без зайвого обслуговування дерева. Більше вузлів саме по собі не є перевагою. Остаточний профіль затверджує розробник після результатів; синхронізуються TP economy, пресети, prerequisites і всі описи кількості.

Presets/SaveData зберігають `profile_id` і версію дерева. Не переносити вкладені TP та purchase_order між несумісними профілями мовчки. Базова формула `14 + 39 + 42 + 21 + 4 = 120` описує чинний каталог, не є універсальною перевіркою всіх експериментів.
