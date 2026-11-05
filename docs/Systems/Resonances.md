---

status: draft  
document_type: resonance-system  
source: Combat System Design Bible v1.2  
balance_status: Balance v1  
updated: 2026-10-15  
tags:

- game-system
    
- combat
    
- elements
    
- resonances
    
- godot
    

---

# RESONANCE SYSTEM — Система резонансів

> Повна специфікація 21 подвійного та 35 потрійних резонансів.
> 
> Джерело: Combat System Design Bible v1.2, розділи 3–6, 10–13.
> 
> Назви, склад комбінацій і логіка ефектів — Canon. Числові коефіцієнти, тривалості, cooldown та пороги — Balance v1, якщо інше не визначене окремим затвердженим рішенням.

## 1. Призначення системи

Система резонансів дозволяє комбінувати Первісні Стихії та створювати різні бойові білди.

Мета:

- Створити різноманітність бойових стилів.
    
- Надати значення вибору екіпірування.
    
- Поєднати стихійні канали ГГ з активним союзним Героєм.
    
- Дозволити гравцю вибирати реакції через Reaction Focus.
    
- Зробити резисти противників важливими для побудови білдів.
    
- Забезпечити конкурентність mono-element і multi-element білдів.
    

## 2. Канонічна структура

У грі існує рівно сім стихій:

- Fire — Вогонь.
    
- Water — Вода.
    
- Nature — Природа.
    
- Light — Світло.
    
- Dark — Тьма.
    
- Lightning — Блискавка.
    
- Wind — Вітер.
    

Унікальні комбінації різних стихій:

- 21 Double Resonance.
    
- 35 Triple Resonance.
    

Порядок стихій у комбінації не створює новий резонанс.

Наприклад, Fire + Water і Water + Fire — один Steam Resonance.

Не можна створювати додаткові резонанси за рахунок перестановки стихій.

## 3. Джерела активації

### 3.1. Primary Element

Перший канал ГГ.

Відкривається через 4/5 предметів броні з однаковою стихією.

### 3.2. Secondary Element

Другий канал ГГ.

Відкривається через 3/4 аксесуарів з однаковою стихією.

### 3.3. Active Hero Element

Один активний союзний Герой додає свою вроджену стихію.

Стихія Героя незмінна.

Його екіпірування не створює додаткових стихійних каналів.

### 3.4. Заборонені джерела

Не створюють новий канал резонансу:

- Стихійна зброя ГГ.
    
- Вихованці.
    
- Неактивні союзні Герої.
    
- Тимчасові візуальні ефекти стихій.
    

## 4. Типи резонансів

### 4.1. Core Resonance

Виникає між двома різними стихійними каналами ГГ.

Наприклад:

Primary = Fire.

Secondary = Water.

Core Resonance = Steam.

Balance v1:

- Базовий Internal Cooldown: 1.0 с.
    

### 4.2. Hero Resonance

Виникає між стихією активного Героя та одним відповідним каналом ГГ.

Якщо існують дві можливі пари, гравець вибирає одну через Reaction Focus.

Balance v1:

- Базовий Internal Cooldown: 1.5 с.
    

### 4.3. Triad Resonance

Активується лише за наявності трьох різних стихій:

Primary + Secondary + Active Hero.

Потрійний резонанс переважно пасивно модифікує білд, а не створює третій великий damage proc.

### 4.4. Приклад активації

Primary = Water.

Secondary = Nature.

Active Hero = Fire.

Результат:

- Core Resonance = Bloom.
    
- Hero Resonance = Steam або Wildfire.
    
- Triad Resonance = Первісний Кругообіг.
    

Reaction Focus визначає одну Hero Resonance.

Core Resonance та Triad Resonance залишаються доступними.

### 4.5. Alignment

Якщо стихії збігаються, застосовуються відповідні правила Dual, Elemental або Pure Alignment.

Вони визначені в [Combat](Combat.md) та [Elements](Elements.md).

Не створювати окремих резонансів із двох або трьох однакових стихій.

## 5. Каталог 21 Double Resonance

Назви та механіки взято з Combat Bible v1.2.

Усі наведені нижче числові значення мають статус Balance v1.

### 01. 🔥 + 💧 Пар (Steam)

**Роль:** Burst / RES Shred.

- Завдає 160% Resonance Power.
    
- Знижує Fire RES та Water RES цілі на 8% протягом 3 с.
    
- Для босів RES Shred становить 6%.
    

### 02. 🔥 + 🌿 Дике Полум'я (Wildfire)

**Роль:** DoT / Spread.

- Накладає Горіння.
    
- Завдає 45% Resonance Power за секунду протягом 4 с.
    
- Після смерті цілі 50% залишкового DoT переходить на наступного противника.
    

### 03. 🔥 + 🌟 Сонячний Спалах (Solar Flare)

**Роль:** Crit Burst.

- Завдає 210% Resonance Power.
    
- Отримує +20% Crit Rate саме для цього резонансу.
    

### 04. 🔥 + 🌑 Пекельне Клеймо (Hellfire Brand)

**Роль:** Execute / DoT.

- Завдає 30% Resonance Power за секунду протягом 5 с.
    
- По цілях нижче 30% HP всі resonance-ефекти отримують +10% damage.
    

### 05. 🔥 + ⚡ Плазма (Plasma)

**Роль:** Burst / Multi-hit.

- Основний удар: 175% Resonance Power.
    
- Додатковий arc-hit: 55% Resonance Power по двох сусідніх ворогах.
    
- Проти боса arc-hit повторно атакує основну ціль із 40% ефективністю.
    

### 06. 🔥 + 🌪️ Вогняний Шторм (Firestorm)

**Роль:** AoE / Tempo.

- Чотири тики по 45% Resonance Power.
    
- Поки шторм активний, Attack Speed +8%.
    

### 07. 💧 + 🌿 Цвітіння (Bloom)

**Роль:** Delayed Burst / Cooldown.

- Створює Насіння.
    
- Насіння вибухає після трьох resonance proc або через 4 с.
    
- Вибух завдає 220% Resonance Power.
    
- Зменшує cooldown випадкової активної навички на 0.5 с.
    

### 08. 💧 + 🌟 Очищення (Purification)

**Роль:** Utility / Universal Shred.

- Завдає 120% Resonance Power.
    
- Знімає один шар ворожого barrier або buff.
    
- Знижує всі позитивні Elemental RES на 8% протягом 4 с.
    
- Для Стражів та Генералів зниження становить 4%.
    

### 09. 💧 + 🌑 Безодній Приплив (Abyssal Tide)

**Роль:** DoT / Vulnerability.

- П'ять тиків по 30% Resonance Power.
    
- Під час ефекту ціль отримує +12% DoT Damage.
    
- Знижує RES на 6% до стихії, обраної через Reaction Focus.
    

**Уточнення для майбутньої реалізації:** Combat Bible не деталізує поведінку останнього ефекту, коли Reaction Focus недоступний. Не вигадувати автоматичний вибір стихії без погодження.

### 10. 💧 + ⚡ Електроліз (Electrocution)

**Роль:** Rapid DoT / Proc.

- Шість тиків по 32% Resonance Power протягом 3 с.
    
- Кожен третій тик гарантовано створює Echo-hit.
    
- Echo-hit завдає 35% Resonance Power.
    

### 11. 💧 + 🌪️ Штормовий Туман (Storm Mist)

**Роль:** Crit / Tempo.

- Початковий удар: 100% Resonance Power.
    
- На 5 с +10% Crit Rate для resonance-атак.
    
- На 5 с +8% Combo Gain.
    

### 12. 🌿 + 🌟 Священне Відродження (Sacred Renewal)

**Роль:** Skill Synergy.

- Накладає Radiant Seed.
    
- Наступна активна навичка детонує Radiant Seed.
    
- Детонація завдає 180% Resonance Power.
    
- Навичка отримує +10% Skill Damage.
    

### 13. 🌿 + 🌑 Розклад (Decay)

**Роль:** Stacking DoT / Shred.

- Накладає Rot.
    
- Максимум 5 стаків.
    
- Кожен стак збільшує отримувану DoT Damage на 4%.
    
- На п'яти стаках додатково знижує Nature RES і Dark RES на 8%.
    

### 14. 🌿 + ⚡ Живий Струм (Living Current)

**Роль:** Multi-hit / Burst.

- Кожен п'ятий elemental hit породжує електричну лозу.
    
- Лоза завдає 90% Resonance Power.
    
- Удар вважається Resonance Damage.
    

### 15. 🌿 + 🌪️ Споровий Шторм (Sporestorm)

**Роль:** AoE DoT.

- Створює хмару на 5 с.
    
- Завдає 28% Resonance Power за секунду.
    
- При зміні ворога хмара переноситься з 60% залишкової тривалості.
    

### 16. 🌟 + 🌑 Анігіляція (Annihilation)

**Роль:** Crit / Penetration.

- Завдає 200% Resonance Power.
    
- Гарантований критичний удар.
    
- Ігнорує 20% позитивного Light/Dark RES.
    
- Власний Internal Cooldown: 2.0 с.
    

### 17. 🌟 + ⚡ Небесний Суд (Judgment)

**Роль:** Boss Burst.

- Звичайний удар: 170% Resonance Power.
    
- Проти Зональних босів, Стражів та Генералів +20%.
    
- Кожен четвертий proc завдає 280% замість 170%.
    

### 18. 🌟 + 🌪️ Сяючий Потік (Radiant Current)

**Роль:** Cooldown / Skill.

- Завдає 90% Resonance Power.
    
- На 5 с Skill Damage +8%.
    
- На 5 с Cooldown Recovery +8%.
    

### 19. 🌑 + ⚡ Чорний Імпульс (Black Surge)

**Роль:** Crit / Hero Synergy.

- Завдає 150% Resonance Power.
    
- Додатково +25% Crit DMG для удару.
    
- На 4 с Hero Damage по цілі +10%.
    

### 20. 🌑 + 🌪️ Порожній Шторм (Voidstorm)

**Роль:** AoE / Execute.

- Три тики по 55% Resonance Power.
    
- Звичайні вороги нижче 10% HP добиваються.
    
- Боси нижче 20% HP отримують +12% Resonance Damage.
    

### 21. ⚡ + 🌪️ Буревій (Tempest)

**Роль:** Speed / Chain.

- На 5 с Attack Speed +12%.
    
- Кожен шостий direct hit створює chain-hit.
    
- Chain-hit завдає 70% Resonance Power.
    

## 6. Каталог 35 Triple Resonance

Потрійні резонанси — пасивні модифікатори білдів.

Вони активуються лише за наявності трьох різних стихій.

Balance v1: орієнтовний ефективний power budget — 8–15%, із можливими компромісами й ситуативними умовами.

### Комбінації з Fire

**01. 🔥 + 💧 + 🌿 Первісний Кругообіг**

- Resonance Damage +8%.
    
- DoT Duration +10%.
    
- Reaction Focus можна змінювати без втрати поточного resonance ICD.
    

**02. 🔥 + 💧 + 🌟 Світанкова Пара**

- Crit Rate resonance-ефектів +6%.
    
- Fire/Water RES Shred ефекти сильніші на 2 процентні пункти.
    

**03. 🔥 + 💧 + 🌑 Чорний Котел**

- DoT Damage +10%.
    
- Resonance Damage по цілях нижче 35% HP +6%.
    

**04. 🔥 + 💧 + ⚡ Грозовий Котел**

- Resonance Internal Cooldown −8%.
    
- Plasma та Electrocution отримують один додатковий слабкий hit із 25% ефективністю.
    

**05. 🔥 + 💧 + 🌪️ Киплячий Мусон**

- AoE Radius +20%.
    
- Fire/Water Resonance Damage +5%.
    

**06. 🔥 + 🌿 + 🌟 Священне Полум'я**

- Fire/Nature DoT може критувати.
    
- Використовується 40% звичайного Crit Rate.
    
- Crit DMG такого DoT становить 150% базового.
    

**07. 🔥 + 🌿 + 🌑 Полум'я Скверни**

- Максимальна кількість Rot та подібних стаків +1.
    
- Dark/Nature RES Shred сильніший на 3 процентні пункти.
    

**08. 🔥 + 🌿 + ⚡ Громове Древо**

- Кожен шостий elemental hit створює mini-burst.
    
- Mini-burst завдає 65% Resonance Power.
    
- Mini-burst не може критувати.
    

**09. 🔥 + 🌿 + 🌪️ Попелясті Спори**

- DoT Spread Efficiency +25%.
    
- При переході DoT на нову ціль тривалість збільшується на 1 с.
    

**10. 🔥 + 🌟 + 🌑 Полум'я Затемнення**

- Crit DMG +12%.
    
- Resonance Damage додатково ігнорує 5% позитивного RES.
    

**11. 🔥 + 🌟 + ⚡ Сонячна Буря**

- Skill Damage +10%.
    
- Boss Damage +5%.
    

**12. 🔥 + 🌟 + 🌪️ Сонячний Вихор**

- Attack Speed +7%.
    
- Cooldown Recovery +5%.
    

**13. 🔥 + 🌑 + ⚡ Пекельний Контур**

- По цілях нижче 50% HP Fire, Dark і Lightning Damage +8%.
    

**14. 🔥 + 🌑 + 🌪️ Попеляста Безодня**

- Execute-пороги резонансів +3 процентні пункти.
    
- DoT Tick Rate +8% без зміни загальної тривалості.
    

**15. 🔥 + ⚡ + 🌪️ Грозове Полум'я**

- Auto/Hold Attack Speed +10%.
    
- Кожні десять базових ударів створюють shockwave.
    
- Shockwave завдає 75% Resonance Power.
    

### Комбінації з Water без Fire

**16. 💧 + 🌿 + 🌟 Священне Цвітіння**

- Cooldown Recovery +6%.
    
- Delayed Burst та Seed-ефекти завдають +15% Damage.
    

**17. 💧 + 🌿 + 🌑 Чорна Трясовина**

- DoT Duration +15%.
    
- RES Shred ефекти цієї трійки сильніші на 2 процентні пункти.
    

**18. 💧 + 🌿 + ⚡ Грозове Зростання**

- Attack Speed +5%.
    
- Кожен resonance proc зменшує cooldown випадкового скіла на 0.2 с.
    
- Ефект спрацьовує не частіше одного разу за секунду.
    

**19. 💧 + 🌿 + 🌪️ Живий Туман**

- Reaction/DoT Duration +12%.
    
- AoE Radius +15%.
    

**20. 💧 + 🌟 + 🌑 Приплив Затемнення**

- All Elemental RES Shred +4 процентні пункти.
    
- Direct Resonance Damage −3%.
    

**21. 💧 + 🌟 + ⚡ Хрещення Бурею**

- Після resonance proc Crit Rate +3% на 4 с.
    
- Максимум два стаки.
    

**22. 💧 + 🌟 + 🌪️ Сяючий Туман**

- Cooldown Recovery +8%.
    
- Direct Resonance Damage +5%.
    

**23. 💧 + 🌑 + ⚡ Безодній Струм**

- DoT Tick Rate +10%.
    
- Проти босів RES Shred +3 процентні пункти.
    

**24. 💧 + 🌑 + 🌪️ Потоп Порожнечі**

- AoE Damage +10%.
    
- Цілі нижче 30% HP отримують +8% Damage від Water/Dark/Wind.
    

**25. 💧 + ⚡ + 🌪️ Море Бурі**

- Hero Attack Speed +10%.
    
- Chain-hit Damage +10%.
    

### Комбінації з Nature без Fire/Water

**26. 🌿 + 🌟 + 🌑 Сутінковий Сад**

- Усі Elemental Packets отримують +6% Damage.
    
- Ефекти Light/Dark не можуть взаємно скасовувати один одного.
    

**27. 🌿 + 🌟 + ⚡ Живий Суд**

- Hero Damage +8%.
    
- Кожен шостий удар Героя створює Resonance Spark.
    
- Resonance Spark завдає 60% Resonance Power.
    

**28. 🌿 + 🌟 + 🌪️ Священний Гай**

- Skill Duration +10%.
    
- Cooldown Recovery +5%.
    
- AoE +10%.
    

**29. 🌿 + 🌑 + ⚡ Зіпсований Контур**

- DoT Damage +12%.
    
- Crit Rate −3 процентні пункти.
    

**30. 🌿 + 🌑 + 🌪️ Чумний Вітер**

- DoT може поширюватися на одну додаткову ціль.
    
- Проти босів DoT Damage +8%.
    

**31. 🌿 + ⚡ + 🌪️ Коріння Бурі**

- Auto/Hero Damage +8%.
    
- Кожен восьмий сумарний удар створює burst.
    
- Burst завдає 55% Resonance Power.
    

### Комбінації Light / Dark / Lightning / Wind

**32. 🌟 + 🌑 + ⚡ Суд Затемнення**

- Positive RES Penetration +7%.
    
- Crit DMG resonance-ефектів +10%.
    

**33. 🌟 + 🌑 + 🌪️ Ореол Порожнечі**

- Cooldown Recovery +6%.
    
- Execute/Boss-Low-HP бонуси сильніші на 20% від їхнього базового значення.
    

**34. 🌟 + ⚡ + 🌪️ Небесний Буревій**

- Skill Damage +8%.
    
- Attack Speed +8%.
    

**35. 🌑 + ⚡ + 🌪️ Безодня Бурі**

- Resonance Damage +10%.
    
- Cooldown активних навичок +5%.
    
- Компроміс між постійною шкодою та частотою навичок.
    

## 7. Resonance Power

Основна формула:

`ResonancePower = PreRES_ElementContribution_A + PreRES_ElementContribution_B`

Для Hero Resonance використовується нормалізований elemental contribution активного Героя.

Hero Contribution має окремий Resonance Contribution Cap.

Не дозволяти Hero Damage безконтрольно збільшувати шкоду реакцій.

### Поділ шкоди

За замовчуванням damage резонансу із двох стихій розподіляється:

- 50% Element A.
    
- 50% Element B.
    

Кожен пакет окремо проходить через відповідний RES.

Інші пропорції допускаються лише за явним правилом конкретного резонансу.

## 8. Взаємодія з RES та True Immunity

True Elemental Immunity перевіряється для кожного elemental packet до RES Shred і Penetration.

Приклад:

Fire/Water resonance має 2000 базової шкоди.

Ціль має Fire True Immunity.

Результат:

- Fire packet = 1000 → 0.
    
- Water packet = 1000 → розрахунок за Water RES.
    

True Immunity не скасовує весь резонанс, якщо його друга стихія неімунна.

Жоден стандартний RES Shred або Penetration не обходить True Immunity.

Важливо: резонанси, які змінюють Penetration або RES Shred, повинні дотримуватися цього правила.

## 9. Internal Cooldown та Proc

### Базові ICD — Balance v1

- Core Resonance: 1.0 с.
    
- Hero Resonance: 1.5 с.
    

Окремі резонанси можуть мати власні значення, наприклад Annihilation 2.0 с.

### Обмеження

- Attack Speed не обнуляє ICD.
    
- Наявність швидких multi-hit атак не повинна створювати нескінченні resonance proc.
    
- Talents і Triple Resonance можуть модифікувати ICD у дозволених межах.
    
- Правила конкретних навичок мають пріоритет для спеціальних proc-умов.
    

## 10. Зміна Reaction Focus

Reaction Focus зберігається у Player Build State.

Коли ГГ має дві різні стихії, а активний Герой має третю:

- Core Resonance залишається активним.
    
- Гравець вибирає лише один Hero Resonance.
    
- Triad Resonance продовжує працювати.
    

Винятки й спеціальні умови зміни Focus визначаються конкретними ефектами, зокрема Первісним Кругообігом.

Не запускати автоматично дві Hero Resonance одночасно.

## 11. Взаємодія з іншими системами

### Equipment

- Визначає Primary і Secondary Element.
    
- Зміна екіпірування може змінити доступні резонанси.
    

### Heroes

- Один активний Герой додає одну вроджену стихію.
    
- Реакції залежать від поточного Reaction Focus.
    

### Pets

- Можуть давати бойові бонуси.
    
- Не створюють резонансних каналів.
    

### Talent Tree

- Має 21 Resonance Bridge.
    
- Модифікує відповідні затверджені резонанси.
    
- Не створює нових парних комбінацій.
    

### Soul Skills

- Можуть посилювати або примусово запускати доступні резонанси за визначеними правилами.
    

### Enemies

- RES, Weakness та True Immunity впливають на підсумкову шкоду.
    
- Фази босів можуть змінювати RES.
    

## 12. Технічні вимоги Godot

### Double Resonance Data

Кожен подвійний резонанс повинен мати:

- Стабільний унікальний ID.
    
- Дві стихії.
    
- Назву.
    
- Бойову роль.
    
- Tags.
    
- Coefficients.
    
- Internal Cooldown.
    
- Proc Conditions.
    
- Status Effects.
    
- VFX/SFX References.
    

### Triple Resonance Data

Кожен потрійний резонанс повинен мати:

- Стабільний унікальний ID.
    
- Три стихії.
    
- Назву.
    
- Passive Modifiers.
    
- Conditions.
    
- Optional Drawback.
    
- VFX/SFX References.
    

Точні технічні ID та схема файлів мають бути узгоджені під час створення архітектури Godot.

### Загальні правила

- Не розміщувати каталог ефектів як велику жорстко прописану систему умов.
    
- Використовувати data-driven архітектуру.
    
- Зберігати числові коефіцієнти у Godot Resources або інших узгоджених конфігураційних даних.
    
- Для однакових вхідних даних Damage Calculator має повертати однаковий результат.
    
- Випадкові proc перевіряти через централізований RNG.
    
- UI не повинен самостійно обчислювати шкоду резонансів.
    

## 13. Обмеження та заборони

Заборонено без погодження:

- Додавати 22-й подвійний резонанс.
    
- Додавати 36-й потрійний резонанс.
    
- Змінювати комбінації стихій.
    
- Змінювати затверджені назви й базову поведінку.
    
- Створювати реакції з однакових стихій.
    
- Використовувати стихії вихованців як канали.
    
- Одночасно запускати дві Hero Resonance через один Reaction Focus.
    
- Ігнорувати Internal Cooldown.
    
- Обходити True Elemental Immunity звичайним Penetration/Shred.
    
- Перетворювати Triple Resonance на третій великий незалежний proc без погодження.
    

Balance v1 можна коригувати після плейтестів, не змінюючи затверджену структуру системи.

## 14. Критерії перевірки

### Каталоги

- Існує рівно 21 Double Resonance.
    
- Існує рівно 35 Triple Resonance.
    
- Усі комбінації унікальні.
    
- Порядок стихій не створює дублікати.
    
- Назви відповідають Combat Bible v1.2.
    
- Числові значення внесені у конфігурацію.
    

### Активація

- Два різні канали ГГ створюють Core Resonance.
    
- Однакові канали не створюють Core Resonance.
    
- Reaction Focus дозволяє один Hero Resonance.
    
- Три різні стихії активують правильний Triad Resonance.
    
- Pure Alignment не запускає Double/Triple Resonance.
    
- Стихія вихованця не створює реакції.
    

### Combat

- Core ICD працює.
    
- Hero ICD працює.
    
- Індивідуальні ICD працюють.
    
- Attack Speed не обходить ICD.
    
- Damage packets правильно розділяються.
    
- RES застосовується до відповідної стихії.
    
- True Immunity блокує лише відповідний пакет.
    
- DoT і stacking працюють за своїми правилами.
    
- Execute-механіки не порушують boss rules.
    
- Triple modifiers не застосовуються двічі.
    

### Save/Load та UI

- Reaction Focus правильно зберігається.
    
- Після зміни екіпірування резонанси оновлюються.
    
- Після зміни Героя резонанси оновлюються.
    
- UI відображає Core/Hero/Triad окремо.
    
- Build Preview показує зміни до підтвердження екіпірування.
    

Усі перевірки залишаються невиконаними до тестування у Godot.

## 15. Відкриті технічні та балансні питання

Не змінювати затверджені правила, але уточнити під час реалізації:

- Точний Hero Resonance Contribution Cap.
    
- Баланс усіх 21 парних резонансів.
    
- Баланс усіх 35 потрійних резонансів.
    
- Підсумкові ICD з урахуванням талантів.
    
- Порядок обчислення окремих модифікаторів при одночасному спрацюванні.
    
- Поведінка ефекту Abyssal Tide без доступного Reaction Focus.
    
- Правила лічильників multi-hit/proc після переходу до наступного ворога, якщо вони не визначені в спеціалізованих даних.
    
- Правила stacking окремих debuff і DoT, де вони не уточнені.
    
- Взаємодія резонансів із phase transitions босів.
    

Для невизначених випадків використовувати статус pending clarification замість вигаданого значення.

## 16. Пов'язані документи

- [Головні правила](../02_Core_Rules.md)
    
- [Огляд гри](../01_Game_Overview.md)
    
- [Бойова система](Combat.md)
    
- [Стихії](Elements.md)
    
- [Екіпірування](Equipment.md)
    
- [Таланти](Talents.md)
    
- [Прогресія](Progression.md)
    
- [Економіка](Economy.md)
    
- [Герої](../Characters/Heroes.md)
    
- [Вороги](../World/Enemies.md)
    

---

**Статус специфікації:** підготовлена на основі Combat System Design Bible v1.2.

**Кількість Double Resonance:** 21.

**Кількість Triple Resonance:** 35.

**Статус реалізації:** не реалізовано.

**Статус числового балансу:** Balance v1, потребує симуляцій і плейтестів.