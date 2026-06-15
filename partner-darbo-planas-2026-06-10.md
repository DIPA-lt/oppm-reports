# DIPA partnerių darbo planas ir statusas

**Dokumento versija:** 1.0  
**Data:** 2026 m. birželio 10 d.  
**Autorius:** Eimantas Norvaišas (Dev vadovas)  
**Auditorija:** DIPA partneriai, projektų užsakovai, vidinė komanda  
**Susiję failai:** [`partner-meeting-summary-jun10-2026.html`](../partner-meeting-summary-jun10-2026.html)

---

## Turinys

1. [Santrauka](#1-santrauka)
2. [Partnerių susitikimo susitarimai (prioritetai)](#2-partnerių-susitikimo-susitarimai-prioritetai)
3. [Pokalbis su Igoriumi — naujas darbo procesas](#3-pokalbis-su-igoriumi--naujas-darbo-procesas)
4. [Statusas: kas padaryta ir kas ne](#4-statusas-kas-padaryta-ir-kas-ne)
5. [Prioritetų hierarchija](#5-prioritetų-hierarchija)
6. [Rizikos ir priklausomybės](#6-rizikos-ir-priklausomybės)
7. [Artimiausi veiksmai](#7-artimiausi-veiksmai)
8. [Dev vadovo vaidmens plėtra (planuojama)](#8-dev-vadovo-vaidmens-plėtra-planuojama)
9. [Priedai](#9-priedai)

---

## 1. Santrauka

2026 m. birželio 10 d. su DIPA partneriais suderinti **trys pagrindiniai prioritetai (P0)** ir **trys antrinės eilės kryptys (P1)**. Tą pačią dieną su **Igoriumi** aptartas Dev vadovo vaidmuo, resursų valdymas ir **naujas darbo principas**:

> Visi nauji (ir šiuo metu kuriami) įrankiai bei automatizacijos vystomi tik remiantis **duomenimis grįsta poreikių analize** ir **MVP principu**. Kiekvienas funkcionalumas turi aiškiai išmatuojamą naudą; projektai skaidomi į etapus ir stebimi **OPPM** sistemoje.

**Nuo susitarimo realiai įvykdyta:** OPPM produkcinis atnaujinimas, komandos admin prieiga, vieno kliento matricos atkūrimas, partnerių dokumentacija, formalizuotas MVP procesas.

**Nepabaigta pagal planą:** Linas RAG core (~20 val.), DIPA OS MVP (~30 val. — stabdoma dėl trūkstamų As-Is metrikų), visa P1 eilė, OPPM plačios apimties feedback ciklas.

| Rodiklis | Vertė |
|---|---|
| P0 įvertinta (fiksuota dalis) | ~50 val. + OPPM (TBD) |
| P1 įvertinta | ~32 val. |
| DIPA OS pardavimų tikslas | +300 % |
| RAG universalus šablonas | Linas RAG multiagent core |

---

## 2. Partnerių susitikimo susitarimai (prioritetai)

### 2.1. Susitikimo esmė

Aiškiai atskirti **strateginius prioritetus (P0)** nuo **vystomų, bet antrinės eilės užduočių (P1)**:

- **OPPM** ir **Linas RAG** multiagentinė architektūra — ilgalaikiai produktų pagrindai.
- **DIPA OS** — vidinės komandos efektyvumo ir pardavimų augimo instrumentas.

---

### 2.2. P0 — prioritetinės kryptys

#### P0-1 · OPPM (One Page Project Management) — finalizavimas

| Laukas | Reikšmė |
|---|---|
| **Projektas** | `oppm-assistant` |
| **Produkcija** | Cloud Run `oppm-assistant-v2` · https://oppm.dipa.lt |
| **Laiko įvertinimas** | **Kol kas neįvertinta** — priklauso nuo feedback apimties |
| **Charakteris** | Nuolatinis iteracinis procesas, ne vienkartinis release |

**Užduotys:**

1. **Klaidų taisymas** — matricos generavimas, importai, teisių valdymas, kalbų palaikymas (LT/EN).
2. **Grįžtamojo ryšio surinkimas** — struktūruotas feedback iš komandos ir klientų.
3. **Patobulinimai pagal feedback** — iteracijos; įvertinimas po pirmojo ciklo.

---

#### P0-2 · Linas RAG — branduolio finalizavimas su multiagentais

| Laukas | Reikšmė |
|---|---|
| **Projektas** | `/Users/mac/Documents/Cursor projects/linas-rag` |
| **Laiko įvertinimas** | **~20 val.** |
| **Apimtis** | Pagal projektinį pasiūlymą |
| **Strateginė reikšmė** | Universalus **template** visiems kitiems RAG su multiagentais |

**Užduotys:**

1. **Multiagentinis orkestratorius (core)** — `smart_agent_orchestrator.py` (Planner → Validator → Retriever → Drafter → Verifier → Finalizer).
2. **Duomenų šaltinių ir agentų integracija** — Vertex RAG, Outlook, inquiry workflow.
3. **Diegimo ir konfigūracijos modelis** — Cloud Run, Firebase, env šablonas kitiems RAG projektams.

**Pastaba:** MVP v1.2 jau perduotas klientui testavimui; ši užduotis — **branduolio finalizavimas kaip šablono**, ne pirmasis MVP release.

---

#### P0-3 · DIPA OS — vidinės komandos automatizacijos (MVP)

| Laukas | Reikšmė |
|---|---|
| **Projektas** | `/Users/mac/Documents/dipa-os-presentation` |
| **Laiko įvertinimas** | **~30 val.** iki MVP testavimo etapo |
| **Tikslas** | +300 % pardavimų augimas per efektyvumą ir lead'ų kokybę |

**Užduotys:**

1. **MVP versijos užbaigimas** — komandos testavimui ir feedback.
2. **Pardavimų komandos darbo laiko matavimas** — lygiagrečiai su MVP (As-Is duomenys).
3. **Komandos testavimo etapas** — praktinis naudojimas, KPI fiksavimas.

---

### 2.3. P1 — antrinės eilės užduotys

> **Svarbu:** tęsiamos lygiagrečiai, bet **neperstumia P0**.

| ID | Užduotis | Projektas | Įvertinimas | Būsena |
|---|---|---|---|---|
| **P1-1** | LJA RAG — užbaigimas + feedback | `/Users/mac/Documents/Cursor projects/lja-ev-rag` | ~12 val. | Planuojama |
| **P1-2** | GCP migracija (senas DIPA Cloud → nauja org.) | Keli projektai / GCP | ~10 val. | Planuojama |
| **P1-3** | DIPA RAG (vidinis, su Intelektex) | Vidinis RAG | ~10 val. | **Blocked** — laukia Intelektex fix'ų |

**P1-2 apimtis:** likusių aplikacijų deploy, DB perkėlimas, Firestore / duomenų struktūrų kūrimas naujoje organizacijoje.

**P1-3 apimtis:** diegimas + smoke test + bendras testavimas po Intelektex paskutinių klaidų taisymų.

---

## 3. Pokalbis su Igoriumi — naujas darbo procesas

### 3.1. Kontekstas

Produktyvus pokalbis apie Dev vadovo **funkcijas**, **atsakomybes** ir **resursų valdymą**. Bendra išvada: norint dirbti efektyviau ir nemėtyti resursų, visi nauji ir šiuo metu kuriami įrankiai vystomi tik pagal griežtą metodiką.

### 3.2. Kas keičiasi

#### 1. Detali poreikių analizė (prieš pradedant darbus)

**Problema iki šiol:** dažnai gaunamos užduotys automatizuoti procesą **be bazinių duomenų**.

**Pavyzdys — DIPA OS:**  
Iš Gretos ir Marijos aiškiai suprantamas poreikis automatizuoti kliento apdorojimo kelią. Tačiau **neturime statistikos**, kiek minučių / valandų šiuo metu praleidžiama prie vieno kliento rankiniu būdu.

**Nauja taisyklė:**  
Užsakovas privalo pateikti **„As-Is“ (kaip yra dabar) metrikas**. Tik žinant, kiek laiko / pinigų prarandame dabar, galima:

- apskaičiuoti **ROI** (per kiek laiko automatizacija atsipirks);
- nuspręsti, ar projektas **apsimoka apskritai**;
- apibrėžti **MVP apimtį** (ką daryti pirmiausia).

#### 2. MVP (Minimum Viable Product) stadijos

**Principas:** nebekuriame „visko iš karto“.

Kiekvienas įrankis ar agentas turi **MVP versiją** — bazinį, greičiausiai sukuriamą funkcionalumą, kuris išsprendžia pagrindinę problemą (**~80 % vertės su ~20 % pastangų**).

| Nauda užsakovui | Nauda Dev komandai |
|---|---|
| Pradeda naudotis ir taupyti laiką nelaukiant galutinio produkto | Testuoja ir tobulina remiantis realiu grįžtamuoju ryšiu |

### 3.3. Naujas darbo procesas (5 etapai)

```
┌─────────────────────────────────────────────────────────────────┐
│  1. POREIKIO IŠKĖLIMAS          │  Užsakovų atsakomybė          │
│     Savaitiniai meet'ai         │  Problema + realūs skaičiai   │
├─────────────────────────────────┼───────────────────────────────┤
│  2. TECHNINIS VERTINIMAS         │  Dev vadovo atsakomybė        │
│     Variantai, MVP apimtis,      │  Laikas + savikaina           │
│     preliminarios sąnaudos       │                               │
├─────────────────────────────────┼───────────────────────────────┤
│  3. TVIRTINIMAS IR OPPM          │  Bendra atsakomybė            │
│     OPPM projektas su MVP        │  Etapai, funkcionalumai,      │
│     stadijomis ir terminais      │  terminai                     │
├─────────────────────────────────┼───────────────────────────────┤
│  4. VYSTYMAS IR TESTAVIMAS       │  Dev + užsakovas              │
│     Eiga stebima OPPM'e          │  MVP / modulis → praktinis    │
│                                  │  testavimas                   │
├─────────────────────────────────┼───────────────────────────────┤
│  5. ITERACIJA                    │  Feedback → patobulinimai     │
│     Pagal realų naudojimą        │  Kitas MVP etapas arba stop   │
└─────────────────────────────────┴───────────────────────────────┘
```

**Užsakovo pateikiamas minimumas (As-Is):**

- Kiek laiko užtrunka procesas **dabar** (min. / val. vienam atvejui)?
- Kaip **dažnai** procesas kartojasi (per dieną / savaitę / mėnesį)?
- Koks **laukiamas rezultatas** po automatizacijos?
- Kokie **piniginiai nuostoliai** dabar (jei žinomi)?

### 3.4. Kaip tai dera su partnerių susitarimu

| Partnerių susitarimas | Igoriaus procesas | Santykis |
|---|---|---|
| DIPA OS MVP ~30 val. | Reikia As-Is metrikų | **Paaiškina stabdymą** — ne vėlavimas, o sąmoningas sprendimas |
| Linas RAG kaip template | MVP 80/20 principas | **Sutampa** — MVP v1.2 jau duotas; core finalizavimas = kitas etapas |
| OPPM stebėjimas | OPPM projektai su etapais | **Sutampa** — OPPM deploy tai ir paruošė |
| Valandų planai | „Nemėtyti resursų“ | **Sutampa** — be duomenų naujas darbas nepradedamas |

---

## 4. Statusas: kas padaryta ir kas ne

> **Atskaitos taškas:** partnerių prioritetų susitarimas (2026-06-10).  
> **Statuso data:** 2026-06-10 (po pokalbio su Igoriumi).

### 4.1. ✅ Kas **buvo padaryta**

#### OPPM — infrastruktūra ir prieiga

| Veiksmas | Detalės | Rezultatas |
|---|---|---|
| Produkcinis redeploy | Cloud Run `oppm-assistant-v2`, revizija `00003-rgx` | Gyva aplinka atnaujinta |
| Super admin allowlist | Pridėti: `mantas@dipa.lt`, `ausrine@dipa.lt`, `eimantas@dipa.lt` (+ esami) | Komanda gali naudoti admin funkcijas |
| Profilio sutvarkymas | `user_profiles` — `mantas@dipa.lt` → `role: super_admin`, `status: active` | Nebe „nuleidžiamas“ vaidmuo prisijungus |

**Techninė pastaba:** super admin yra **allowlist-only** — rankinis Firestore redagavimas be kodo deploy neveikė, nes sistema prisijungimo metu grąžindavo vaidmenį atgal.

#### OPPM — kliento projekto matricos atkūrimas (Balmed)

| Veiksmas | Detalės |
|---|---|
| Šaltinis | Rankinio vedlio pokalbis Firestore (`oppm-progress-1781011581982`, 115 žin.) |
| Užduotys | 10 kanoninių (T1–T10), datos pagal vedlio 8 žingsnį |
| Timeline | Savaitinis, 30 periodų |
| Biudžetas | **6 kategorijos, €50 000** (anksčiau liko tik 1 kategorija — €25 000) |
| Subjektyvios užduotys | **4** (anksčiau — 1) |
| Failas | `oppm-assistant/exports/Patient-conversion-operational-plans-matrix-import.json` |

**Rezultatas:** paruoštas korektiškas JSON importui; tipinis OPPM iteracinis ciklas (feedback → fix → re-import).

#### Dokumentacija

| Dokumentas | Aprašymas |
|---|---|
| `partner-meeting-summary-jun10-2026.html` | Struktūruota partnerių santrauka (P0/P1, rizikos, veiksmai) |
| `docs/partner-darbo-planas-2026-06-10.md` | Šis markdown dokumentas |

#### Procesas

| Veiksmas | Detalės |
|---|---|
| Formalizuotas MVP procesas | Sutarta su Igoriumi: As-Is → vertinimas → OPPM → MVP → testavimas |

---

### 4.2. ⚠️ Kas **dalinai padaryta**

| Sritis | Kas padaryta | Kas liko |
|---|---|---|
| **P0-1 OPPM finalizavimas** | Infrastruktūra, admin prieiga, vienas kliento atvejis | Struktūruotas feedback ciklas iš visos komandos; prioritetizuotas backlog; laiko įvertinimas po pirmojo ciklo |
| **P0-3 DIPA OS** | Koncepcija, architektūra, poreikio supratimas (Greta, Marija) | As-Is metrikos; MVP implementacija (~30 val.); komandos testavimas |

---

### 4.3. ❌ Kas **nebuvo padaryta**

#### P0

| ID | Užduotis | Planas | Priežastis / būsena |
|---|---|---|---|
| P0-2 | Linas RAG core + multiagent | ~20 val. | Ne pradėta / ne užbaigta — MVP v1.2 jau anksčiau perduotas klientui |
| P0-3 | DIPA OS MVP | ~30 val. | **Stabdoma** — trūksta As-Is metrikų (formalizuota su Igoriumi) |

#### P1

| ID | Užduotis | Planas | Būsena |
|---|---|---|---|
| P1-1 | LJA RAG + feedback | ~12 val. | ❌ Neatlikta |
| P1-2 | GCP migracija | ~10 val. | ❌ Neatlikta |
| P1-3 | DIPA RAG + Intelektex | ~10 val. | ❌ **Blocked** — laukiama Intelektex |

#### Planuojama (ne aptarta)

| Tema | Būsena |
|---|---|
| MB steigimas | Planuojama aptarti kitame meet'e |
| Pilnas resursų valdymo modelis (kaip Intelektex) | Tik pasiūlymas — sąlygos neaptartos |

---

### 4.4. Suvestinė lentelė

| Sritis | Susitarimas | Statusas | % |
|---|---|---|---|
| OPPM deploy + admin | P0-1 dalis | ✅ Atlikta | 100 % |
| OPPM feedback ciklas | P0-1 | ⚠️ Dalinai | ~20 % |
| Balmed matricos fix | P0-1 pavyzdys | ✅ Atlikta | 100 % |
| Linas RAG core | P0-2 · 20 h | ❌ Neatlikta | 0 % |
| DIPA OS MVP | P0-3 · 30 h | ⚠️ Blokuota (As-Is) | ~10 % |
| LJA RAG | P1-1 · 12 h | ❌ Neatlikta | 0 % |
| GCP migracija | P1-2 · 10 h | ❌ Neatlikta | 0 % |
| DIPA RAG | P1-3 · 10 h | ❌ Blocked | 0 % |
| MVP procesas (Igorius) | Naujas | ✅ Sutarta | 100 % |

---

## 5. Prioritetų hierarchija

```
P0-1  OPPM finalizavimas           → nuolatinis ciklas (įvertinimas vėliau)
        ├── ✅ Produkcinis deploy
        ├── ✅ Admin prieiga
        ├── ✅ Balmed matricos fix
        └── ⏳ Feedback ciklas (laukia komandos)

P0-2  Linas RAG core + multiagent   → ~20 h | template visiems RAG
        └── ❌ Ne pradėta

P0-3  DIPA OS MVP                   → ~30 h | +300 % pardavimų tikslas
        ├── ✅ Poreikio supratimas
        ├── ⏳ As-Is metrikos (BLOCKER)
        └── ❌ MVP implementacija

P1-1  LJA RAG + feedback            → ~12 h
P1-2  GCP migracija                 → ~10 h
P1-3  DIPA RAG + Intelektex         → ~10 h | BLOCKED: Intelektex
```

**Taisyklė:** P1 **niekada neperstumia** P0. Be As-Is metrikų **naujas P0-3 darbas nepradedamas**.

---

## 6. Rizikos ir priklausomybės

| Rizika | Poveikis | Tikimybė | Mitigacija |
|---|---|---|---|
| OPPM feedback išplės apimtį | Neaiškus P0-1 laiko planas | Vidutinė | Pirmas ciklas → prioritetų sąrašas → įvertinimas |
| DIPA OS be As-Is metrikų | Neįmanoma ROI; per didelė MVP apimtis | **Dabartinė** | Užsakovai (Greta, Marija) pateikia metrikas; procesas formalizuotas su Igoriumi |
| DIPA RAG blokuoja Intelektex | ~10 h negali prasidėti | Aukšta | Eskalacija Intelektex; lygiagretus P0 darbas |
| Daug lygiagrečių projektų | P0 vėlavimas | Vidutinė | Griežtas P0/P1 atskyrimas; OPPM stebėjimas |
| Super admin rankinis Firestore redagavimas | Vaidmuo „nuleidžiamas“ prisijungus | Išspręsta | Allowlist + deploy (2026-06-10) |

---

## 7. Artimiausi veiksmai

### 7.1. Užsakovų / komandos atsakomybė

| # | Veiksmas | Atsakingas | Terminas |
|---|---|---|---|
| 1 | Pradėti naudoti atnaujintą OPPM; prisijungti iš naujo (super admin) | DIPA komanda | Artimiausios dienos |
| 2 | Pateikti **DIPA OS As-Is metrikas** (laikas vienam klientui, dažnumas, nuostoliai) | Greta, Marija | Prieš P0-3 tęsinimą |
| 3 | Struktūruotas **OPPM feedback** (kas neveikia, kas trūksta) | Visi naudotojai | Per 1–2 savaites |
| 4 | Patvirtinti **Intelektex DIPA RAG fix'ų terminą** | Partneriai / Intelektex | Artimiausias sync |

### 7.2. Dev vadovo (Eimanto) atsakomybė

| # | Veiksmas | Įvertinimas | Prioritetas |
|---|---|---|---|
| 1 | OPPM stabilizavimas pagal feedback | TBD | P0-1 |
| 2 | Linas RAG core finalizavimas | ~20 h | P0-2 |
| 3 | DIPA OS — techninis vertinimas **po As-Is** gavimo | ~30 h MVP | P0-3 |
| 4 | OPPM projekto sukūrimas kiekvienam patvirtintam darbui | — | Procesas |
| 5 | LJA RAG, migracija, DIPA RAG | P1 | Po P0 langų |

### 7.3. Kitas susitikimas

| Tema | Tikslas |
|---|---|
| MB steigimas | Mokestinis / teisinis modelis |
| Resursų valdymas | Pilna atsakomybė už programuotojų paiešką, samdymą, kontrolę (kaip Intelektex) |
| DIPA OS As-Is review | MVP apimties ir ROI patvirtinimas |

---

## 8. Dev vadovo vaidmens plėtra (planuojama)

> **Statusas:** pasiūlymas — detaliai aptarti **kitame meet'e**.

### 8.1. MB steigimas

Individuali veikla dėl mokestinių pokyčių tampa neefektyvi. Planuojama steigti **MB** (Mažoji bendrija).

### 8.2. Resursų valdymo modelis

Pasiūlymas: Dev vadovas prisiima **pilną atsakomybę** už papildomų resursų (programuotojų ir kt.):

- paieška ir atranka;
- samdymas / subcontracting;
- darbo kontrolė ir kokybė.

**Analogija:** dabartinis bendradarbiavimas su **Intelektex** (DIPA RAG projektas).

### 8.3. Atviras klausimai (aptarti meet'e)

- Sąlygos ir kainodara (valandinis / projektinis / fiksuotas MVP)?
- Atsakomybių pasiskirstymas tarp DIPA ir MB?
- Kas finansuoja papildomus resursus — projekto biudžetas ar bendras Dev fondas?
- OPPM kaip vienintelis projektų stebėjimo įrankis visiems subrangovams?

---

## 9. Priedai

### 9.1. Projektų keliai

| Projektas | Kelias / URL |
|---|---|
| OPPM Assistant | `oppm-assistant/` · https://oppm.dipa.lt |
| Linas RAG | `/Users/mac/Documents/Cursor projects/linas-rag` |
| LJA RAG | `/Users/mac/Documents/Cursor projects/lja-ev-rag` |
| DIPA OS | `/Users/mac/Documents/dipa-os-presentation` |
| Balmed import JSON | `oppm-assistant/exports/Patient-conversion-operational-plans-matrix-import.json` |

### 9.2. Super admin allowlist (2026-06-10)

```
info@dipa.lt
mantas@dipa.lt
ausrine@dipa.lt
eimantas@dipa.lt
eimantas.norvaisas@gmail.com
```

Failas: `oppm-assistant/src/config/admin-emails.ts`

### 9.3. Valandų suvestinė

| Kategorija | Valandos | Pastaba |
|---|---|---|
| P0 fiksuota | ~50 h | Linas 20 h + DIPA OS 30 h |
| P0 OPPM | TBD | Po feedback ciklo |
| P1 | ~32 h | DIPA RAG priklauso nuo Intelektex |
| **Iš viso (be OPPM TBD)** | **~82 h + TBD** | |

### 9.4. Dokumentų istorija

| Versija | Data | Pakeitimai |
|---|---|---|
| 1.0 | 2026-06-10 | Pirmoji versija: prioritetai, Igoriaus procesas, statusas |

---

*Dokumentas parengtas DIPA partnerių informavimui. Klausimai ir pastebėjimai — rašyti Eimantui; detaliau aptarti artimiausio susitikimo metu.*
