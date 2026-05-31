# Exit Triggers — Типові тригери виходу за класами активів

Кожна рекомендація скіла ОБОВ'ЯЗКОВО включає numerical exit framework (Правило 9).

---

## Загальна структура exit framework

Будь-який exit план має 5 компонентів:

1. **Take profit (поетапний)** — продаж частинами при різних цінових/yield рівнях
2. **Stop loss (як re-evaluation trigger)** — не догматичний stop, а тригер для перегляду thesis
3. **Time stop** — через X місяців без руху thesis переоцінюється
4. **Thesis-breaking event** — конкретна macro-подія, яка ламає причину покупки
5. **Portfolio rebalance** — як позиція взаємодіє з іншими

---

## Bonds / Long-Duration Treasuries

### Take profit (для thesis "yields впадуть")
| Падіння yield | Дія |
|---|---|
| 30Y yield → 4.3% (-80 bps від 5.1%) | Продаж 30% позиції |
| 30Y yield → 3.7% (-140 bps) | Продаж ще 40% (всього 70%) |
| 30Y yield → 3.2% (-190 bps) | Продаж залишку |

### Stop / re-evaluation
| Сценарій | Дія |
|---|---|
| 30Y yield → 5.7%+ | Переоцінка: можлива докупка з кращої точки входу або переоцінка thesis |
| Time stop: 18 міс без руху | Переоцінка: тримати чи передислокувати в IEF (середня duration) |
| **Stagflation тригер:** CPI стабільно >4% AND no recession через 18 міс | Скоротити позицію 50%, перевести в LTPZ (TIPS) |

### Portfolio rebalance
| Сценарій | Дія |
|---|---|
| VOO падає -25%+, treasuries rally | Продати 50% treasuries, докупити VOO (rebalance gain) |
| Treasuries +30%+, VOO flat | Зафіксувати 30% позиції, тримати залишок |

---

## Single Equity (концентрована ставка)

### Take profit
| Сценарій | Дія |
|---|---|
| +30% від cost basis | Зафіксувати 25% позиції |
| +60% | Зафіксувати ще 25% (всього 50%) |
| +100% | Зафіксувати ще 25% (всього 75%) |
| Тримай 25% як "house money" runner |

### Stop / re-evaluation
| Сценарій | Дія |
|---|---|
| -20% від cost basis | Переоцінити thesis. Якщо thesis intact — потенційна докупка. Якщо broken — exit. |
| Earnings miss + guidance cut | Залежить від ступеня — мінімум 50% reduction |
| **Thesis-breaking подія:** наприклад, втрата ключового керівника, major regulatory issue | Повний exit |
| Time stop: 24 міс без значного руху | Переоцінка opportunity cost vs index |

---

## ETF — Index / Broad Market (VOO, CSPX, ACWI)

### Take profit
| Сценарій | Дія |
|---|---|
| **Не існує** для long-term holding | Trim лише для rebalance або значних life events |

### Re-evaluation triggers
| Сценарій | Дія |
|---|---|
| Position > 70% портфеля | Rebalance до target % |
| Major life event (купівля житла, бізнес) | Може потребувати ліквідацію |
| Кардинальні зміни життєвої ситуації | Переоцінка стратегії в цілому |

**Buy-and-hold ETF — це не trade, а структурне рішення.** Exit-фокус — лише rebalance, не "продати на максимумі".

---

## Опціони (LEAPS і коротші)

### Take profit (для LEAPS calls)
| Сценарій | Дія |
|---|---|
| +100% від премії | Продати 50% контрактів (рекуперація капіталу) |
| +200% | Продати ще 25% (всього 75%) |
| Залишок 25% тримай до або експірації або +400%+ |

### Stop / re-evaluation
| Сценарій | Дія |
|---|---|
| -50% від премії | Переоцінка: roll далі або exit |
| 30 днів до expiration AND OTM | Roll далі (паралельно з фіксацією позицій на іншому активі) або close |
| Implied volatility crush після event | Розглянути ранній exit |

**Особливість опціонів:** time decay прискорюється останні 60-90 днів. Не тримати до експірації якщо OTM/ATM.

---

## Hedge позиції (TIPS, гольд, puts)

### Take profit
| Сценарій | Дія |
|---|---|
| Hedge відіграв 80% свого "максимального" сценарію | Часткова фіксація (50%) |
| Hedged active (наприклад VOO) повернувся до нормали | Reduce hedge до core рівня (наприклад, з 15% до 5%) |

### Re-evaluation
| Сценарій | Дія |
|---|---|
| Cost of carrying hedge перевищує його очікувану виплату | Reassess: можливо exit |
| Hedge кореляція змінилася (наприклад, treasuries перестали корелювати негативно з equities в інфляційних умовах) | Substitute іншим хеджем |

---

## Венчури / Private positions

### Exit triggers (часто обмежені структурою угоди)
| Сценарій | Дія |
|---|---|
| IPO/liquidity event | Виконати pro-rata, але плануй tax відразу |
| Down round 50%+ | Re-evaluation thesis — можливо допоміжне фінансування або списання |
| Secondary marketplace doors відкриваються | Може бути єдина можливість часткового exit |
| Time stop: 5+ років без exit pathway | Переоцінити expectations |

**Венчури — найскладніший exit profile, тому sizing має бути найменший (5-10% портфеля).**

---

## Стандартні макро-тригери (cross-asset)

| Подія | Потенційний вплив |
|---|---|
| Fed announces pivot to cutting | Bond rally, equity short-term boost, dollar weakness |
| CPI surprise upside (+0.3% above expectations) | Bond sell-off, growth equity sell-off |
| Unemployment rate jumps +0.5% | Recession signal, bonds rally, growth equity dump |
| Geopolitical major event (війна, sanctions) | Flight to safety: USD, treasuries, gold |
| Major bank failure | Credit spread widening, treasury rally |
| Tax law changes (Україна) | Може потребувати ребалансування для оптимізації |

---

## Поведінкові правила для exits

1. **Pre-commit before entry.** Триггери писати ПЕРЕД покупкою. Post-hoc раціоналізація — пастка.
2. **Часткові exits — кращі за all-or-nothing.** "Продати половину" вирішує психологічну дилему "продав занадто рано / тримав занадто довго".
3. **Time stop — критичний.** Більшість поганих рішень — це **тримання позиції довше за обґрунтований термін**.
4. **Thesis-breaking ≠ price movement.** Якщо ціна впала, але thesis intact — це buying opportunity. Якщо thesis broken, але ціна ще не впала — це exit signal.
5. **Rebalance triggers — автоматизовані.** Не "коли захочеш", а конкретні пороги (наприклад, позиція виросла з 10% до 20% → rebalance).

---

## Український-специфічні exits

- **Tax-loss harvesting deadline:** мінімум за тиждень до кінця року для гарантії settlement
- **Велика прибуткова позиція в листопаді-грудні:** розглянути часткову фіксацію в наступному податковому році для розкладання податкового навантаження
- **Велика подія в УНР (вибори, реформи):** для UAH-активів — можлива потреба швидкого exit, тому ОВДП завжди мають мати достатню ліквідність на горизонт 6 місяців
