# A/B Test Plan — Padel Clothing Club

*Skill: ab-test-setup*
*Primäre Plattform: Meta Ads + Website (Shopify/WooCommerce)*

---

## Testing-Prinzipien

1. **Eine Variable pro Test** — nie mehrere Variablen gleichzeitig ändern
2. **Statistisch valide** — 95% Konfidenz, MDE ≥ 20% bevor Entscheidung
3. **Ausreichend Volumen** — Mindestens 1.000 Impressionen pro Variante, idealerweise ≥ 50 Conversions
4. **Vorab-Hypothese** — klare Erwartung bevor der Test startet
5. **Sequenziell** — erst Test A abschließen, dann Test B starten (keine simultanen Tests auf gleicher Variable)

---

## Stichprobengröße-Kalkulation

**Formel (vereinfacht):**
```
n = (Z² × p × (1-p)) / MDE²
```
- Z = 1.96 (für 95% Konfidenz)
- p = Baseline Conversion Rate
- MDE = Minimum Detectable Effect (20%)

**Beispiel für Website CVR (Baseline 2%):**
```
n = (1.96² × 0.02 × 0.98) / 0.004² = ~4.752 Besucher pro Variante
```
→ Bei 100 Besuchern/Tag pro Variante: ~48 Tage — Traffic pushen oder Metric wechseln

**Für Meta Ads (CTR Baseline 1.5%, MDE 20%):**
→ ~8.600 Impressionen pro Variante
→ Bei €5 CPM: ca. €43 pro Variante für valides Ergebnis

---

## Priorisierte Tests (nach ROI-Impact)

### TEST 1: Creative-Typ — UGC vs. Studio

**Priorität:** ★★★★★ (höchster Impact)
**Plattform:** Meta Ads
**Funnel:** TOF

| | Variante A | Variante B |
|---|---|---|
| Creative | UGC-Style Handy-Video (authentisch) | Studio-Foto (professionell) |
| Audience | Padel-Interessen DACH | Gleich |
| Budget | €10/Tag | €10/Tag |
| Laufzeit | 14 Tage | 14 Tage |

**Hypothese:** UGC-Style Video erzeugt 30%+ höheren CTR weil es nativer im Feed wirkt.

**Primary Metric:** CTR (Click-Through Rate)
**Secondary Metrics:** CPP, ROAS
**Mindest-Impressionen:** 8.000 pro Variante

**Entscheidungsregel:**
- Winner = Variante mit statistisch signifikant höherem CTR → Budget komplett auf Winner
- Bei Gleichstand: Variante mit besserem ROAS gewinnt

---

### TEST 2: Copy-Angle — Identity vs. Gift

**Priorität:** ★★★★★
**Plattform:** Meta Ads
**Funnel:** TOF

| | Variante A | Variante B |
|---|---|---|
| Copy-Angle | Identity: "Das bin ich" | Gift: "Perfektes Padel-Geschenk" |
| Targeting | Padel-Interessen (Spieler) | Padel-Interessen (breit) |
| Creative | Gleich (Lifestyle-Foto) | Gleich |
| Budget | €10/Tag | €10/Tag |
| Laufzeit | 14 Tage | 14 Tage |

**Hypothese:** Gift-Angle erschließt eine größere Zielgruppe (Geschenkkäufer sind oft Nicht-Spieler) und senkt den CPP.

**Primary Metric:** CPP
**Secondary:** ROAS, CTR

---

### TEST 3: CTA-Text — "Shop Now" vs. "Find Your Slogan"

**Priorität:** ★★★☆☆
**Plattform:** Meta Ads
**Funnel:** TOF

| | Variante A | Variante B |
|---|---|---|
| CTA Button | "Shop Now" (Standard) | "Find Your Slogan" (Custom) |
| Alles andere | Gleich | Gleich |
| Budget | €5/Tag | €5/Tag |

**Hypothese:** Personalisierter CTA ("Find Your Slogan") erhöht CTR um 15%+ durch höhere Relevanz für die Padel-Zielgruppe.

**Primary Metric:** CTR

---

### TEST 4: Audience — Padel Interests vs. Racket Brands

**Priorität:** ★★★★☆
**Plattform:** Meta Ads
**Funnel:** TOF

| | Variante A | Variante B |
|---|---|---|
| Audience | Padel + Padel Tennis Interessen | Racket Brands (Bullpadel, Nox, Head) |
| Geo | DACH | DACH |
| Creative | Gleich | Gleich |
| Budget | €10/Tag | €10/Tag |

**Hypothese:** Racket Brand-Interesse hat höhere Kaufbereitschaft (aktive Ausrüstungs-Käufer) → niedrigerer CPP.

**Primary Metric:** CPP
**Secondary:** CPM (wie teuer ist die Audience?)

---

### TEST 5: Landing Page — Produktseite vs. Collection-Seite

**Priorität:** ★★★★☆
**Plattform:** Meta Ads → Website
**Funnel:** TOF/MOF

| | Variante A | Variante B |
|---|---|---|
| Landing Page | Direkt auf Produkt-Seite ("Need Money for Padel") | Collection-Seite (alle Designs) |
| Ad | Gleich | Gleich |
| Metric | CVR (Add-to-Cart), ROAS | CVR (Add-to-Cart), ROAS |

**Hypothese:** Direkter Produkt-Link konvertiert besser bei klarem Creative. Collection-Seite hat höheren AOV durch Cross-Sell.

**Primary Metric:** CVR + ROAS kombiniert
**Erwartetes Volumen:** ≥500 Sessions pro Variante

---

### TEST 6: Website — Exit-Intent Popup vs. Kein Popup

**Priorität:** ★★★★☆
**Plattform:** Website (Shopify A/B Test oder separate Tools wie Privy/Klaviyo)
**Funnel:** Website CVR

| | Variante A | Variante B |
|---|---|---|
| Setup | Exit-Intent Popup aktiv (10% Rabatt) | Kein Popup |
| Metric | E-Mail Capture Rate, CVR, Revenue/Session | |

**Hypothese:** Exit-Intent Popup erhöht E-Mail Capture Rate um 2%+ bei minimalem Revenue-Impact (Rabatt kompensiert durch LTV).

---

### TEST 7: Retargeting Copy — Urgency vs. Review-fokussiert

**Priorität:** ★★★☆☆
**Plattform:** Meta Ads
**Funnel:** BOF

| | Variante A | Variante B |
|---|---|---|
| Copy | Urgency: "Nur noch 3 auf Lager" | Social Proof: "87 andere haben's diese Woche geholt" |
| Audience | Add-to-Cart ohne Kauf, 7 Tage | Gleich |

**Hypothese:** Social Proof konvertiert bei wärmeren Audiences besser als Urgency (sie kennen das Produkt schon).

---

## Test-Kalender

| Woche | Aktive Tests |
|-------|-------------|
| Woche 1–2 | Test 1 (UGC vs. Studio) + Test 4 (Audience) |
| Woche 3–4 | Test 2 (Identity vs. Gift) + Test 5 (Landing Page) |
| Woche 5–6 | Test 3 (CTA) + Test 6 (Popup) |
| Woche 7–8 | Test 7 (Retargeting) + Winner skalieren |

---

## Ergebnis-Tracking

| Test | Start | Ende | Winner | CTR A | CTR B | CPP A | CPP B | Entscheidung |
|------|-------|------|--------|-------|-------|-------|-------|-------------|
| Test 1 | | | | | | | | |
| Test 2 | | | | | | | | |
| Test 3 | | | | | | | | |
| Test 4 | | | | | | | | |
| Test 5 | | | | | | | | |
| Test 6 | | | | | | | | |
| Test 7 | | | | | | | | |

---

## Häufige Fehler vermeiden

- ❌ Test zu früh stoppen (zu wenig Daten → falsche Entscheidung)
- ❌ Zu viele Tests gleichzeitig (Ergebnisse nicht isolierbar)
- ❌ Ohne Baseline testen (keine Referenz)
- ❌ Budget zwischen Varianten ungleich aufteilen
- ❌ Saisonale Effekte ignorieren (z.B. Black Friday beeinflusst alle Tests)
