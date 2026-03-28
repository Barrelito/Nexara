# AI-kurs Remake — Designspec
**Datum:** 2026-03-28
**Projekt:** Nexara / ai-kurs.html
**Syfte:** Höja innehållskvaliteten på AI-kurssidan så att den ger första linjens chefer mer än de själva hade kunnat lista ut genom att skapa ett konto på ChatGPT.

---

## Bakgrund och syfte

Sidan är en gratis e-postkurs i 6 veckor riktad till första linjens chefer. Nexara använder den för positionering — inte för att ta betalt. Kursen ska ge chefer konkret nytta direkt, och leda dem vidare till Nexara som avsändare.

**Kärninsikt:** Kursen ska organiseras kring problem chefer känner igen, inte kring verktyg. "Förbereda ett svårt medarbetarsamtal" är ett starkare ingångsvärde än "lär dig ChatGPT".

---

## Kursstruktur

### Vecka 0 — Innan du börjar (uppdaterad)
Behåll nuvarande struktur med GDPR/säkerhetsregler. Lägg till en viktig distinktion som saknas idag:

- **Betalversioner** (ChatGPT Plus, Copilot via M365-licens) tränar inte på din data — du kan arbeta friare
- **Gratisversionerna** kan använda din input för träning — var mer försiktig
- Ge chefen ett konkret val, inte bara varningar

### Vecka 1 — Förbereda svåra samtal
**Situation:** Du har ett samtal imorgon med en medarbetare som underpresterar. Du har gått igenom det hundra gånger i huvudet och vet ändå inte hur du ska börja.

**Insikt:** AI kan rollspela som din medarbetare så du övar samtalet i förväg — inte bara skriva manus.

**Promptar:**
- `"Jag ska ta upp med en medarbetare att hen ofta missar deadlines. Vi har pratat om det en gång tidigare. Hjälp mig formulera en öppning som är direkt men inte anklagande."`
- `"Rollspela nu som en defensiv medarbetare. Jag övar på att hålla mig saklig när hen hittar ursäkter."`
- `"Ge mig tre sätt att avsluta samtalet konstruktivt — med tydliga nästa steg och utan att lämna dålig stämning."`

**Uppgift:** Förbered ett riktigt samtal du har den här veckan med AI-stöd.

### Vecka 2 — Möten som tar för lång tid
**Situation:** Du leder tre möten i veckan. De drar ut på tiden, folk vet inte vad som beslutades, och du skriver protokoll dagen efter av minnet.

**Insikt:** Mötesproblematiken är egentligen tre problem — förberedelse, genomförande, uppföljning. AI hjälper med alla tre.

**Promptar:**
- Före: `"Skapa en agenda för ett 45-minuters statusmöte. Vi har tre projekt igång och ska fatta ett prioriteringsbeslut."`
- Under: Starta Teams-transkription (Microsoft 365)
- Efter: `"Här är transkriptet. Sammanfatta: 1) Beslut som fattades 2) Åtgärdspunkter med ansvarig och deadline 3) Frågor som hänger kvar"`

**Verktyg:** Microsoft Teams (transkription). Kräver Microsoft 365-licens.

**Uppgift:** Kör hela kedjan — agenda, transkription, protokoll — på ett riktigt möte.

### Vecka 3 — Rapportera uppåt snabbare
**Situation:** Du ska skriva månadsrapport till din chef igen. Det är inte svårt — men det tar alltid en timme att komma igång och hitta rätt form.

**Insikt:** Rapporter till ledningen har ett oskrivet format — kort, strukturerat, fokus på avvikelser och beslutspunkter. AI känner det formatet.

**Promptar:**
- `"Skriv en månadsrapport för mitt team. Vi levererade X i tid, hade problem med Y, och fokuserar på Z nästa period. Max en A4-sida, strukturerat."`
- `"Jag ska presentera ett förslag för ledningsgruppen om att [X]. Hjälp mig strukturera argumenten så att en chef utan detaljkunskap förstår och kan fatta beslut."`
- `"Gör texten kortare — behåll bara det som kräver ett beslut eller en åtgärd."`

**Uppgift:** Skriv nästa månadsrapport eller statusuppdatering med AI på under 15 minuter.

### Vecka 4 — Kommunikation som fastnar
**Situation:** Det finns mail i din utkorgsmapp som legat där i dagar. Inte för att du glömt dem — utan för att de är svåra att skriva.

**Insikt:** AI är bäst på just de mail som är svårast — när tonen måste vara exakt rätt. Inte "skriv ett mail", utan "hjälp mig säga detta på ett sätt som inte skapar konflikt."

**Promptar:**
- `"Jag behöver meddela en medarbetare att hen inte fick den interna tjänst de sökte. Ton: ärlig och respektfull, med fokus framåt. Skriv ett utkast."`
- `"Jag behöver adressera skriftligt att en medarbetare upprepade gånger lämnar in arbete för sent. Professionellt men tydligt — det ska kunna dokumenteras."`
- `"Gör budskapet kortare men lika tydligt. Ta bort allt som mjukar upp utan att tillföra något."`

**Uppgift:** Välj ett mail du skjutit upp. Skriv och skicka det med AI-hjälp idag.

### Vecka 5 — Planera och delegera
**Situation:** Du vet vad teamet ska leverera — men det är svårt att formulera uppdraget så att någon annan faktiskt kan ta det och köra. Det slutar med att du gör det själv.

**Insikt:** Dålig delegering beror nästan alltid på en otydlig uppdragsbeskrivning. AI hjälper dig skriva den tydligt på tre minuter.

**Promptar:**
- `"Jag ska delegera ansvaret för [uppgift] till en medarbetare. Skriv en uppdragsbeskrivning med: mål, resurser, befogenheter och förväntad leverans."`
- `"Mitt team har dessa uppgifter nästa kvartal: [lista]. Hjälp mig prioritera dem efter påverkan och insats."`
- `"Skriv en kort veckoplan för teamet baserat på prioriteringarna ovan — så att alla vet vad som gäller måndag morgon."`

**Uppgift:** Delegera en uppgift du normalt hade behållit själv — med en AI-skriven uppdragsbeskrivning.

### Vecka 6 — Bygg din AI-rutin (förstärkt)
**Situation:** Du har provat verktygen. Några fastnade, andra glömdes bort. Nu handlar det om att bygga in det som faktiskt fungerar.

**Insikt:** Tre enkla vanor slår tio verktyg du använder ibland. Men först: hitta dina egna AI-möjligheter med ett konkret ramverk.

**Ramverk — AI-vänliga uppgifter (5 kriterier):**
En uppgift är AI-vänlig om den:
1. Återkommer varje vecka eller månad
2. Följer ungefär samma struktur varje gång
3. Innehåller text, siffror eller informationshantering
4. Tar tid men kräver inte kreativ problemlösning
5. Har tydlig input och förväntad output

**Promptar:**
- `"Baserat på dessa kriterier — här är mina vanligaste arbetsuppgifter: [lista]. Vilka tre passar bäst för AI-stöd?"`
- `"Skriv tre konkreta AI-vanor jag kan börja med nästa måndag, baserat på de uppgifterna."`

**Avslutning:** CTA till Nexara — "Vill du gå djupare med AI i din organisation? Det är vad vi gör på Nexara."

---

## Förändringar i hero-sektionen

Lägg till konkreta resultatmått för att stärka värdeerbjudandet:
- "20–40% snabbare på text och rapporter"
- "Möten som avslutas med ett klart protokoll på 5 minuter"
- "Delegera tydligare — utan att behöva göra det själv ändå"

---

## Nexara-koppling

- Logga/länk till nexara.se i navigeringen och footern
- Vecka 6 avslutas med tydlig CTA till Nexara (ej påträngande — "vill du gå djupare")
- Footer byter från "AI för Chefer · Uppdateras löpande" till att inkludera Nexara-varumärket

---

## Vad som inte ändras

- Sidans övergripande design och layout
- Vecka 0:s struktur (säkerhet/GDPR) — uppdateras men behåller formen
- Formuläret och signup-flödet (infrastruktur kopplas i nästa fas)
- Tab-navigationen per vecka

---

## Avgränsningar (nästa fas)

- Koppla formuläret mot e-posttjänst (Mailchimp, Kit, Brevo)
- Skriva faktiska e-postmail för varje vecka
- SEO och metadata
