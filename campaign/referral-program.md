# Referral-Programm — Padel Clothing Club

*Skill: referral-program*
*Tool-Empfehlung: Tolt oder Rewardful*

---

## Warum Referral bei Padel Clothing Club riesig ist

Padel ist ein **Gruppen-Sport**. Spieler spielen nicht allein — sie spielen mit Freunden, in Clubs, in WhatsApp-Gruppen. Wenn ein Spieler das Shirt trägt, sehen es:
- 2–3 Spieler auf dem Court
- Die gesamte WhatsApp-Gruppe (Foto nach dem Match)
- Follower auf Instagram

Das ist **natürlicher Referral** — wir müssen ihn nur formalisieren und incentivieren.

---

## Programm-Struktur

### Mechanik: Double-Sided Incentive

| Wer | Aktion | Belohnung |
|-----|--------|-----------|
| **Bestehender Kunde (Referrer)** | Teilt seinen persönlichen Code | **15% der ersten Bestellung des Geworbenen** als Store Credit |
| **Neuer Kunde (Referred)** | Kauft mit dem Code des Referrers | **10% Rabatt** auf erste Bestellung |

**Mindesteinkauf:** €25 (verhindert Missbrauch mit Mini-Orders)
**Ablauf des Codes:** 30 Tage (verhindert Link-Sharing ohne Nutzung)
**Auszahlung (Store Credit):** Verfügbar nach Ablauf der Rückgabeperiode (30 Tage)

---

## Implementierung mit Tolt

**Warum Tolt:**
- Günstigster Einstieg (ab ~$29/Monat)
- Native Shopify-Integration
- Affiliate + Referral in einem Tool
- Einfaches Dashboard für Kunden

**Setup-Schritte:**
1. Tolt-Account erstellen (tolt.io)
2. Shopify-App installieren
3. Tracking-Script im Theme hinterlegen
4. Reward-Struktur konfigurieren (15% Credit / 10% Discount)
5. Trigger: Post-Purchase Page + E-Mail E-Mail 2 (Tag 7)
6. Referrer-Dashboard aktivieren (Kunden sehen ihre Stats)

**Alternative: Rewardful** (ebenfalls gute Shopify-Integration, stärker bei Affiliate-Programmen)

---

## Trigger-Punkte

### 1. Post-Purchase Page (Checkout Confirmation)

**Headline:** Hol dir 15% auf deine nächste Bestellung — automatisch.

**Body:**
> Dein persönlicher Code: **[CODE]**
>
> Teile ihn mit deinen Padel-Partnern. Wenn jemand mit deinem Code kauft:
> - ✓ Sie sparen 10%
> - ✓ Du bekommst 15% als Guthaben für die nächste Bestellung
>
> **[Code kopieren]** · **[Direkt auf WhatsApp teilen →]**

---

### 2. Post-Purchase E-Mail (Tag 7 — E-Mail 2)

**Betreff:** Dein Padel-Partner braucht auch eins. 🎾

**Body:**
> Du hast dir deinen Slogan gesichert.
>
> Jetzt an deine Padel-Community denken:
>
> **Dein persönlicher Referral-Code: [CODE]**
>
> → Sie sparen 10% auf ihre erste Bestellung
> → Du bekommst 15% Store Credit automatisch
>
> **[Code kopieren]**
>
> **[Direkt auf WhatsApp teilen]** · **[Per E-Mail teilen]**
>
> Bonus: Teile direkt nach dem nächsten Match — wenn alle noch das Shirt gesehen haben.

---

### 3. Account-Dashboard (für registrierte Kunden)

**Seite:** /account/referrals

**Inhalt:**
- Persönlicher Referral-Link
- Anzahl erfolgreicher Referrals
- Verdientes Store Credit
- Sharing-Buttons (WhatsApp, E-Mail, Instagram)

---

## Messaging-Framework

### Für Referrer (bestehende Kunden)

**Kern-Message:** "Bring deinen Padel-Partner mit — ihr spart beide"

**WhatsApp-Share-Text (vorgefertigt):**
> "Hey! Ich hab mir ein Shirt von Padel Clothing Club geholt — die machen lustige Padel-Shirts, wirklich gut. Mit meinem Code [CODE] kriegst du 10% Rabatt: padelclothingclub.com 🎾"

**Instagram-Story (Vorlage):**
> "Absolut notwendige Entdeckung für jeden Padel-Spieler 🎾 → padelclothingclub.com · Code [CODE] für 10%"

---

### Für Geworbene (neue Kunden)

**Headline:** Dein Padel-Freund hat dir was geschickt.

**Body:**
> [Name] hat dir einen exklusiven Code geschickt: **[CODE]**
>
> 10% auf deine erste Bestellung bei Padel Clothing Club — Streetwear, die jeder Padel-Spieler sofort versteht.
>
> → [Jetzt einlösen →]

---

## Micro-Influencer Programm (Erweiterung)

Padel-Coaches, Padel-Club-Manager und Padel-Content-Creator auf Instagram/TikTok erhalten ein **Affiliate-Programm** (identisch zur Referral-Mechanik, aber höhere Commission):

| Tier | Follower | Commission | Zusatz |
|------|----------|------------|--------|
| Nano Influencer | < 5.000 | 15% Store Credit | Kostenlose Produktmuster |
| Micro Influencer | 5.000–50.000 | 20% Store Credit | Kostenlose Muster + Promo-Kit |
| Mid Influencer | 50.000+ | 25% Cash oder Credit | Paid Collab verhandeln |

**Targeting-Strategie:**
- Suche nach #padeltennis, #padellovers, #padeladdicted auf Instagram
- Padel-Coaches auf lokalen Courts kontaktieren
- Padel-Club-Betreiber als Partner (Club-Code für Members)

**Outreach-Template:**
> "Hey [Name], ich bin von Padel Clothing Club. Wir machen Streetwear für Padel-Spieler — ich denke, das passt perfekt zu dir und deiner Community. Ich würde dir gerne ein paar Shirts schicken, damit du sie selbst siehst. Falls du magst, gibt's einen Affiliate-Code für deine Followers. Interesse?"

---

## KPIs

| Metric | Ziel (Monat 3) |
|--------|----------------|
| Referral-Rate | ≥ 10% der Käufer teilen ihren Code |
| Referral-Conversion | ≥ 25% der Referral-Links führen zu Kauf |
| Referral-Anteil am Revenue | ≥ 15% des Gesamtumsatzes |
| Durchschnittliche Referrals/Referrer | ≥ 1.5 Personen |

---

## Tracking & Analyse

- Tolt/Rewardful Dashboard: Referral Revenue, Top-Referrer
- UTM: `utm_source=referral&utm_medium=tolt&utm_campaign=padel-friends`
- GA4 Custom Dimension: Referral-Käufe vs. organisch vs. Ads
- Monatliches Review: Top-Referrer belohnen (Shoutout, Extra-Credit)
