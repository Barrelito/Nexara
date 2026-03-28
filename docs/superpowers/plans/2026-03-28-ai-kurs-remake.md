# AI-kurs Remake — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Rewrite the content of `ai-kurs.html` so every week is organised around a real first-line manager problem, with specific copy-paste prompts, and add Nexara branding throughout.

**Architecture:** Single static HTML file. All changes are in-place edits to `ai-kurs.html`. No build system, no dependencies. Design and layout are preserved; only text content, a few labels, and the footer/nav copy change.

**Tech Stack:** Plain HTML/CSS. No JavaScript changes required.

**Spec:** `docs/superpowers/specs/2026-03-28-ai-kurs-remake-design.md`

---

## File Map

| File | Action | What changes |
|------|--------|--------------|
| `ai-kurs.html` | Modify | Hero bullets, week-rows, nav, Vecka 0 addition, Vecka 1–6 full content replacement, module nav tab labels, footer, Vecka 6 CTA block |

> There are no automated tests for a static HTML file. Verification for each task = open the file in a browser and confirm visually, or use `Ctrl+F` to locate key strings.

---

## Task 1: Hero bullets + week rows + nav Nexara link

**Files:**
- Modify: `ai-kurs.html` (hero section ~line 483–543, nav ~line 463–468)

- [ ] **Step 1: Replace `.hero-promise` list**

Find and replace the entire `<ul>` inside `.hero-promise` (the list starting with "Renskriva och förbättra text"):

```html
<ul>
  <li>Förbereda svåra medarbetarsamtal på 10 minuter istället för en hel dag</li>
  <li>Avsluta varje möte med ett klart protokoll — utan att du skrivit en rad</li>
  <li>Skicka månadsrapporten på 15 minuter, inte en timme</li>
  <li>Delegera tydligare — och slippa göra det själv ändå</li>
</ul>
```

- [ ] **Step 2: Replace `.weeks-preview` week rows**

Find the `<div class="weeks-preview">` block and replace all six `.week-row` divs:

```html
<div class="week-row"><span class="week-num">1</span><span class="week-name">Förbereda svåra samtal</span><span class="week-tool">ChatGPT</span></div>
<div class="week-row"><span class="week-num">2</span><span class="week-name">Möten som tar för lång tid</span><span class="week-tool">Teams</span></div>
<div class="week-row"><span class="week-num">3</span><span class="week-name">Rapportera uppåt snabbare</span><span class="week-tool">ChatGPT</span></div>
<div class="week-row"><span class="week-num">4</span><span class="week-name">Kommunikation som fastnar</span><span class="week-tool">ChatGPT</span></div>
<div class="week-row"><span class="week-num">5</span><span class="week-name">Planera och delegera</span><span class="week-tool">ChatGPT</span></div>
<div class="week-row"><span class="week-num">6</span><span class="week-name">Bygg din AI-rutin</span><span class="week-tool">Alla verktyg</span></div>
```

- [ ] **Step 3: Add Nexara link to nav**

Find `<div class="nav-logo">AI för <span>Chefer</span></div>` and replace with:

```html
<div class="nav-logo"><a href="https://nexara.se" style="color:inherit;text-decoration:none;font-size:0.75rem;letter-spacing:0.06em;opacity:0.6;margin-right:1.5rem;">Nexara</a>AI för <span>Chefer</span></div>
```

- [ ] **Step 4: Verify in browser**

Open `ai-kurs.html` locally. Confirm:
- Hero promise list has 4 new bullets
- Week overview shows new titles
- "Nexara" appears as a muted link in the nav

- [ ] **Step 5: Commit**

```bash
git add ai-kurs.html
git commit -m "feat: update hero bullets, week rows and nav Nexara link"
```

---

## Task 2: Module nav tab labels

**Files:**
- Modify: `ai-kurs.html` (module nav ~line 564–574)

- [ ] **Step 1: Replace all tab labels**

Find `<div class="module-nav-inner">` and replace its contents:

```html
<div class="module-nav-inner">
  <button class="mod-tab active" onclick="showModule(0)">⚠️ Innan du börjar</button>
  <button class="mod-tab" onclick="showModule(1)">Vecka 1 · Svåra samtal</button>
  <button class="mod-tab" onclick="showModule(2)">Vecka 2 · Möten</button>
  <button class="mod-tab" onclick="showModule(3)">Vecka 3 · Rapportera uppåt</button>
  <button class="mod-tab" onclick="showModule(4)">Vecka 4 · Svåra mail</button>
  <button class="mod-tab" onclick="showModule(5)">Vecka 5 · Delegera</button>
  <button class="mod-tab" onclick="showModule(6)">Vecka 6 · Din rutin</button>
</div>
```

- [ ] **Step 2: Verify**

Confirm tab labels updated. Click through all tabs to ensure JS switching still works.

- [ ] **Step 3: Commit**

```bash
git add ai-kurs.html
git commit -m "feat: update module nav tab labels to problem-first titles"
```

---

## Task 3: Vecka 0 — add free vs. paid section

**Files:**
- Modify: `ai-kurs.html` (`#mod-0`, after the existing "Det här kan du använda AI till" steps list)

- [ ] **Step 1: Add new section after the green step-cards list**

Find the closing `</div>` of the second `.steps-list` in `#mod-0` (the green/sage-coloured "Det här kan du använda AI till" list), then insert this block immediately after it and before the existing `.task-box`:

```html
<div class="steps-title" style="margin-top: 2.5rem;">Gratis eller betald — vad är skillnaden?</div>
<div class="steps-list">
  <div class="step-card" style="border-left: 3px solid var(--slate);">
    <div class="step-num-circle" style="background: var(--slate);">💳</div>
    <div class="step-content">
      <div class="step-title">Betalversioner tränar inte på dina data</div>
      <div class="step-body">ChatGPT Plus och Copilot via din organisations Microsoft 365-licens använder inte det du skriver för att träna modellen. Du kan arbeta friare och behöver inte anonymisera lika noggrant.</div>
      <div class="step-tool"><span>✅</span> ChatGPT Plus · Copilot via M365</div>
    </div>
  </div>
  <div class="step-card" style="border-left: 3px solid var(--gold);">
    <div class="step-num-circle" style="background: var(--gold); color: var(--ink);">🆓</div>
    <div class="step-content">
      <div class="step-title">Gratisversionerna — var lite mer försiktig</div>
      <div class="step-body">De kostnadsfria versionerna av ChatGPT och liknande tjänster kan använda din input för träning. Grundreglerna gäller fortfarande — men med en betald licens kan du slappna av lite mer.</div>
      <div class="step-tool"><span>⚠️</span> Kolla din organisations IT-policy</div>
    </div>
  </div>
</div>
```

- [ ] **Step 2: Verify**

Open Vecka 0-tabben. Confirm the new section appears between the green steps and the "Tre frågor"-task-box.

- [ ] **Step 3: Commit**

```bash
git add ai-kurs.html
git commit -m "feat: add free vs paid AI distinction to Vecka 0"
```

---

## Task 4: Vecka 1 — Förbereda svåra samtal

**Files:**
- Modify: `ai-kurs.html` (`#mod-1`, full content replacement)

- [ ] **Step 1: Replace all content inside `#mod-1 .container`**

Find `<div class="module-section" id="mod-1">` and replace everything inside its `.container` div with:

```html
<div class="security-reminder">
  <div class="security-reminder-icon">⚠️</div>
  <div class="security-reminder-text"><strong>Påminnelse:</strong> Beskriv situationen med egna ord — nämn inte namn eller detaljer som identifierar en verklig person. <a onclick="showModule(0)">Läs reglerna i "Innan du börjar".</a></div>
</div>
<div class="mod-header">
  <div class="mod-num-big">1</div>
  <div class="mod-header-text">
    <div class="mod-week-badge">📅 Vecka 1</div>
    <h2 class="mod-title">Förbereda<br>svåra samtal</h2>
    <p class="mod-desc">Du har ett samtal imorgon med en medarbetare som underpresterar. Du har gått igenom det hundra gånger i huvudet och vet ändå inte hur du ska börja. AI kan hjälpa dig öva samtalet i förväg — inte bara skriva ett manus.</p>
    <div class="mod-time">⏱ Ca 20 minuter</div>
  </div>
</div>

<div class="tip-box">
  <div class="tip-icon">💬</div>
  <div>
    <div class="tip-label">Veckans insikt</div>
    <div class="tip-text">"AI kan rollspela som din medarbetare. Du övar samtalet tills du känner dig trygg — innan det händer på riktigt."</div>
  </div>
</div>

<div class="steps-title">Steg för steg — gör detta nu</div>
<div class="steps-list">
  <div class="step-card">
    <div class="step-num-circle">1</div>
    <div class="step-content">
      <div class="step-title">Formulera en tydlig öppning</div>
      <div class="step-body">Skriv i ChatGPT eller Claude: <em>"Jag ska ta upp med en medarbetare att hen ofta missar deadlines. Vi har pratat om det en gång tidigare. Hjälp mig formulera en öppning som är direkt men inte anklagande."</em></div>
      <div class="step-tool"><span>🤖</span> ChatGPT · Claude</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">2</div>
    <div class="step-content">
      <div class="step-title">Öva med rollspel</div>
      <div class="step-body">Fortsätt i samma chatt: <em>"Rollspela nu som en defensiv medarbetare. Jag övar på att hålla mig saklig när hen hittar ursäkter."</em> Kör samtalet fram och tillbaka tills det känns naturligt.</div>
      <div class="step-tool"><span>🎭</span> Rollspelsövning</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">3</div>
    <div class="step-content">
      <div class="step-title">Planera avslutningen</div>
      <div class="step-body">Be AI:n: <em>"Ge mig tre sätt att avsluta samtalet konstruktivt — med tydliga nästa steg och utan att lämna dålig stämning."</em></div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">4</div>
    <div class="step-content">
      <div class="step-title">Välj ditt eget scenario</div>
      <div class="step-body">Anpassa promptarna till en riktig situation från din vardag — beskriv rollen och problemet med egna ord, utan att nämna namn. AI anpassar sig direkt.</div>
      <div class="step-tool"><span>✏️</span> Anpassa till din situation</div>
    </div>
  </div>
</div>

<div class="tools-strip">
  <div class="tools-strip-label">Verktyg den här veckan</div>
  <div class="tool-pill"><span>🤖</span> ChatGPT (gratis eller Plus)</div>
  <div class="tool-pill"><span>🧠</span> Claude (gratis)</div>
</div>

<div class="task-box">
  <div class="task-label">Veckans uppgift — skickas per mail</div>
  <div class="task-title">Förbered ett riktigt samtal</div>
  <ul class="task-steps">
    <li><span class="task-step-num">1</span>Välj ett samtal du har den här veckan — eller ett du skjutit upp.</li>
    <li><span class="task-step-num">2</span>Formulera öppningen med AI. Kör ett rollspel tills du känner dig trygg.</li>
    <li><span class="task-step-num">3</span>Ha samtalet på riktigt — och se vad som händer.</li>
  </ul>
  <div class="task-result">🎯 <strong>Mål:</strong> Gå in i ett svårt samtal förberedd, inte improviserad.</div>
</div>
```

- [ ] **Step 2: Verify**

Click "Vecka 1 · Svåra samtal" tab. Confirm new situation text, three prompts in `<em>` tags, rollspel step, tools strip, and task box.

- [ ] **Step 3: Commit**

```bash
git add ai-kurs.html
git commit -m "feat: rewrite Vecka 1 — förbereda svåra samtal"
```

---

## Task 5: Vecka 2 — Möten som tar för lång tid

**Files:**
- Modify: `ai-kurs.html` (`#mod-2`, full content replacement)

- [ ] **Step 1: Replace all content inside `#mod-2 .container`**

```html
<div class="security-reminder">
  <div class="security-reminder-icon">⚠️</div>
  <div class="security-reminder-text"><strong>Extra viktigt:</strong> Informera alltid mötesdeltagare innan du startar transkription. Klistra inte in transkript med namn i publika AI-tjänster — anonymisera eller använd Copilot via er organisations licens. <a onclick="showModule(0)">Läs reglerna.</a></div>
</div>
<div class="mod-header">
  <div class="mod-num-big">2</div>
  <div class="mod-header-text">
    <div class="mod-week-badge">📅 Vecka 2</div>
    <h2 class="mod-title">Möten som tar<br>för lång tid</h2>
    <p class="mod-desc">Du leder tre möten i veckan. De drar ut på tiden, folk vet inte vad som beslutades, och du skriver protokoll dagen efter av minnet. Mötesproblematiken är egentligen tre problem — förberedelse, genomförande, uppföljning. AI hjälper med alla tre.</p>
    <div class="mod-time">⏱ Ca 20 minuter</div>
  </div>
</div>

<div class="tip-box">
  <div class="tip-icon">🗓️</div>
  <div>
    <div class="tip-label">Veckans insikt</div>
    <div class="tip-text">"Ett möte utan agenda är ett samtal. Ett möte utan protokoll är ett minne. AI fixar båda på fem minuter."</div>
  </div>
</div>

<div class="steps-title">Steg för steg — gör detta nu</div>
<div class="steps-list">
  <div class="step-card">
    <div class="step-num-circle">1</div>
    <div class="step-content">
      <div class="step-title">Före mötet — skapa en agenda</div>
      <div class="step-body">Skriv i ChatGPT: <em>"Skapa en agenda för ett 45-minuters statusmöte. Vi har tre projekt igång och ska fatta ett prioriteringsbeslut."</em> Anpassa med dina egna projekt.</div>
      <div class="step-tool"><span>🤖</span> ChatGPT · Claude</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">2</div>
    <div class="step-content">
      <div class="step-title">Under mötet — starta transkription i Teams</div>
      <div class="step-body">Klicka på "..." i möteskontrollerna → välj "Starta transkription". Teams dokumenterar allt automatiskt. Kräver Microsoft 365-licens — kolla med din IT-avdelning om du är osäker.</div>
      <div class="step-tool"><span>💼</span> Microsoft Teams · Kräver M365</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">3</div>
    <div class="step-content">
      <div class="step-title">Efter mötet — sammanfatta transkriptet</div>
      <div class="step-body">Klistra in transkriptet i ChatGPT (anonymisera namn om det finns med) och skriv: <em>"Sammanfatta: 1) Beslut som fattades 2) Åtgärdspunkter med ansvarig och deadline 3) Frågor som hänger kvar."</em></div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">4</div>
    <div class="step-content">
      <div class="step-title">Skicka protokollet direkt</div>
      <div class="step-body">Granska sammanfattningen snabbt — är besluten och åtgärdspunkterna rätt? Skicka den sedan till deltagarna. Klart på 5 minuter istället för 45.</div>
      <div class="step-tool"><span>✅</span> Spara 40 min per möte</div>
    </div>
  </div>
</div>

<div class="tools-strip">
  <div class="tools-strip-label">Verktyg den här veckan</div>
  <div class="tool-pill"><span>💼</span> Microsoft Teams (transkription)</div>
  <div class="tool-pill"><span>🤖</span> ChatGPT (sammanfatta)</div>
</div>

<div class="task-box">
  <div class="task-label">Veckans uppgift — skickas per mail</div>
  <div class="task-title">Kör hela kedjan på ett riktigt möte</div>
  <ul class="task-steps">
    <li><span class="task-step-num">1</span>Skapa en AI-agenda innan mötet.</li>
    <li><span class="task-step-num">2</span>Starta Teams-transkription under mötet.</li>
    <li><span class="task-step-num">3</span>Be AI sammanfatta — skicka protokollet till deltagarna.</li>
  </ul>
  <div class="task-result">🎯 <strong>Mål:</strong> Ett protokoll som skickats innan alla lämnat konferensrummet.</div>
</div>
```

- [ ] **Step 2: Verify**

Click "Vecka 2 · Möten" tab. Confirm the Teams step renders as a regular step-card (not prompt-styled), and both prompts use `<em>` formatting.

- [ ] **Step 3: Commit**

```bash
git add ai-kurs.html
git commit -m "feat: rewrite Vecka 2 — möten som tar för lång tid"
```

---

## Task 6: Vecka 3 — Rapportera uppåt snabbare

**Files:**
- Modify: `ai-kurs.html` (`#mod-3`, full content replacement)

- [ ] **Step 1: Replace all content inside `#mod-3 .container`**

```html
<div class="security-reminder">
  <div class="security-reminder-icon">⚠️</div>
  <div class="security-reminder-text"><strong>Påminnelse:</strong> Beskriv rapporten med egna ord — klistra inte in konfidentiella budgetsiffror eller kunduppgifter. <a onclick="showModule(0)">Läs reglerna.</a></div>
</div>
<div class="mod-header">
  <div class="mod-num-big">3</div>
  <div class="mod-header-text">
    <div class="mod-week-badge">📅 Vecka 3</div>
    <h2 class="mod-title">Rapportera uppåt<br>snabbare</h2>
    <p class="mod-desc">Månadsrapporten till din chef ska in på fredag. Du har all information i huvudet — men varje gång sitter du ändå där i en timme och stirrar på ett tomt dokument. Det känns som att det borde gå snabbare.</p>
    <div class="mod-time">⏱ Ca 20 minuter</div>
  </div>
</div>

<div class="tip-box">
  <div class="tip-icon">📊</div>
  <div>
    <div class="tip-label">Veckans insikt</div>
    <div class="tip-text">"Rapporter till ledningen har ett oskrivet format — kort, strukturerat, fokus på avvikelser och beslutspunkter. AI känner det formatet. Du behöver bara fylla i vad som hänt."</div>
  </div>
</div>

<div class="steps-title">Steg för steg — gör detta nu</div>
<div class="steps-list">
  <div class="step-card">
    <div class="step-num-circle">1</div>
    <div class="step-content">
      <div class="step-title">Ge AI en snabb situationsbeskrivning</div>
      <div class="step-body">Skriv i ChatGPT: <em>"Skriv en månadsrapport för mitt team. Vi levererade X i tid, hade problem med Y, och fokuserar på Z nästa period. Max en A4-sida, strukturerat."</em> Byt ut X, Y och Z mot dina faktiska situationer.</div>
      <div class="step-tool"><span>🤖</span> ChatGPT · Claude</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">2</div>
    <div class="step-content">
      <div class="step-title">Strukturera ett beslutsunderlag</div>
      <div class="step-body">Om du behöver presentera ett förslag: <em>"Jag ska presentera ett förslag för ledningsgruppen om att [X]. Hjälp mig strukturera argumenten så att en chef utan detaljkunskap förstår och kan fatta beslut."</em></div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">3</div>
    <div class="step-content">
      <div class="step-title">Skär ner till det väsentliga</div>
      <div class="step-body">Är texten för lång? Skriv: <em>"Gör texten kortare — behåll bara det som kräver ett beslut eller en åtgärd."</em> Ledningen läser det som är kort.</div>
      <div class="step-tool"><span>✂️</span> Kortare = starkare</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">4</div>
    <div class="step-content">
      <div class="step-title">Granska och skicka</div>
      <div class="step-body">Läs igenom AI:ns utkast. Är siffrorna och fakta rätt? Är tonen din? Justera det som behöver justeras — och skicka. Det tar 5 minuter, inte en timme.</div>
      <div class="step-tool"><span>✅</span> Du ansvarar för faktan</div>
    </div>
  </div>
</div>

<div class="tools-strip">
  <div class="tools-strip-label">Verktyg den här veckan</div>
  <div class="tool-pill"><span>🤖</span> ChatGPT</div>
  <div class="tool-pill"><span>🧠</span> Claude</div>
  <div class="tool-pill"><span>💼</span> Copilot i Word</div>
</div>

<div class="task-box">
  <div class="task-label">Veckans uppgift — skickas per mail</div>
  <div class="task-title">Skriv nästa rapport med AI</div>
  <ul class="task-steps">
    <li><span class="task-step-num">1</span>Välj en rapport eller statusuppdatering du har den här veckan.</li>
    <li><span class="task-step-num">2</span>Beskriv situationen för AI — få ett utkast på 2 minuter.</li>
    <li><span class="task-step-num">3</span>Granska, justera och skicka. Mät hur lång tid det tog.</li>
  </ul>
  <div class="task-result">⏱ <strong>Tidsmål:</strong> Månadsrapporten klar på under 15 minuter.</div>
</div>
```

- [ ] **Step 2: Verify**

Click "Vecka 3 · Rapportera uppåt" tab. Confirm new situation text and three prompts.

- [ ] **Step 3: Commit**

```bash
git add ai-kurs.html
git commit -m "feat: rewrite Vecka 3 — rapportera uppåt snabbare"
```

---

## Task 7: Vecka 4 — Kommunikation som fastnar

**Files:**
- Modify: `ai-kurs.html` (`#mod-4`, full content replacement)

- [ ] **Step 1: Replace all content inside `#mod-4 .container`**

```html
<div class="security-reminder">
  <div class="security-reminder-icon">⚠️</div>
  <div class="security-reminder-text"><strong>Påminnelse:</strong> Klistra inte in inkomna mail med personuppgifter. Beskriv situationen med egna ord — du får lika bra hjälp utan att dela känslig information. <a onclick="showModule(0)">Läs reglerna.</a></div>
</div>
<div class="mod-header">
  <div class="mod-num-big">4</div>
  <div class="mod-header-text">
    <div class="mod-week-badge">📅 Vecka 4</div>
    <h2 class="mod-title">Kommunikation<br>som fastnar</h2>
    <p class="mod-desc">Det finns mail i din utkorgsmapp som legat där i dagar. Inte för att du glömt dem — utan för att de är svåra att skriva. AI är bäst på just de mail där tonen måste vara exakt rätt.</p>
    <div class="mod-time">⏱ Ca 20 minuter</div>
  </div>
</div>

<div class="tip-box">
  <div class="tip-icon">📬</div>
  <div>
    <div class="tip-label">Veckans insikt</div>
    <div class="tip-text">"Beskriv situationen — inte hur mailet ska se ut. 'Jag behöver säga detta utan att det låter som en anklagelse' är en bättre startpunkt än 'skriv ett mail om X'."</div>
  </div>
</div>

<div class="steps-title">Steg för steg — gör detta nu</div>
<div class="steps-list">
  <div class="step-card">
    <div class="step-num-circle">1</div>
    <div class="step-content">
      <div class="step-title">Ge ett svårt besked</div>
      <div class="step-body">Skriv i ChatGPT: <em>"Jag behöver meddela en medarbetare att hen inte fick den interna tjänst de sökte. Ton: ärlig och respektfull, med fokus framåt. Skriv ett utkast."</em></div>
      <div class="step-tool"><span>🤖</span> ChatGPT · Claude</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">2</div>
    <div class="step-content">
      <div class="step-title">Dokumentera ett beteendeproblem</div>
      <div class="step-body">När något behöver skrivas svart på vitt: <em>"Jag behöver adressera skriftligt att en medarbetare upprepade gånger lämnar in arbete för sent. Professionellt men tydligt — det ska kunna dokumenteras."</em></div>
      <div class="step-tool"><span>📄</span> Dokumenterande kommunikation</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">3</div>
    <div class="step-content">
      <div class="step-title">Skärp tonen</div>
      <div class="step-body">Om utkastet är för mjukt: <em>"Gör budskapet kortare men lika tydligt. Ta bort allt som mjukar upp utan att tillföra något."</em></div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">4</div>
    <div class="step-content">
      <div class="step-title">Använd Copilot direkt i Outlook</div>
      <div class="step-body">Om du har Microsoft 365: Börja skriva ett nytt mail i Outlook → klicka på Copilot-ikonen → välj "Utkast med Copilot". Beskriv situationen — Copilot skriver åt dig direkt i malfönstret.</div>
      <div class="step-tool"><span>💼</span> Microsoft 365 Copilot</div>
    </div>
  </div>
</div>

<div class="tools-strip">
  <div class="tools-strip-label">Verktyg den här veckan</div>
  <div class="tool-pill"><span>🤖</span> ChatGPT</div>
  <div class="tool-pill"><span>🧠</span> Claude</div>
  <div class="tool-pill"><span>💼</span> Copilot i Outlook</div>
</div>

<div class="task-box">
  <div class="task-label">Veckans uppgift — skickas per mail</div>
  <div class="task-title">Skicka ett mail du skjutit upp</div>
  <ul class="task-steps">
    <li><span class="task-step-num">1</span>Välj ett mail som legat i utkorgen i mer än ett dygn.</li>
    <li><span class="task-step-num">2</span>Beskriv situationen för ChatGPT — be om ett utkast.</li>
    <li><span class="task-step-num">3</span>Justera tonen, godkänn och skicka idag.</li>
  </ul>
  <div class="task-result">🎯 <strong>Mål:</strong> Skicka ett mail du annars hade skjutit upp i dagar till.</div>
</div>
```

- [ ] **Step 2: Verify**

Click "Vecka 4 · Svåra mail" tab. Confirm Outlook/Copilot step is included.

- [ ] **Step 3: Commit**

```bash
git add ai-kurs.html
git commit -m "feat: rewrite Vecka 4 — kommunikation som fastnar"
```

---

## Task 8: Vecka 5 — Planera och delegera

**Files:**
- Modify: `ai-kurs.html` (`#mod-5`, full content replacement)

- [ ] **Step 1: Replace all content inside `#mod-5 .container`**

```html
<div class="security-reminder">
  <div class="security-reminder-icon">⚠️</div>
  <div class="security-reminder-text"><strong>Påminnelse:</strong> Beskriv uppgiften i generella termer — undvik konfidentiell affärsinformation när du formulerar uppdrag med AI. <a onclick="showModule(0)">Läs reglerna.</a></div>
</div>
<div class="mod-header">
  <div class="mod-num-big">5</div>
  <div class="mod-header-text">
    <div class="mod-week-badge">📅 Vecka 5</div>
    <h2 class="mod-title">Planera och<br>delegera</h2>
    <p class="mod-desc">Du vet vad teamet ska leverera — men det är svårt att formulera uppdraget så att någon annan faktiskt kan ta det och köra. Det slutar med att du gör det själv. Dålig delegering beror nästan alltid på en otydlig uppdragsbeskrivning.</p>
    <div class="mod-time">⏱ Ca 20 minuter</div>
  </div>
</div>

<div class="tip-box">
  <div class="tip-icon">🎯</div>
  <div>
    <div class="tip-label">Veckans insikt</div>
    <div class="tip-text">"En tydlig uppdragsbeskrivning besvarar fyra frågor: Vad ska göras? Vad får man besluta själv? Vilka resurser finns? När är det klart? AI skriver den åt dig på tre minuter."</div>
  </div>
</div>

<div class="steps-title">Steg för steg — gör detta nu</div>
<div class="steps-list">
  <div class="step-card">
    <div class="step-num-circle">1</div>
    <div class="step-content">
      <div class="step-title">Skriv en uppdragsbeskrivning</div>
      <div class="step-body">Skriv i ChatGPT: <em>"Jag ska delegera ansvaret för [uppgift] till en medarbetare. Skriv en uppdragsbeskrivning med: mål, resurser, befogenheter och förväntad leverans."</em> Fyll i med ett riktigt uppdrag du har nu.</div>
      <div class="step-tool"><span>🤖</span> ChatGPT · Claude</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">2</div>
    <div class="step-content">
      <div class="step-title">Prioritera teamets uppgifter</div>
      <div class="step-body">Skriv: <em>"Mitt team har dessa uppgifter nästa kvartal: [lista]. Hjälp mig prioritera dem efter påverkan och insats."</em> Du får en enkel matris att visa teamet.</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">3</div>
    <div class="step-content">
      <div class="step-title">Skapa en veckoplan</div>
      <div class="step-body">Fortsätt: <em>"Skriv en kort veckoplan för teamet baserat på prioriteringarna ovan — så att alla vet vad som gäller måndag morgon."</em></div>
      <div class="step-tool"><span>📋</span> Tydlighet sparar frågor</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">4</div>
    <div class="step-content">
      <div class="step-title">Stäm av med medarbetaren</div>
      <div class="step-body">Gå igenom uppdragsbeskrivningen med den du delegerar till. Fråga: "Är det tydligt vad du kan besluta själv?" En tydlig beskrivning ger färre avbrott och uppföljningsfrågor.</div>
    </div>
  </div>
</div>

<div class="tools-strip">
  <div class="tools-strip-label">Verktyg den här veckan</div>
  <div class="tool-pill"><span>🤖</span> ChatGPT</div>
  <div class="tool-pill"><span>🧠</span> Claude</div>
</div>

<div class="task-box">
  <div class="task-label">Veckans uppgift — skickas per mail</div>
  <div class="task-title">Delegera något du normalt hade gjort själv</div>
  <ul class="task-steps">
    <li><span class="task-step-num">1</span>Välj en uppgift du brukar behålla för att "det är enklare att göra det själv".</li>
    <li><span class="task-step-num">2</span>Skriv en uppdragsbeskrivning med AI — dela den med medarbetaren.</li>
    <li><span class="task-step-num">3</span>Låt dem köra. Följ upp — men utan att ta tillbaka uppgiften.</li>
  </ul>
  <div class="task-result">🎯 <strong>Mål:</strong> En uppgift delegerad med en tydlig beskrivning — och du slipper göra den själv.</div>
</div>
```

- [ ] **Step 2: Verify**

Click "Vecka 5 · Delegera" tab. Confirm situation text and three prompts.

- [ ] **Step 3: Commit**

```bash
git add ai-kurs.html
git commit -m "feat: rewrite Vecka 5 — planera och delegera"
```

---

## Task 9: Vecka 6 — Bygg din AI-rutin + Nexara CTA

**Files:**
- Modify: `ai-kurs.html` (`#mod-6`, full content replacement + new CTA block)

- [ ] **Step 1: Replace all content inside `#mod-6 .container`**

```html
<div class="security-reminder">
  <div class="security-reminder-icon">⚠️</div>
  <div class="security-reminder-text"><strong>Påminnelse:</strong> När du bygger din AI-rutin — bygg in dataskyddsvanan från start. Gör det till en reflex, inte en eftertanke. <a onclick="showModule(0)">Läs grundreglerna igen.</a></div>
</div>
<div class="mod-header">
  <div class="mod-num-big">6</div>
  <div class="mod-header-text">
    <div class="mod-week-badge">📅 Vecka 6 · Sista veckan</div>
    <h2 class="mod-title">Bygg din<br>egen AI-rutin</h2>
    <p class="mod-desc">Du har provat verktygen. Några fastnade, andra glömdes bort. Nu handlar det om att bygga in det som faktiskt fungerar — så att det sker automatiskt, inte när du kommer ihåg det.</p>
    <div class="mod-time">⏱ Ca 30 minuter</div>
  </div>
</div>

<div class="tip-box">
  <div class="tip-icon">🔄</div>
  <div>
    <div class="tip-label">Veckans insikt</div>
    <div class="tip-text">"Tre enkla vanor slår tio verktyg du använder ibland. Välj färre, använd dem varje vecka."</div>
  </div>
</div>

<div class="steps-title">Hitta dina egna AI-möjligheter</div>
<div class="tip-box" style="background: var(--warm); color: var(--ink);">
  <div class="tip-icon" style="font-size:1.8rem;">📋</div>
  <div>
    <div class="tip-label" style="color: var(--muted);">Ramverk — AI-vänliga uppgifter</div>
    <div class="tip-text" style="font-family: 'DM Sans', sans-serif; font-size: 0.9rem; line-height: 1.8; color: var(--ink);">
      En uppgift passar bra för AI om den:<br>
      1. Återkommer varje vecka eller månad<br>
      2. Följer ungefär samma struktur varje gång<br>
      3. Innehåller text, siffror eller informationshantering<br>
      4. Tar tid men kräver inte kreativ problemlösning<br>
      5. Har tydlig input och förväntad output
    </div>
  </div>
</div>

<div class="steps-title" style="margin-top: 2rem;">Steg för steg — gör detta nu</div>
<div class="steps-list">
  <div class="step-card">
    <div class="step-num-circle">1</div>
    <div class="step-content">
      <div class="step-title">Identifiera dina tre bästa AI-uppgifter</div>
      <div class="step-body">Skriv i ChatGPT: <em>"Baserat på dessa kriterier — här är mina vanligaste arbetsuppgifter: [lista]. Vilka tre passar bäst för AI-stöd?"</em> Lista 5–10 uppgifter från din vanliga arbetsvecka.</div>
      <div class="step-tool"><span>🤖</span> ChatGPT · Claude</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">2</div>
    <div class="step-content">
      <div class="step-title">Formulera tre konkreta vanor</div>
      <div class="step-body">Fortsätt: <em>"Skriv tre konkreta AI-vanor jag kan börja med nästa måndag, baserat på de uppgifterna."</em> Vanor som är specifika fastnar — "använd AI till måndagsrapporten" är bättre än "använd AI mer".</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">3</div>
    <div class="step-content">
      <div class="step-title">Testa hela kedjan den här veckan</div>
      <div class="step-body">Välj ett arbete du har nu. Använd AI i varje steg: förbered med en prompt, genomför, följ upp med AI-skrivet protokoll eller mail. Se hur det känns att ha AI som standard — inte undantag.</div>
      <div class="step-tool"><span>🔗</span> Alla veckors verktyg</div>
    </div>
  </div>
  <div class="step-card">
    <div class="step-num-circle">4</div>
    <div class="step-content">
      <div class="step-title">Dela ett tips med en kollega</div>
      <div class="step-body">Det bästa sättet att befästa lärandet är att lära ut. Visa en kollega ett enda AI-trick du lärt dig — det tar fem minuter och gör det mer naturligt för dig också.</div>
      <div class="step-tool"><span>👥</span> Dela vidare</div>
    </div>
  </div>
</div>

<div class="tools-strip">
  <div class="tools-strip-label">Alla verktyg du lärt dig</div>
  <div class="tool-pill"><span>🤖</span> ChatGPT</div>
  <div class="tool-pill"><span>🧠</span> Claude</div>
  <div class="tool-pill"><span>💼</span> Copilot</div>
</div>

<div class="task-box" style="background: linear-gradient(135deg, #1a3a5c 0%, #0f2035 100%);">
  <div class="task-label">Kursen är klar — men resan fortsätter</div>
  <div class="task-title">Ditt personliga AI-löfte</div>
  <ul class="task-steps">
    <li><span class="task-step-num">1</span>Skriv ner dina tre AI-vanor — och sätt dem i kalendern.</li>
    <li><span class="task-step-num">2</span>Skicka dem till en kollega och be dem följa upp om tre månader.</li>
    <li><span class="task-step-num">3</span>Fortsätt experimentera. AI förändras snabbt — nyfikenhet är din bästa kompetens.</li>
  </ul>
  <div class="task-result">🎓 <strong>Grattis!</strong> Du har gjort hela kursen. Nu vet du hur du använder AI på riktigt — som chef.</div>
</div>

<div style="margin-top: 2.5rem; background: var(--cream); border: 1.5px solid var(--warm); border-radius: 8px; padding: 2rem 2.5rem; display: flex; align-items: center; justify-content: space-between; gap: 2rem; flex-wrap: wrap;">
  <div>
    <div style="font-size: 0.68rem; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase; color: var(--muted); margin-bottom: 0.5rem;">Från Nexara</div>
    <div style="font-family: 'DM Serif Display', serif; font-size: 1.3rem; color: var(--ink); margin-bottom: 0.5rem;">Vill du gå djupare med AI i din organisation?</div>
    <div style="font-size: 0.9rem; color: var(--muted); max-width: 420px; line-height: 1.6;">Det är vad vi gör på Nexara — hjälper organisationer använda AI på riktigt, inte bara experimentera.</div>
  </div>
  <a href="https://nexara.se" style="background: var(--ink); color: var(--cream); text-decoration: none; font-family: 'DM Sans', sans-serif; font-size: 0.85rem; font-weight: 600; padding: 0.85rem 1.8rem; border-radius: 4px; white-space: nowrap; letter-spacing: 0.03em;">Besök nexara.se →</a>
</div>
```

- [ ] **Step 2: Verify**

Click "Vecka 6 · Din rutin" tab. Confirm:
- The framework tip-box renders in warm/cream style
- The Nexara CTA block appears at the bottom
- The "Besök nexara.se →" link is clickable

- [ ] **Step 3: Commit**

```bash
git add ai-kurs.html
git commit -m "feat: rewrite Vecka 6 — AI-rutin with framework and Nexara CTA"
```

---

## Task 10: Footer update

**Files:**
- Modify: `ai-kurs.html` (footer ~line 1156–1172)

- [ ] **Step 1: Update footer bottom text**

Find `<div class="footer-bottom">` and replace its content:

```html
<div class="footer-bottom">
  AI för Chefer är en gratiskurs från <a href="https://nexara.se" style="color: var(--gold); text-decoration: none;">Nexara</a> — vi hjälper organisationer använda AI på riktigt.
</div>
```

- [ ] **Step 2: Update footer brand tagline**

Find `<p class="footer-tagline">` and replace:

```html
<p class="footer-tagline">En praktisk 6-veckorskurs för första linjens chefer som vill använda AI i sin vardag — utan teknikexamen.</p>
```

- [ ] **Step 3: Verify**

Scroll to footer. Confirm Nexara link appears in gold, tagline updated.

- [ ] **Step 4: Commit and push**

```bash
git add ai-kurs.html
git commit -m "feat: update footer with Nexara branding"
git push origin main
```

---

## Final verification checklist

Before declaring done, run through all tabs once:

- [ ] Vecka 0: New "Gratis eller betald" section visible after the green steps list
- [ ] Vecka 1: Rollspel-prompt present, task box says "Förbered ett riktigt samtal"
- [ ] Vecka 2: Teams UI step renders as regular card, not prompt-styled
- [ ] Vecka 3: New situation text ("stirrar på ett tomt dokument") present
- [ ] Vecka 4: Copilot i Outlook step included
- [ ] Vecka 5: Uppdragsbeskrivning prompt present
- [ ] Vecka 6: Framework box in warm/cream style, Nexara CTA at bottom
- [ ] Footer: Nexara link in gold
- [ ] Nav: "Nexara" link visible (muted, top left)
- [ ] Hero: 4 new promise bullets visible
- [ ] Week overview rows: new titles visible
- [ ] All tab switches work (click through all 7 tabs)
