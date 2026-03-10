# Tracking Plan — Padel Clothing Club

*Skill: analytics-tracking*
*Tools: GA4 + GTM + Meta Pixel + Conversions API (CAPI)*
*Platform: Shopify oder WooCommerce*

---

## Tracking-Stack Übersicht

| Tool | Zweck | Priorität |
|------|-------|-----------|
| **GA4** | Website-Analytics, Conversion Tracking, Attribution | Kritisch |
| **GTM** | Tag-Management (alle anderen Tags darüber) | Kritisch |
| **Meta Pixel** | Meta Ads Conversion Tracking, Audience Building | Kritisch |
| **Meta CAPI** | Server-Side Events (iOS14+ Workaround) | Kritisch |
| **Klaviyo/Mailchimp** | E-Mail Analytics, Flow-Performance | Wichtig |
| **Tolt/Rewardful** | Referral-Tracking | Wichtig |

---

## GA4 Setup

### Property-Konfiguration

**Property Name:** Padel Clothing Club — Production
**Data Stream:** Web — padelclothingclub.com
**Currency:** EUR
**Time Zone:** Europe/Berlin

**Enhanced Measurement aktivieren:**
- ✓ Page views
- ✓ Scrolls (90%)
- ✓ Outbound clicks
- ✓ Site search (falls vorhanden)
- ✓ Video engagement (falls Video auf Seite)
- ✓ File downloads

---

### GA4 Conversion Events

| Event Name | Trigger | Wert |
|-----------|---------|------|
| `purchase` | Kauf abgeschlossen | Dynamisch (Revenue) |
| `add_to_cart` | "In den Warenkorb" geklickt | Dynamisch (Produktwert) |
| `begin_checkout` | Checkout-Seite aufgerufen | Dynamisch |
| `view_item` | Produkt-Seite aufgerufen | Dynamisch |
| `generate_lead` | E-Mail Signup (Popup/Footer) | €5 (geschätzter LTV) |

**Als Conversions markieren in GA4:**
- ✓ purchase
- ✓ generate_lead

---

### GTM Setup (Tag Manager)

**Container:** Padel Clothing Club — GTM-XXXXXXX

**Tags via GTM:**
1. GA4 Configuration Tag
2. GA4 Event Tags (purchase, add_to_cart, etc.)
3. Meta Pixel Base Code
4. Meta Pixel Event Tags

**Trigger-Typen:**
- All Pages → GA4 Config, Meta Base
- DOM Ready auf /cart/add oder Shopify ATC-Event → add_to_cart
- DOM Ready auf /checkout → begin_checkout
- Custom Event "purchase" (Shopify Thank You Page) → purchase
- Form Submission (E-Mail Popup) → generate_lead

---

## Meta Pixel + CAPI Setup

### Meta Pixel Events

| Event | Trigger | Parameter |
|-------|---------|-----------|
| `PageView` | Alle Seiten | — |
| `ViewContent` | Produkt-Seite aufgerufen | content_id, content_name, value, currency |
| `AddToCart` | "In den Warenkorb" geklickt | content_id, value, currency |
| `InitiateCheckout` | Checkout gestartet | value, currency, num_items |
| `Purchase` | Kauf abgeschlossen | value, currency, content_ids |

**Beispiel: Purchase Event Parameter:**
```javascript
fbq('track', 'Purchase', {
  value: 34.99,
  currency: 'EUR',
  content_ids: ['shirt-need-money-padel-M'],
  content_type: 'product',
  num_items: 1
});
```

### Conversions API (CAPI) — kritisch für iOS14+

**Warum CAPI:** iOS14 App Tracking Transparency (ATT) blockiert Pixel-Events auf Apple-Geräten. CAPI sendet Events direkt vom Server → höhere Datenqualität, bessere Attribution.

**Setup (Shopify):**
1. Meta Business Manager → Events Manager → Datensources → Conversions API
2. Access Token generieren
3. In Shopify: Meta App → Conversions API aktivieren
4. Oder: GTM Server-Side Container (fortgeschritten)

**Minimum CAPI Events:** Purchase, AddToCart (höchste Impact)

**Event Match Quality (EMQ):** Ziel > 7.0/10
- E-Mail (hashed) mitschicken für besseres Matching
- Telefonnummer optional

---

## UTM-Tracking-Konvention

**Pflicht:** ALLE externen Links müssen UTM-Parameter haben.

**Format:**
```
utm_source=[Kanal]&utm_medium=[Medium]&utm_campaign=[Kampagne]&utm_content=[Creative-Typ]&utm_term=[Audience/Keyword]
```

### UTM-Tabelle

| Kanal | utm_source | utm_medium | utm_campaign Beispiel |
|-------|------------|------------|----------------------|
| Meta Ads TOF | meta | paid_social | TOF-padel-interests |
| Meta Ads BOF | meta | paid_social | BOF-retargeting-atc |
| E-Mail Welcome | klaviyo | email | welcome-series |
| E-Mail Post-Purchase | klaviyo | email | post-purchase |
| Instagram Organisch | instagram | organic_social | bio-link |
| TikTok Organisch | tiktok | organic_social | bio-link |
| Referral | tolt | referral | padel-friends |

**Beispiel-URLs:**
```
https://padelclothingclub.com/products/need-money-for-padel?utm_source=meta&utm_medium=paid_social&utm_campaign=TOF-padel-interests&utm_content=UGC-video

https://padelclothingclub.com/?utm_source=klaviyo&utm_medium=email&utm_campaign=welcome-series&utm_content=email-1
```

---

## GA4 Dashboard — Key Reports

### Report 1: Acquisition Overview

**Metrics:** Sessions, New Users, Conversion Rate, Revenue
**Dimension:** Session Source/Medium
**Filter:** Letzte 30 Tage
**Ziel:** Welcher Kanal bringt den besten ROI?

---

### Report 2: E-Commerce Funnel

**Funnel Steps:**
1. Session start
2. view_item
3. add_to_cart
4. begin_checkout
5. purchase

**Ziel Conversion Rate:** Session → Purchase ≥ 2%

---

### Report 3: Meta Ads Performance (Cross-Platform)

**In GA4:**
- Kanal: meta / paid_social
- Metrics: Sessions, Revenue, ROAS (Revenue / Ad Spend)

**Vergleich mit Meta Ads Manager:**
- Meta zeigt immer höheren ROAS (7-Day Click Attribution)
- GA4 zeigt konservativere, genauere Zahlen (Last-Click)
- Wahrheit liegt dazwischen — nutze 30–50% Discount auf Meta-ROAS als Faustregel

---

### Report 4: E-Mail Performance

**In Klaviyo/Mailchimp:**
- Open Rate Ziel: ≥ 35%
- Click Rate Ziel: ≥ 3%
- Conversion Rate Ziel: ≥ 2%
- Revenue per Email Ziel: ≥ €0.30

**In GA4:**
- Kanal: klaviyo / email
- Revenue attributiert zu E-Mail

---

## KPI-Dashboard (Wöchentlich)

| KPI | Ziel | Aktuell |
|-----|------|---------|
| **Gesamt-Revenue** | Wachstum +20%/Monat | — |
| **ROAS Meta (GA4)** | ≥ 2.5x | — |
| **CPP Meta** | < €15 | — |
| **Website CVR** | ≥ 2% (Session → Purchase) | — |
| **AOV** | ≥ €35 | — |
| **E-Mail Open Rate** | ≥ 35% | — |
| **E-Mail CVR** | ≥ 2% | — |
| **Checkout Completion Rate** | ≥ 70% | — |
| **Warenkorbabbruch Rate** | < 70% | — |
| **Neue Subscriber/Woche** | ≥ 50 | — |
| **Referral-Anteil am Revenue** | ≥ 15% | — |

---

## Tracking-Validierung Checkliste

### Vor Go-Live:

**GA4:**
- [ ] GA4 Property erstellt und Tracking-Code installiert
- [ ] Enhanced Measurement aktiv
- [ ] Alle 5 Conversion Events in GA4 Realtime sichtbar
- [ ] Conversions korrekt markiert
- [ ] Interne Traffic-Filter gesetzt (eigene IP ausschließen)

**Meta Pixel:**
- [ ] Pixel via GTM installiert
- [ ] Alle 5 Events in Meta Events Manager sichtbar
- [ ] Test-Purchase in Meta bestätigt
- [ ] CAPI aktiv und Events werden doppelt empfangen (Deduplizierung aktiv)
- [ ] Event Match Quality ≥ 7.0

**GTM:**
- [ ] GTM Container live
- [ ] Alle Tags in GTM Preview getestet
- [ ] Keine doppelten Tags (GA4 nur einmal feuern)

**UTM:**
- [ ] Alle Ad-Links haben UTM-Parameter
- [ ] Alle E-Mail-Links haben UTM-Parameter
- [ ] UTM-Parameter in GA4 Acquisition Reports sichtbar

---

## Shopify-spezifische Hinweise

**Für Shopify:**
- GA4 und Meta Pixel über "Online Store → Preferences" oder besser via GTM
- Klaviyo native Shopify Integration nutzen (Events automatisch)
- Meta Pixel im Shopify Meta Channel installieren (für CAPI)
- "Thank You Page" Custom Events für Purchase-Firing

**Für WooCommerce:**
- GTM4WP Plugin für GA4
- PixelYourSite oder WP Pixel Captain für Meta Pixel
- Klaviyo WooCommerce Plugin für E-Mail
