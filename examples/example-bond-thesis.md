# Приклад: Аналіз 30Y Treasuries (теза AI bubble + Fed cuts)

Це **референсний приклад** повного аналізу. Приклад тези: купівля 30Y облігацій США під припущення про AI bubble crash + Fed cuts, горизонт 2-4 роки, розмір $10-15K. Цей приклад навмисно деперсоналізований — числа можна замінити під конкретний кейс.

---

## Класифікація (Синій старт)

**Тип тези:** Directional bet з характеристиками hedge

**Hedge Reframing Test:** Припустимо, інвестор має портфель VOO + cash. Treasuries при AI-bubble crash дають негативну кореляцію з VOO. Отже, це **одночасно directional bet ТА partial hedge**. Обидва кадри треба розглянути.

**Параметри прикладу:**
- Канал: Interactive Brokers
- Розмір: $12.5K (середнє з $10-15K, обрано для розрахунків)
- Горизонт: адаптивний (trigger-based exit)
- W-8BEN: ✅ (0% withholding на купони treasuries)
- UCITS: ✅ доступний
- Існуючий портфель: VOO + cash

---

## Білий капелюх — ключові факти

**Макро (травень 2026):**
- 30Y Treasury yield: 5.12%
- CPI на 3-річному максимумі
- Курс НБУ USD: 44.07 грн

**Інструменти-кандидати:**
| ETF | Поточна ціна | Падіння від 52w High |
|---|---|---|
| TLT (20+ yr) | $83.66 | -9.3% |
| EDV (25+ yr extended) | $61.48 | -13.8% |
| ZROZ (zero coupon) | $60.24 | -15.4% |

**Сценарний аналіз (на $12,500, 24 місяці):**

| Сценарій | yield change | USD result | НБУ ставка | UAH результат | Податок 23% |
|---|---|---|---|---|---|
| Bullish | -150 bps до 3.6% | +29% | 48 | +278,793 грн | -64,122 грн |
| Base | flat 5.1% | +4% (купони) | 47 | +75,213 грн (примарний) | -17,299 грн |
| Bearish | +100 bps до 6.1% | -14% | 46 | -56,455 грн | 0 |

---

## Зелений капелюх — 3 шляхи реалізації

### Шлях A: Single 30Y Treasury Bond через IB
- US Treasury 4.625% 02/15/2055
- 12-13 bonds × $1000 face × ~95% = $12,000-12,500
- Купон 2 рази/рік = **2 податкові події** + 1 при продажу
- 0% US withholding на купони (для нерезидентів)
- Можливість тримати до погашення = гарантія номіналу

### Шлях B: UCITS Acc ETF
- DTLA (iShares $ Treasury 20+yr UCITS USD Acc), TER 0.07%
- VDTY (Vanguard альтернатива), TER 0.05%
- **0 розподілів** → 0 проміжних податкових подій
- Доступ через IB ✅ (для прикладу припускаємо, що інвестор має доступ до європейських UCITS через IB)
- Адміністративно — найпростіший

### Шлях C: LEAPS Calls на TLT
- TLT call strike $85, exp Jan 2028
- Премія ~$600/контракт = контроль $8,366 TLT
- Капітал під ризиком: $1,200-3,000
- Решта в SGOV (5% yield)
- High leverage, time decay risk

**Recommended combo:** 70% UCITS Acc (DTLA/VDTY) + 10% LTPZ (TIPS hedge) + 10% LEAPS + 10% SGOV reserve

---

## Жовтий — обґрунтовані переваги

1. **Asymmetric risk/reward:** downside -14%, upside +29% → ratio 1:2
2. **Точка входу:** yield 5.12% історично високий, mean reversion на стороні тези
3. **Hedge VOO:** негативна кореляція в crisis scenarios (2008: VOO -37%, TLT +33%)
4. **UCITS Acc — потрійна перевага для українця:** 0 розподілів, 0 US withholding, чистий cost basis
5. **Девальваційний хедж:** навіть flat USD дає +5-10% UAH через очікувану девальвацію
6. **Single bond опція:** психологічна якірна — гарантія номіналу до 2055

---

## Чорний — ризики

1. **Stagflation сценарій:** CPI 4%+ AND no recession → Fed cannot cut → bonds tank разом з equity. У 2022 VOO -19%, TLT -31%.
   - **Mitigation:** 10% позиції в LTPZ
2. **Timing risk:** "bubble лусне" — невизначений timeline. Markets can stay irrational довше за твою терпеливість.
   - **Mitigation:** UCITS Acc + single bond не страждають від time decay (на відміну від опціонів)
3. **Yield може зростати далі:** до 5.7-6%, TLT -10-15%.
   - **Mitigation:** поетапний вхід (33% × 3 траншами)
4. **Український парадокс:** flat USD + девальвація = податок на "примарний" дохід
5. **AI thesis може бути хибною:** revenue реальна, це може бути structural shift, не bubble
   - **Mitigation:** limit 15% портфеля

---

## Червоний — емоційна діагностика

1. **Contrarian status reward:** "я бачу bubble" — статусна позиція
2. **Hedge rationalization:** перейменування directional bet як хедж для виправдання
3. **Тест:** Чи зробив би цю інвестицію якби AI акції впали 20% за тиждень? Якщо ні — це FOMO для bonds
4. **"Адаптивний горизонт" як пастка:** може легально обґрунтувати будь-яке post-hoc рішення → **антидот: pre-committed triggers**

---

## Синій фініш — рекомендація

**Оцінка тези:** 6/10 standalone, 7/10 as hedge

**Best implementation для цього профілю:**

**Структура $12,500:**
- 80% ($10,000) → **DTLA або VDTY** (UCITS Acc 20+yr)
- 10% ($1,250) → **LTPZ** (TIPS stagflation hedge)
- 10% ($1,250) → **TLT LEAPS Jan 2028 strike $85** (accelerator)

**Поетапний вхід:**
- Зараз: 40% ($5,000)
- При yield 5.4%+: ще 30% ($3,750)
- При yield 5.7%+ OR Fed pivot signals: 30% ($3,750)

**Exit Triggers:**
| Подія | Дія |
|---|---|
| 30Y yield → 4.3% | Продаж 30% |
| 30Y yield → 3.7% | Продаж ще 40% |
| 30Y yield → 3.2% | Продаж залишку |
| VOO -25%+ AND treasuries rally | Продаж 50%, докуп VOO |
| 30Y yield → 5.7%+ | Переоцінка thesis |
| CPI >4% + no recession через 18 міс | Скоротити 50%, перевести в LTPZ |
| 18 міс без руху, yield 4.5-5.2% | Переоцінка |

---

## Що змінило би оцінку

**До 8/10:**
- Yield 5.5%+ (кращий вхід)
- CPI стабільно знижується
- Fed уже signaled pivot
- Користувач has heavy AI-equity exposure → real hedge need

**До 3/10:**
- Yield <4.5% (rally trade)
- CPI прискорюється
- Lump sum entry одним траншем
