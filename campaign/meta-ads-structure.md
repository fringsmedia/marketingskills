# Meta Ads Kampagnen-Struktur — Padel Clothing Club

*Skill: paid-ads*
*Platform: Meta (Facebook + Instagram)*
*Ziel: Purchase (D2C E-Commerce)*

---

## Account Setup

**Business Manager:** Padel Clothing Club
**Ad Account Currency:** EUR
**Pixel:** Padel Clothing Club Pixel (mit Conversions API / CAPI)
**Katalog:** Produktkatalog aus Shopify/WooCommerce (für Dynamic Product Ads)

**Naming Convention:**
```
[Platform]_[Objective]_[Audience]_[Creative-Typ]_[Datum]

Beispiele:
META_CONV_TOF-Padel-Interests_UGC-Video_2026Q1
META_CONV_BOF-ATC-Retargeting_DPA_2026Q1
META_CONV_MOF-WebsiteVisitors_StaticSlogan_2026Q1
```

---

## Kampagnen-Übersicht

| Campaign | Objective | Funnel | Budget-Anteil |
|----------|-----------|--------|---------------|
| Campaign 1: Cold Traffic | Conversions (Purchase) | TOF | 60% |
| Campaign 2: Warm Traffic | Conversions (Purchase) | MOF | 15% |
| Campaign 3: Retargeting | Conversions (Purchase) | BOF | 25% |

**Empfohlenes Startbudget:** €30–50/Tag gesamt (erste 4 Wochen Testing)
**Skalierungs-Budget:** Nach Winner-Identifikation 20–30% Erhöhung alle 3–5 Tage

---

## Campaign 1: Cold Traffic (TOF)

**Campaign Name:** META_CONV_TOF_Padel-Community_2026Q1
**Objective:** Conversions → Purchase
**Bid Strategy:** Cost Cap (Ziel: €12 CPP) oder zunächst Lowest Cost für Daten

### Ad Set 1A — Padel Interests (DACH)

**Name:** META_CONV_TOF_Padel-Interests_DACH
**Budget:** €10/Tag
**Geo:** Deutschland, Österreich, Schweiz
**Alter:** 20–45
**Geschlecht:** Alle

**Interessen (layered — ODER-Verknüpfung):**
- Padel Tennis
- Padel
- World Padel Tour
- Bullpadel (Marke)
- Nox (Marke)
- Head Padel
- Babolat
- Tennis (broad fallback)

**Verhalten:** Online-Käufer

**Placements:** Automatic Placements (Meta optimiert zwischen Feed, Stories, Reels)

**Ausschlüsse:**
- Bestehende Kunden (Custom Audience: Käufer letzte 365 Tage)
- E-Mail-Liste (bereits subscribed)

---

### Ad Set 1B — Padel Interests (Südeuropa + Nordics)

**Name:** META_CONV_TOF_Padel-Interests_International
**Budget:** €10/Tag
**Geo:** Spanien, Schweden, Niederlande, Belgien
**Alter:** 20–45
**Sprache der Ads:** Englisch (internationale Slogans funktionieren universell)

**Interessen:** (gleich wie 1A)

**Hinweis:** Spanien = weltweit größter Padel-Markt. Schweden = am schnellsten wachsend pro Kopf.

---

### Ad Set 1C — Lookalike 1% (Käufer)

**Name:** META_CONV_TOF_LAL1pct-Kaeufer_DACH
**Budget:** €10/Tag
**Geo:** DACH
**Audience:** Lookalike 1% basierend auf Custom Audience "Alle Käufer letzte 180 Tage"

*Hinweis: Sobald ≥100 Käufer im Pixel, diese Audience aktivieren. Vorher Ad Set 1D nutzen.*

---

### Ad Set 1D — Lookalike 1% (Website-Besucher) [Starter]

**Name:** META_CONV_TOF_LAL1pct-WebVisitors_DACH
**Budget:** €10/Tag
**Geo:** DACH
**Audience:** Lookalike 1% basierend auf Website-Besucher letzte 90 Tage

*Dieser Ad Set läuft während der Anfangsphase (bevor genug Käufer-Daten vorhanden sind).*

---

## Campaign 2: Warm Traffic (MOF)

**Campaign Name:** META_CONV_MOF_WarmAudiences_2026Q1
**Objective:** Conversions → Purchase
**Bid Strategy:** Lowest Cost

### Ad Set 2A — Website-Besucher (kein Kauf)

**Name:** META_CONV_MOF_WebVisitors30d
**Budget:** €5/Tag
**Audience:** Custom Audience — Website-Besucher letzte 30 Tage
**Ausschlüsse:** Käufer letzte 30 Tage

**Message-Anpassung:** Mehr Social Proof, FAQ-Antworten, Reviews

---

### Ad Set 2B — Video-Viewer 50%+

**Name:** META_CONV_MOF_VideoViewers50pct
**Budget:** €5/Tag
**Audience:** Custom Audience — Personen die 50%+ eines Videos angeschaut haben
**Ausschlüsse:** Käufer

**Message-Anpassung:** "Gefiel dir unser Video? Hier ist dein Shirt." → direkter Produkt-Link

---

## Campaign 3: Retargeting (BOF)

**Campaign Name:** META_CONV_BOF_Retargeting_2026Q1
**Objective:** Conversions → Purchase
**Bid Strategy:** Cost Cap (aggressiver als TOF, bis €20 CPP OK da wärmere Audience)

### Ad Set 3A — Add-to-Cart ohne Kauf (Hot)

**Name:** META_CONV_BOF_ATC-NoPurchase_7d
**Budget:** €8/Tag
**Audience:** Custom Audience — AddToCart Event, letzte 7 Tage
**Ausschlüsse:** Purchase Event letzte 7 Tage

**Message:** Urgency + Objection-Handling + kleiner Anreiz

**Ad Format:** Dynamic Product Ads (zeigt exakt das Produkt das sie angeschaut/in den Warenkorb gelegt haben)

---

### Ad Set 3B — Produktseiten-Viewer (Warm)

**Name:** META_CONV_BOF_ProductViewers_14d
**Budget:** €5/Tag
**Audience:** Custom Audience — ViewContent Event, letzte 14 Tage
**Ausschlüsse:** AddToCart + Purchase letzte 14 Tage

**Message:** Social Proof + "Andere aus deiner Region tragen's schon"

---

## Kampagnen-Einstellungen (Universell)

**Conversion Window:** 7-Day Click, 1-Day View
**Attribution:** Data-Driven (oder 7d click wenn nicht genug Daten)
**Optimierung:** Purchase (nicht ATC oder View Content)
**Delivery:** Standard (nicht Accelerated)

---

## Pre-Launch Checklist

- [ ] Meta Pixel installiert und getestet (alle 4 Events feuern korrekt)
- [ ] Conversions API (CAPI) aktiv (kritisch für iOS14+)
- [ ] Produktkatalog verbunden und alle Produkte sichtbar
- [ ] Custom Audiences erstellt (Website-Besucher, Käufer, ATC)
- [ ] Lookalike Audiences erstellt
- [ ] UTM-Parameter für alle Ads gesetzt
- [ ] Landing Pages mobile-optimiert und schnell (<3 Sek.)
- [ ] Alle Events in Meta Events Manager bestätigt
- [ ] Test Purchase durchgeführt und in Meta sichtbar

---

## Optimierungs-Regeln (nach Woche 1–2)

**Wenn CPP > €20:**
1. Prüfe Landing Page Conversion Rate (GA4)
2. Teste neue Creative-Angles
3. Erweitere Audience (zu narrow?)

**Wenn CTR < 1% (TOF):**
- Creative refresh — teste neue Hooks
- Überprüfe Audience-Fit

**Wenn ROAS < 2.0:**
1. Prüfe AOV — Bundle-Angebote pushen?
2. Erhöhe BOF-Budget (wärmere Audiences konvertieren besser)
3. E-Mail Sequence optimieren (Post-Click Retention)

**Winner skalieren:**
- Identifiziere Ad Sets mit ROAS > 3.0 nach Woche 2
- Erhöhe Budget 20–30% alle 3–5 Tage
- Dupliziere winning Ad Sets mit neuen Creatives

---

## Reporting-Dashboard (Wöchentlich)

| Metric | Ziel | Woche 1 | Woche 2 | Woche 3 | Woche 4 |
|--------|------|---------|---------|---------|---------|
| ROAS | ≥ 2.5x | | | | |
| CPP | < €15 | | | | |
| CTR | > 1.5% | | | | |
| CPM | < €12 | | | | |
| Frequency | < 3.0 | | | | |
| Spend | On Budget | | | | |
