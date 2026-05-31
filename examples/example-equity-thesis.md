# Приклад: Equity Thesis — додавання NVDA до VOO-портфеля

Короткий референс — як скіл аналізує single-equity тезу.

---

## Запит (приклад)

> "Розглядаю купити NVDA на $8K на 2-3 роки. AI-тема структурна, NVDA — інфраструктурний бенефіціар. Застосуй 6 капелюхів."

(Це абстрактний приклад. Реальні числа і контекст підставляються з вашого `portfolio.md` і запиту.)

---

## Класифікація (Синій старт)

**Тип:** Long-term compounder з directional bias на конкретний сектор

**Реальне питання:** Це додавання до core (VOO) чи окрема ставка? У VOO вже є NVDA з вагою ~6%. Тобто $8K в NVDA окремо = подвоєння експозиції до NVDA в портфелі.

---

## Білий — критичні факти

**ОБОВ'ЯЗКОВО через EODHD:**
- `get_us_live_extended_quotes`: NVDA ціна, P/E, 52w range
- `get_fundamentals_data`: revenue growth, margins, FCF
- `get_earnings_trends`: forward EPS expectations
- `get_sentiment_data`: ринковий sentiment
- `get_historical_dividends`: dividend history (мінімальна для NVDA)

**Сценарний UAH розрахунок (3 роки, $8K):**
| Сценарій | USD result | Курс продажу | UAH дохід | Податок |
|---|---|---|---|---|
| Bullish (+50%) | +$4,000 | 50 | +208,560 | -47,969 |
| Base (+15%) | +$1,200 | 48 | +88,464 | -20,347 |
| Bearish (-30%) | -$2,400 | 46 | -94,176 | 0 |

**Подвоєння експозиції (приклад розрахунку):**
- Припустимо, портфель ~$80K в VOO, де NVDA становить ~6% = $4,800 already в NVDA через VOO
- Direct NVDA $8K = додатково
- Total NVDA exposure: $12,800 = ~14% портфеля
- **Concentration risk: значний**

(Реальні % треба рахувати з фактичного `portfolio.md`)

---

## Зелений — альтернативи (Directional bet → SPOT vs Options vs Futures)

| Шлях | Опис | Капітал | Підходить? |
|---|---|---|---|
| **SPOT direct** | 60 акцій NVDA | $8,000 | ✅ Якщо conviction висока |
| **UCITS Acc альтернатива** | SOXX (semiconductor ETF) UCITS Acc-варіант | $8,000 | ✅ Якщо хочеш sector exposure без single-stock risk |
| **LEAPS calls** | NVDA $140 strike Jan 2028 | $1,200-1,500 | ⚠️ Для leverage без full capital |
| **Sector ETF: SMH** | semiconductor exposure | $8,000 | ✅ Diversified semiconductor |
| **Не робити нічого** | VOO вже має NVDA 6% | $0 | ✅ Якщо conviction помірна |

**Combo варіант:**
- 60% ($4,800) → SMH UCITS Acc (диверсифікація sector)
- 25% ($2,000) → NVDA direct (concentration на лідері)
- 15% ($1,200) → LEAPS calls для acceleration

---

## Жовтий — переваги (з обґрунтуванням)

1. **AI-cycle структурний:** NVDA — інфраструктурний beneficiary, не лідер хайпу
2. **Margins і FCF:** ~50% gross margin, $X billion FCF — це не valuation bubble, це реальний кеш
3. **Moat:** CUDA ecosystem creates switching costs
4. **3-річний горизонт:** дозволяє пережити 1-2 quarter misses

---

## Чорний — ризики

1. **Concentration:** після додавання — 14% портфеля в одній компанії
2. **Valuation:** P/E на історичному premium → multiple compression risk
3. **Cyclicality:** semiconductors історично циклічні, sell-off може бути -40%
4. **Competition:** AMD, Intel, custom silicon від hyperscalers
5. **China exposure risk:** export controls, geopolitical
6. **AI-bubble тезa в макро:** якщо вона спрацює — NVDA впаде разом з усім сектором

---

## Червоний — діагностика

1. **AI FOMO:** "structural" — слово, яке часто маскує FOMO
2. **Recency bias:** NVDA виросла, тому "очевидно йде вгору"
3. **Тест:** Чи купував би ти NVDA 3 роки тому за $90? Якщо ні — звідки conviction зараз за $130?
4. **Status investing:** NVDA — "топ-1" акція, є соціальний компонент

---

## Синій фініш

**Оцінка тези:** 5-6/10. Концептуально OK, але concentration risk значний.

**Best implementation:**
- 60% ($4,800) → SMH (semiconductor diversification)
- 40% ($3,200) → NVDA direct

**Загальний effective NVDA exposure** після угоди: ~11% (vs 14% при pure NVDA), що знижує concentration без жертви upside.

**Exit triggers:**
- NVDA +60%: продати 50% позиції
- NVDA -25%: re-evaluation
- AI capex falls -20% YoY у hyperscalers: thesis break, exit
- 3 квартали підряд revenue miss: 50% reduction
- VOO -30% (broad bear): rebalance — продати 30% NVDA, докуп VOO

**Що змінило би до 7/10:**
- Correction -20% від поточної ціни (кращий вхід)
- Hyperscaler capex still rising
- Якщо вже маєш high cash position (15%+) → допустимо більший concentration
