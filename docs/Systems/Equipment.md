---

status: draft  
document_type: equipment-system  
source: Resources Equipment Accessories Bible v1.2  
balance_status: Balance v1  
updated: 2026-10-15  
tags:

- game-system
    
- equipment
    
- inventory
    
- progression
    
- godot
    

---

# EQUIPMENT SYSTEM — Екіпірування та аксесуари

> Специфікація 12 слотів Головного Героя, типів зброї, якостей, характеристик, Rank, Upgrade, Affixes, зачарування, інвентарю та Rebirth Seal.
> 
> Головне джерело: Resources, Equipment & Accessories Design Bible v1.2.
> 
> Механіки є затвердженим каноном. Числові коефіцієнти та діапазони характеристик належать до Balance v1.

## 1. Призначення системи

Система екіпірування забезпечує довгостроковий розвиток Головного Героя, різноманітність білдів і постійний інтерес до отримання нових предметів.

Основні принципи:

- Екіпірування впливає на атаку, захист, стихії та додаткові механіки.
    
- Якість предмета не є єдиним показником його цінності.
    
- Rank визначає головний довгостроковий розвиток сили.
    
- Upgrade забезпечує поступове покращення.
    
- Affixes дозволяють спеціалізувати білд.
    
- Аксесуари мають три гарантовані характеристики.
    
- Предмети високої якості повинні залишатися корисними після Rebirth.
    
- Непотрібний лут можна продавати, розбирати або синтезувати.
    

Предмет Rare із високим Rank, хорошими характеристиками та правильними Affixes може бути кориснішим за слабкий Legendary.

## 2. Архітектура екіпірування ГГ

Головний Герой має рівно 12 слотів.

### 2.1. Основна броня — 5 слотів

1. Шолом (Helmet).
    
2. Нагрудник (Chestplate).
    
3. Рукавички (Gloves).
    
4. Штани (Pants).
    
5. Черевики (Boots).
    

Основні завдання:

- HP.
    
- DEF.
    
- Виживання.
    
- Elemental RES.
    
- Primary Element Channel.
    

### 2.2. Озброєння — 3 слоти

1. Основна зброя (Weapon).
    
2. Щит / Defensive Off-hand (Shield).
    
3. Плащ (Cloak).
    

Ролі:

- Weapon — DPS та стиль атаки.
    
- Shield — захист і Block.
    
- Cloak — utility, cooldown, boss progression.
    

Це три різні слоти, а не можливість одночасно екіпірувати три основні види зброї.

### 2.3. Аксесуари — 4 слоти

1. Амулет (Amulet).
    
2. Перстень (Ring).
    
3. Пояс (Belt).
    
4. Сережки (Earrings).
    

Основні завдання:

- Налаштування білдів.
    
- Комбінації атакувальних і захисних характеристик.
    
- Resonance та Elemental Damage.
    
- Secondary Element Channel.
    

## 3. Елементальні канали

### Primary Element Channel

Для відкриття каналу необхідно зачарувати щонайменше 4 із 5 предметів основної броні однією стихією.

### Secondary Element Channel

Необхідно зачарувати щонайменше 3 із 4 аксесуарів однією стихією.

### Загальні правила

- У ГГ максимум два елементальні канали від екіпірування.
    
- Канали можуть мати однакові або різні стихії.
    
- Стихійна зброя може додавати власну елементальну шкоду.
    
- Зброя не створює третього каналу.
    
- Канали визначають Core Resonance або Dual Alignment.
    

Подробиці:

[Elements](Elements.md)  
[Resonances](Resonances.md)

## 4. Шість якостей предметів

|Rarity|Множник сили v1|Додаткові Affixes|
|---|---|---|
|Common|×1.00|0|
|Uncommon|×1.12|1|
|Rare|×1.28|2|
|Epic|×1.50|3|
|Legendary|×1.80|4|
|Mythic|×2.15|5 + Mythic Trait|

### 4.1. Common

- Базовий предмет.
    
- Без додаткових Affixes.
    
- Переважно ранній етап гри.
    

### 4.2. Uncommon

- Один додатковий Affix.
    
- Перший рівень спеціалізації предметів.
    

### 4.3. Rare

- Два додаткові Affixes.
    
- Важливий для раннього та середнього розвитку.
    

### 4.4. Epic

- Три додаткові Affixes.
    
- Перша якість, яка зберігається через Rebirth Seal.
    

### 4.5. Legendary

- Чотири додаткові Affixes.
    
- Високий потенціал характеристик.
    
- Не зобов'язаний мати унікальну механіку.
    

### 4.6. Mythic

- П'ять додаткових Affixes.
    
- Один Mythic Trait.
    
- Унікальна активна або пасивна властивість.
    
- Окремий помітний VFX.
    

Mythic Trait змінює або розширює поведінку гри, а не просто додає ще один звичайний Affix.

Множники Rarity належать до Balance v1.

## 5. Rank System — 0–12

Rank — головний довгостроковий множник сили спорядження.

Базовий новостворений предмет може мати Rank 0.

Основна прогресія: Rank 1–12.

Rank поділяється на чотири стадії.

### Стадія I — Rank 1–3

|Rank|Бонус сили v1|
|---|---|
|1|+12%|
|2|+18%|
|3|+26%|

Матеріали:

- Common.
    
- Uncommon.
    
- Ранні трофеї.
    

### Стадія II — Rank 4–6

|Rank|Бонус сили v1|
|---|---|
|4|+40%|
|5|+52%|
|6|+66%|

Матеріали:

- Uncommon.
    
- Rare.
    
- Регіональні компоненти.
    

### Стадія III — Rank 7–9

|Rank|Бонус сили v1|
|---|---|
|7|+90%|
|8|+108%|
|9|+128%|

Матеріали:

- Rare.
    
- Epic.
    
- Окремі Legendary-компоненти.
    

### Стадія IV — Rank 10–12

|Rank|Бонус сили v1|
|---|---|
|10|+165%|
|11|+200%|
|12|+240%|

Матеріали:

- Epic.
    
- Legendary.
    
- Mythic.
    
- Boss Cores.
    
- Компоненти Генералів.
    

### 5.1. Отримання Rank із дропа

Предмети можуть випадати з готовим Rank у межах дозволеного діапазону.

Орієнтири:

- Early Game: переважно R1–R3.
    
- Midgame: переважно R3–R6.
    
- Late Game: R7–R10.
    
- R11–R12: надзвичайно рідкісні high-end rolls.
    

Rank не повинен визначатися лише кількістю Gold.

Високі Rank блокуються доступом до відповідних матеріалів і контенту.

### 5.2. Ручне підвищення Rank

Гравець може розвивати предмет із хорошими Affixes, навіть якщо початковий Rank низький.

Правила:

- Успіх підвищення Rank — 100%.
    
- Витрати залежать від поточного Rank.
    
- Високі Rank вимагають рідкісних матеріалів.
    
- Підвищення Rank не скидає Upgrade Level.
    

Точні рецепти та ціни визначає Crafting & Forge Bible v1.2.

## 6. Upgrade Level +0–30

Upgrade — плавне підвищення сили конкретного предмета.

Діапазон: від +0 до +30.

Balance v1:

- +1.2% до базових main stats за один рівень.
    
- На +30 загальний бонус цього шару становить +36%.
    

### Етапи

**+0 → +10**

- Gold.
    
- Common / Uncommon Materials.
    

**+11 → +20**

- Більше Gold.
    
- Rare Materials.
    

**+21 → +30**

- Високі витрати.
    
- Epic / Regional Materials.
    

### Правила

- Успіх Upgrade — 100%.
    
- Upgrade не замінює Rank.
    
- Rank не обнуляє Upgrade.
    
- Rarity, Rank та Upgrade розраховуються незалежними шарами.
    
- Після звичайного Synthesis 3→1 Upgrade результату скидається до +0.
    

## 7. Формула сили предмета

Balance v1:

`FinalMainStat = RolledBase × RarityMultiplier × (1 + RankBonus) × (1 + 0.012 × UpgradeLevel)`

Де:

- RolledBase — початкове значення характеристики.
    
- RarityMultiplier — множник якості.
    
- RankBonus — бонус відповідного рангу.
    
- UpgradeLevel — рівень покращення 0–30.
    

### Важливі правила

1. Початковий roll генерується один раз.
    
2. Кожен множник застосовується один раз.
    
3. Не дублювати Rank або Rarity в min/max діапазонах і фінальному розрахунку.
    
4. Main Stats та Affixes повинні дотримуватися своїх правил масштабування.
    
5. Фінальна реалізація узгоджується з Forge та Economy.
    

## 8. Сім типів зброї

Кожна основна зброя має дві гарантовані характеристики.

Усі наведені діапазони — Balance v1 до додаткового масштабування.

### 8.1. Шипований ланцюг / Батіг

- Attack Speed: +8–18%.
    
- Skill / DoT Damage: +10–24%.
    

Стиль: швидкі атаки та proc/DoT білдів.

### 8.2. Важкий молот / Булава

- ATK: +18–35%.
    
- Boss Damage: +10–22%.
    

Стиль: сильний одиночний удар, особливо проти босів.

### 8.3. Бойова коса

- Crit DMG: +18–38%.
    
- Elemental DMG: +10–25%.
    

Стиль: критичні та стихійні burst-білди.

### 8.4. Посох окультиста

- Elemental DMG: +18–35%.
    
- Skill Damage: +12–28%.
    

Стиль: стихійні навички та активна магія.

### 8.5. Спис / Partisan

- ATK: +12–25%.
    
- Crit Chance: +6–14%.
    

Стиль: збалансований наступальний критичний білд.

### 8.6. Кинджал / Dirk

- Attack Speed: +15–30%.
    
- Crit Chance: +8–18%.
    

Стиль: максимальна швидкість та часті критичні удари.

### 8.7. Одноручний меч

- ATK: +10–22%.
    
- Attack Speed: +7–16%.
    

Стиль: універсальна зброя без різко вираженої спеціалізації.

Не додавати нові типи основної зброї без погодження.

## 9. Характеристики основної броні

Броня має дві гарантовані Main Stats.

### Шолом

- Max HP: +8–16%.
    
- Elemental RES: +5–10%.
    

Призначення: HP і захист від конкретної стихії.

### Нагрудник

- DEF: +12–24%.
    
- Max HP: +10–20%.
    

Призначення: основний захисний слот.

### Рукавички

- ATK: +6–12%.
    
- Attack Speed: +5–10%.
    

Призначення: атакувальний слот броні.

### Штани

- DEF: +9–18%.
    
- Damage Reduction: +3–7%.
    

Призначення: стабільне зниження отриманої шкоди.

### Черевики

- Max HP: +6–12%.
    
- HP Regen: +0.5–1.5%/сек.
    

Призначення: витривалість у довготривалих боях.

## 10. Щит та плащ

### Щит / Defensive Off-hand

Гарантовані Main Stats:

- DEF: +15–28%.
    
- Block Chance: +5–12%.
    

Особливості:

- Захисна спеціалізація.
    
- Доступ до Block Affixes.
    
- Звичайні offensive main stats не генеруються.
    

### Плащ

Гарантовані Main Stats:

- Cooldown Reduction: +4–10%.
    
- Boss Damage: +5–12%.
    

Особливості:

- Utility.
    
- Boss Progression.
    
- Допоміжні економічні й захисні Affixes.
    
- Без високих основних ATK/DEF rolls.
    

## 11. Аксесуари — три Main Stats

Аксесуари мають три гарантовані характеристики.

Кожна характеристика має вужчий roll band і нижчу верхню межу, ніж спеціалізовані характеристики зброї або броні.

Аксесуари рідше випадають і складніше створюються.

### 11.1. Амулет

- Elemental DMG: +9–13%.
    
- Skill Damage: +7–11%.
    
- Elemental Penetration: +3–6%.
    

### 11.2. Перстень

- Crit Chance: +5–8%.
    
- Crit DMG: +10–15%.
    
- ATK: +7–11%.
    

### 11.3. Пояс

- Max HP: +7–11%.
    
- DEF: +6–10%.
    
- Gold Drop: +5–9%.
    

### 11.4. Сережки

- Attack Speed: +6–10%.
    
- Cooldown Reduction: +4–7%.
    
- Resonance Damage: +7–11%.
    

Наявність трьох Main Stats не дозволяє аксесуарам ігнорувати свої обмеження Affix Pool.

## 12. Affix System

Affixes — випадкові додаткові характеристики предмета.

Кількість залежить від Rarity.

### 12.1. Загальні правила

- Один і той самий Affix не може згенеруватися двічі на одному предметі.
    
- Main Stat та Affix можуть мати однакову тематику, якщо такий Affix дозволений для слота.
    
- Affixes генеруються лише з дозволених пулів.
    
- Діапазон залежить від Rarity, Rank та відповідних правил балансу.
    
- Mythic Trait не вважається звичайним Affix.
    

### 12.2. Сім'ї Affixes

**Offensive**

ATK, Crit Chance, Crit DMG, Attack Speed, Basic Attack Damage, Boss Damage, Elite Damage, DoT Damage.

**Skill**

Skill Damage, Cooldown Reduction, Skill Duration, Soul Skill Power, Active Skill Crit.

**Elemental**

Elemental Damage семи стихій, Elemental Penetration, RES Shred.

**Resonance**

Resonance Damage, Double Resonance Bonus, Triple Resonance Bonus, Reaction/DoT Amplification.

**Defensive**

Max HP, DEF, Damage Reduction, HP Regen, Physical Mitigation, Elemental RES, All Elemental RES.

**Block**

Block Chance, Block Power, Reflect / Thorns.

**Economy**

Gold Drop, Item Drop, Ore Drop, Mob Material Drop, Element Crystal Drop.

**Utility**

XP Gain, Offline Gain, Healing Received, Status Duration/Resistance, Cooldown Utility.

## 13. Обмеження Affix за слотами

### Основна зброя

Дозволено:

- Offensive.
    
- Skill.
    
- Elemental.
    

Заборонено звичайні DEF, HP, Regen та Damage Reduction rolls.

### Щит

Дозволено:

- Defensive.
    
- Block.
    
- Elemental RES.
    

Заборонено звичайні Crit, Attack Speed, Boss Damage та offensive Penetration rolls.

### Плащ

Дозволено:

- Skill.
    
- Utility.
    
- Economy.
    
- Обмежені Offensive/Defensive.
    

Без high-roll базових ATK/DEF.

### Шолом, нагрудник, штани, черевики

Дозволено:

- Defensive.
    
- Elemental RES.
    
- Обмежені Utility.
    

Звичайно заборонено Attack Speed, Crit DMG та Penetration.

### Рукавички

Дозволено:

- Обмежені Offensive.
    
- Skill.
    
- Elemental.
    
- Базові defensive властивості.
    

Заборонено weapon-exclusive proc affixes.

### Аксесуари

Дозволено більшість non-exclusive Affix Families.

Обмеження:

- Вужчі rolls.
    
- Немає Shield-exclusive Affixes.
    
- Немає Weapon-proc exclusive Affixes.
    

## 14. Ексклюзивні Affixes

### Weapon-exclusive

Лише для основної зброї:

- Basic Attack Damage.
    
- On-hit DoT.
    
- Weapon Proc Chance.
    
- Execute Effects.
    

### Shield-exclusive

Лише для щитів:

- Block Chance.
    
- Block Power.
    
- Reflect / Thorns.
    

### Armor High-Roll Defense

Для броні та щита:

- Високі DEF rolls.
    
- Damage Reduction.
    
- HP Regen.
    

### Accessory-exclusive

Для аксесуарів:

- Resonance Damage.
    
- Reaction Damage.
    
- RES Shred.
    
- Penetration.
    
- Soul Skill Power.
    

### Cloak Utility

Переважно для плаща:

- Offline Gain.
    
- Utility Cooldown.
    
- Змішані Boss/Economy ефекти.
    

Не переносити ексклюзивний Affix на інший тип предмета без затвердженого правила.

## 15. Reroll, Lock та Refinement

Детальна реалізація належить до [Crafting](Crafting.md).

### 15.1. Affix Reroll

Доступний після відкриття Forge II.

Гравець може перегенерувати звичайні Affixes.

Правила:

- Від 0 до 3 заблокованих Affixes.
    
- Принаймні один звичайний Affix повинен залишатися відкритим.
    
- Заблоковані Affixes не змінюються.
    
- Нові Affixes генеруються з дозволених пулів.
    
- Main Stats не змінюються звичайним Reroll.
    
- Mythic Trait не змінюється.
    
- Фіксований Named Unique Effect не втрачається.
    

Множники вартості Balance v1:

|Locked Affixes|Cost Multiplier|
|---|---|
|0|×1|
|1|×2|
|2|×4|
|3|×8|

### 15.2. Refinement

Окрема операція Forge II.

Refinement:

- Підвищує roll_fraction.
    
- Не змінює тип характеристики.
    
- Не погіршує попередній результат.
    
- Працює в межах дозволеного min/max.
    
- Може покращувати Main Stats та допустимі звичайні Affixes.
    
- Не змінює Mythic Trait.
    
- Не змінює Named Unique Effect.
    

Reroll і Refinement повинні мати окремі дії та витрати.

## 16. Sell, Salvage та Synthesis

### Sell

Продаж предмета за Gold.

Цінність залежить від:

- Rarity.
    
- Rank.
    
- Upgrade Level.
    

### Salvage

Розбирання предмета на матеріали.

Може повертати частину ресурсів та відповідні матеріали якості предмета.

### Synthesis 3→1

Три предмети одного типу та якості перетворюються на один предмет наступної якості.

Приклад:

3 Rare Dagger → 1 Epic Dagger.

Правила:

- Однаковий slot/type.
    
- Однакова Rarity.
    
- Нові Main Stat rolls.
    
- Нові Affixes.
    
- Upgrade Level результату = +0.
    
- Старе стихійне зачарування не переноситься.
    

Rank результату:

- Випадковий Rank у діапазоні між мінімальним та максимальним Rank трьох предметів.
    
- Імовірності зважені.
    
- Значення біля середнього або медіани мають більшу вагу.
    
- Найвищі значення менш імовірні.
    
- Якщо всі три Rank однакові, результат отримує цей Rank.
    

Наприклад:

R2 + R3 + R7 → результат у діапазоні R2–R7.

Named Boss Unique не використовує цей стандартний синтез.

## 17. Mythic Traits та Named Items

### 17.1. Mythic Trait

Mythic-предмет має унікальний активний або пасивний ефект.

Його завдання — змінювати поведінку бою.

Можливі концептуальні приклади з Equipment Bible:

- Кожен десятий удар породжує ланцюгову блискавку.
    
- Meteor залишає Burning Ground.
    
- Triple Resonance отримує додатковий utility proc.
    
- Perfect Block запускає короткий захисний burst.
    

Це приклади можливих властивостей, а не остаточний каталог предметів.

### 17.2. Named Boss Unique

Окремі боси можуть мати унікальні іменні предмети.

Особливості:

- Фіксована назва.
    
- Тематичний ефект боса.
    
- Унікальний візуальний мотив.
    
- Спеціальні правила дропа.
    

### 17.3. Blueprint Ritual

Три однакові Named Unique з одним `named_unique_id` можуть використовуватися в окремому Blueprint Ritual.

Результат:

- Три предмети витрачаються.
    
- Відкривається постійне креслення Enhanced Named Item.
    
- Це не звичайний Rarity Synthesis.
    
- Відкрите креслення зберігається після Rebirth.
    

## 18. Інвентар та Auto-Salvage

Інвентар практично необмежений.

Основний QoL-інструмент — фільтрація луту.

### Фільтри

- Slot.
    
- Weapon Type.
    
- Rarity.
    
- Rank.
    
- Element.
    
- Locked / Favorite.
    
- Named / Unique.
    

### Auto-Salvage

Можна налаштувати автоматичне розбирання за:

- Rarity.
    
- Мінімальним Rank.
    

Приклад:

Автоматично розбирати Common та Uncommon нижче Rank 4.

### Захищені предмети

- Favorite / Locked ніколи не продаються, не розбираються та не синтезуються автоматично.
    
- Named Boss Unique захищені від Auto-Salvage за замовчуванням.
    
- Mythic захищені від Auto-Salvage за замовчуванням.
    

## 19. Ресурси, матеріали й сувої

### 19.1. Основні валюти

- Gold — базові покращення та витрати поточного забігу.
    
- Crystals — спеціальні операції й метапрогресія.
    
- Souls — постійна прогресія.
    
- Talent Points — run-based дерево талантів.
    

### 19.2. Матеріали

Шість якостей матеріалів:

Common → Uncommon → Rare → Epic → Legendary → Mythic.

Категорії:

- Ore.
    
- Metal.
    
- Mob Trophies.
    
- Regional Components.
    
- Boss Materials.
    
- Element Crystals.
    

Element Crystals існують окремо для всіх семи стихій.

Вони не тотожні загальній валюті Crystals.

### 19.3. Сувої

Два основні типи:

**Timed Buff Scroll**

Тимчасові бойові, економічні або захисні бонуси.

Одночасно максимум три категорії:

- Combat.
    
- Economy / Loot.
    
- Defense / Utility.
    

По одному активному сувою кожної категорії.

**Stored Farm Scroll**

Видає нагороду, еквівалентну певному часу стабільного фарму.

Balance v1:

|Rarity|Farm Equivalent|
|---|---|
|Common|1 хв|
|Uncommon|3 хв|
|Rare|10 хв|
|Epic|1 год|
|Legendary|6 год|
|Mythic|24 год|

Розрахунок ведеться від Base Farm Rate, а не тимчасово розігнаного DPS.

Сувої:

- Не виготовляються зі звичайної сировини.
    
- Отримуються з дропа та нагород.
    
- Покращуються синтезом трьох однакових сувоїв одного типу й якості.
    
- Зберігаються після Rebirth.
    

## 20. Rebirth Seal

Rebirth відкривається після першого проходження Башти 01-I.

### 20.1. Common / Uncommon / Rare

Повністю зникають після Rebirth.

### 20.2. Epic / Legendary / Mythic

Зберігаються.

Збережений предмет:

- Зберігає Rank.
    
- Зберігає Upgrade Level.
    
- Зберігає Affixes.
    
- Зберігає Element Enchant.
    
- Тимчасово отримує Rebirth Seal.
    
- Повертає силу в міру проходження поверхів.
    

### 20.3. Значення Rebirth Seal — Balance v1

|Rarity|Початкова сила|Орієнтир відновлення|
|---|---|---|
|Epic|≈30%|Поверх 80|
|Legendary|≈25%|Поверх 120|
|Mythic|≈20%|Поверх 141|

Це початкові балансні значення, а не гарантовано фінальні коефіцієнти.

### 20.4. Named Boss Unique

Іменні предмети якості Epic+ зберігаються через Rebirth Seal.

### 20.5. Інші ресурси

- Gold — скидається.
    
- Crystals — залишаються.
    
- Souls — залишаються згідно з правилами обліку.
    
- Сувої — залишаються.
    
- Element Crystals — залишаються.
    

Основний принцип: Rebirth не повинен знищувати найцінніший довгостроковий лут, але й не повинен дозволяти повністю пропустити ранній розвиток нового забігу.

## 21. Захисна система та роль рівня ГГ

Основні характеристики виживання:

- Max HP.
    
- DEF.
    
- Physical Mitigation.
    
- Сім Elemental RES.
    
- Block.
    
- HP Regen.
    

Базове зростання HP/ATK/DEF забезпечує рівень ГГ у поточному забігу.

Екіпірування спеціалізує білд:

- Tank.
    
- Glass Cannon.
    
- Elemental Resist Build.
    
- Block Build.
    
- Hybrid Build.
    

Рекомендований cap звичайного Elemental RES для персонажа — 75% (Balance v1).

Для розрахунку шкоди використовувати Combat Bible, а не спрощену універсальну формулу `RawDamage × (1 − RES)`.

True Elemental Immunity є окремою механікою противників, а не результатом набору 100% RES спорядженням.

## 22. Технічна реалізація в Godot

### 22.1. ItemData

Предмет повинен мати структуровані дані.

Основні поля:

- `item_id`
    
- `slot`
    
- `weapon_type`
    
- `rarity`
    
- `rank`
    
- `upgrade_level`
    
- `element`
    
- `main_stats`
    
- `affixes`
    
- `mythic_trait_id`
    
- `named_unique_id`
    
- `rebirth_seal_state`
    
- `favorite_locked`
    

### 22.2. Affix Data

Кожен Affix має:

- Унікальний ID.
    
- Family.
    
- Allowed Slots.
    
- Forbidden Slots.
    
- Min/Max Roll Curve.
    
- Rarity Floor.
    
- Rank Scaling.
    
- Roll Fraction.
    
- Exclusive Tag.
    

Додатково зберігати:

- Affix Lock Flags.
    
- Refinement Progress.
    

### 22.3. Архітектурні правила

- Data-driven предмети.
    
- Баланс у Resources/JSON.
    
- UI не визначає самостійно бойову силу.
    
- Немає окремого великого if/else для кожного предмета.
    
- Дані інвентарю повинні зберігатися через Save/Load.
    
- Rebirth застосовує різні правила до різної Rarity.
    
- Усі Item ID повинні бути стабільними.
    
- Обчислення характеристик не повинно повторно застосовувати ті самі множники.
    

## 23. Порядок реалізації

1. Rarity / Rank / Slot / WeaponType / Element enums та data.
    
2. ItemData.
    
3. Генерація Main Stat Rolls.
    
4. Незалежні Rarity, Rank та Upgrade modifiers.
    
5. Affix Families і Allowed/Forbidden Slot Rules.
    
6. Inventory, Filters, Favorite/Lock.
    
7. Auto-Salvage.
    
8. Sell, Salvage, Synthesis.
    
9. Forge Reroll / Lock / Refinement.
    
10. Ore / Metal / Materials.
    
11. Element Crystals.
    
12. Scroll Inventory.
    
13. Mythic Traits та Named Boss Unique.
    
14. Rebirth Seal.
    
15. Save/Load і автоматизовані тести.
    

## 24. Заборони та обмеження

Без погодження заборонено:

- Змінювати кількість слотів ГГ.
    
- Додавати нові якості предметів.
    
- Змінювати структуру Rank 0–12.
    
- Перевищувати Upgrade +30.
    
- Додавати восьмий тип основної зброї.
    
- Давати аксесуарам неконтрольовані високі stat rolls.
    
- Генерувати недозволені Affixes.
    
- Автоматично знищувати Favorite/Locked предмети.
    
- Дозволяти стандартному Reroll змінювати Mythic Trait.
    
- Скидати Epic+ предмети при Rebirth.
    
- Створювати Element Channel зі щита чи плаща.
    
- Змішувати Element Crystals із валютою Crystals.
    
- Змінювати затверджену логіку спорядження під виглядом балансування.
    

## 25. Критерії перевірки

### Equipment

- Рівно 12 слотів ГГ.
    
- Рівно 7 типів основної зброї.
    
- Шість якостей.
    
- Коректні Main Stats для кожного слота.
    
- Три гарантовані Main Stats у аксесуарів.
    
- Element Channels працюють за правилами 4/5 і 3/4.
    

### Item Progression

- Rank 0–12.
    
- Upgrade +0–30.
    
- Успіх підвищення Rank і Upgrade 100%.
    
- Rank не скидає Upgrade.
    
- Rarity / Rank / Upgrade застосовуються один раз.
    
- Правильні Affix Counts.
    

### Affixes / Forge

- Affixes належать дозволеним сім'ям.
    
- Ексклюзивні Affixes не з'являються на недозволених слотах.
    
- Неможливо отримати два однакові Affixes.
    
- Maximum Locked Affixes = 3.
    
- Reroll не змінює Main Stats.
    
- Refinement не погіршує значення.
    
- Mythic Trait захищений.
    

### Inventory / Rebirth

- Favorite/Locked предмети захищені.
    
- Auto-Salvage працює за налаштованими умовами.
    
- Common–Rare зникають після Rebirth.
    
- Epic–Mythic залишаються.
    
- Rebirth Seal відновлює силу за прогресом.
    
- Save/Load зберігає Rank, Upgrade, Affixes і Enchant.
    
- Сувої та постійні ресурси не скидаються.
    

Статус перевірок: не виконано до тестування в Godot.

## 26. Відкриті питання

Наведені параметри потребують плейтестів і балансної перевірки:

- Rarity Multipliers.
    
- Rank Bonuses.
    
- Upgrade Scaling.
    
- Діапазони Main Stat Rolls.
    
- Affix Roll Curves.
    
- Drop Rank Bands.
    
- Фінальні ціни високих Rank.
    
- Частота випадіння аксесуарів.
    
- Точні значення Rebirth Seal.
    
- Баланс Mythic Traits.
    
- Економіка Sell / Salvage / Synthesis.
    

Не змінювати структуру системи для коригування тестових чисел.

## 27. Пов'язані документи

- [Головні правила](../02_Core_Rules.md)
    
- [Огляд гри](../01_Game_Overview.md)
    
- [Бойова система](Combat.md)
    
- [Стихії](Elements.md)
    
- [Резонанси](Resonances.md)
    
- [Крафт та Кузня](Crafting.md)
    
- [Економіка](Economy.md)
    
- [Прогресія](Progression.md)
    
- [Герої](../Characters/Heroes.md)
    
- [Вороги та лут](../World/Enemies.md)
    

---

**Статус документа:** специфікація підготовлена з Resources, Equipment & Accessories Bible v1.2.

**Статус реалізації:** не реалізовано.

**Статус балансу:** Balance v1, потребує симуляцій і плейтестів.

**Пріоритет:** Equipment Bible визначає предмети, характеристики та Affix Pools; Crafting & Forge Bible — рецепти й кузнярські операції; Combat Bible — розрахунки шкоди та резистів.