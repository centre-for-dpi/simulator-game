# Build the Rails: product notes

This is a browser game for CDPI's internal meetings and workshops. Teams play a country's ten-year DPI and AI journey, either as the national program lead or as CDPI's advisory team. The goal is to reach **one billion new people** with DPI and AI services. It is inspired by Copero's career simulator (copero.com.ar/juegos/simulador-carrera).

- **Live version:** https://claude.ai/artifact/GyF2bNmT56WSPt2Dz3Wod4. It is private until shared from the page's Share menu. To update it, republish `index.html` to the same artifact.
- **Source:** `index.html`, a single self-contained file with no build step. Open it in a browser to play offline.
- **Status:** 31 published versions as of 30 September 2026.

---

## 1. What a game looks like

**Setup**, in five steps:

1. **Role:** program lead, or CDPI advisor.
2. **Country:** 29 starting countries, filterable by region (Latin America & Caribbean, Africa, Asia). Each card shows its DPI Map profile and any CDPI engagement status.

   The selected country's profile appears in a panel:
   - **Contents:** context, CDPI today, DPI Map rails with system names, national app, and the real starting values.
   - **Desktop:** pinned on the right while you scroll the cards.
   - **Phone:** above the cards, scrolled into view when you tap one.
3. **First rail:**
   - Digital ID
   - Payments
   - Data Exchange
   - Verifiable Credentials
   - Registries
   - AI Blocks & Public Agents
   - General **DPI advisory** or **AI advisory**: no rail yet beyond what the country already has. The first rail is offered from the second quarter, and AI advisory leans to AI.
4. **Use case:** one of 13, or "Not decided yet".
5. **Pace:**
   - Full game: 40 quarterly decisions, about 90 minutes.
   - Half: 20 decisions.
   - Express: 10 decisions.

   There is also an optional team name and a 45-second room vote timer.

**Each quarter:**

- A decision card for the main country: category, flag chip showing which country it is for, story text, and two to four options. Keys 1–4 or A–D choose.
- As advisor with a portfolio, one decision per advised country follows, in turn ("Country 2 of 3 this quarter").
- An outcome card shows the effects, the drift until the next quarter, a **CDPI lens** explaining the trade-off, and any trophy won with an explanation of why it matters.
- Sometimes a "Meanwhile" news item or an **A/B crisis** follows.

**The screen:**

- **Left column:** score badge (after Copero's OVR), meters, new people reached with a progress bar to 1B, the portfolio list and the trophy shelf.
- **Centre:** the card.
- **Right:** a ten-year record table filled year by year.
- **Bottom:** a line map of quarters.

**End screen:** impact (new people reached) is the headline, then rating, score, milestones, the full journey log and a "Copy summary" button.

**Hall of Fame:** ranked by new people reached, then score. It is stored in the browser only.

## 2. Roles

| | Program lead | CDPI advisor |
|---|---|---|
| Who you are | The country's program champion | CDPI: pro bono, politically neutral technical architect and ecosystem orchestrator |
| First meter | Political capital | Influence (with that government) |
| Extra meter | none | CDPI reputation (across all countries) |
| Decisions | You decide | You advise; the government decides |
| Countries | One | Start with one; take on more (in region and out of region) |
| Game over | Political capital or trust at 0, budget below 0, fired in a reshuffle, corruption | Influence, trust or budget in the main country (you relocate if you advise others), reputation at 0, sacked, corruption |

Advisor-only scenes cover CDPI's own conduct:

- a vendor wanting "CDPI-recommended"
- being asked to write the tender
- "can't you just run it?"
- being stretched thin
- the press asking for blame
- who takes the credit
- vendor gifts
- taking political sides
- CDPI funders checking in

## 3. Core mechanics

**Meters (0–100 except budget):**

- political capital / influence
- budget ($M)
- public trust
- tech capacity
- adoption (%)
- ecosystem
- CDPI reputation (advisor only)

**Time:** 520 weeks from October 2026, in quarterly windows. Two elections, around years 4 and 8.

**Phases:** Design (first 1.5 years), Build & pilot (to year 4), Scale.

**Drift each quarter:**

- income minus running costs; rails that already existed are government-funded
- organic adoption growth, driven by capacity, trust and ecosystem
- blocks compounding, with an AI bonus
- slower growth in very large countries
- political wear
- bureaucracy drag per extra rail, unless the process is fast-tracked
- a trust drain at scale if UN safeguards were never applied
- private-sector reach once rails are open

**Per-decision effects are scaled to the pace**, so 10, 20 and 40-decision games balance.

### Rules the user set explicitly

- **Influence bands** apply to gambles and to whether the government takes CDPI's advice:

  | Influence | Gambles | Advice |
  |---|---|---|
  | 70 or more | win 85% | taken 88% |
  | 40–69 | chance; reputation weighs in, 60+ tips it your way | chance; reputation weighs in, 60+ tips it your way |
  | Below 40 | always backfire | never taken |

  Low capacity or ecosystem (below 30) can still sink a gamble.
- **Elections are pure chance.** Backing any side or campaigning is a coin flip. Influence and reputation don't apply.
- **Nothing is certain.** Any ordinary decision has about a 7% ego or political backfire.
- **Private-sector actions** work when the ecosystem is 70 or more (90% of the time). Below 70 they can backfire, with influence helping. Government-centric choices cut the ecosystem hard.
- **Delivery gambles always succeed** when the country has ID, payments and data exchange rails plus a G2P program with an ID Account Mapper. The option shows a "Rails ready" tag.
- **Corruption ends the game immediately**, in either role. There are four integrity scenes, shown at most once per game at low weight.
- **CDPI never advises on financing.** Loans, grants and budget fights are program-lead only. In the advisor role, the government secures money itself and CDPI only shapes the technical design, including a "running low on money" lifeline from the regional development bank or the World Bank.
- **Neutrality builds reputation** and never costs influence: declining vendor endorsements and gifts, outcome-based tenders, staying out of politics.
- **The program lead is the champion.** They are fired in a reshuffle only when political capital or trust is below 20, or adoption is under 5% after year 3.
- **Starting influence:** 80 in DaaS countries, 65 in bootcamp countries.
- **Don't offer to build what already exists:** rails from DPI Map, national apps and wallets, DaaS wallets.
- **Named partners and public figures only appear positively**, with no invented quotes.
- **Non-DPI approaches cost points.** 25 options are tagged `antiDpi`: point-to-point or custom integrations, database copies, central data lakes, proprietary formats, vendor-run platforms, turnkey, big bang, heavy forks, a single government app built as a silo (it counts as DPI on verifiable credentials or an open-standards ID; it is penalised with a proprietary or vendor-locked ID or its own data store), static surveys, foreign commercial APIs, outsourcing everything. They cost capacity −3, ecosystem −3 and political capital −2, and the outcome shows "Not a DPI approach".
- **Every scenario needs a real trade-off.** Not every option can add points. Weak or coercive options (declining, skipping, mandates, leaving it to consulates) have a net cost. The exception is partner scenes, which stay positive by rule.

### Multi-country advising

- **Offers:** country offers arrive as cards, one in region and one outside, or "stay focused". Larger countries notice CDPI as reputation grows. The cap is 4 extra countries, or 6 at reputation 60+.
- **State:** each advised country has its own full state (meters, flags, rails, use cases, follow-ups). The engine swaps it in with `swapIn()` and out with `swapOut()`.
- **Attention:** advising more countries stretches the team, so each decision moves adoption less.
- **Losing a country:** a country can be lost on its own. If the main country is lost, you continue in the strongest remaining one, with a reputation hit.

### Expansion market (about once a year)

- New country (advisor only).
- New building block. Blocks compound, and AI acts as the integration layer.
- New use case, including "the first train" when you started with "Not decided yet".
- **CDPI bootcamps,** one of each type per country, from the build phase:
  - verifiable credentials: 5 days to deploy the infrastructure on Inji or CREDEBL and launch two credentials, which the government chooses based on the APIs it already has
  - API gateway (secure APIs and federated login)
  - DPI-AI: 5 days to stand up Ollama, which orchestrates open-source and commercial AI models, and OpenFn, which runs use cases as DPI Workflows

  A bootcamp adds its rail if it's missing and sets the bootcamp flags. It is weaker when tech capacity is below 35.

## 4. Mission and scoring

- **Mission:** 1 billion **new** people reached during the game, counted against each country's baseline when it entered the game. People already on the rails don't count. Reaching the billion ends the game with a win.
- **People reached:** adoption plus private-sector services on the rails, capped at 98% of population.
- **Score:** adoption, trust, ecosystem, capacity, milestones, budget, advice rate, rails, use cases and portfolio. It is normalised by pace, so thresholds mean the same at every length. Ratings:
  1. Digital white elephant
  2. Pilot purgatory
  3. Solid foundations
  4. Rails in place
  5. Global DPI reference
- **Impact beats score** everywhere: end screen, Hall of Fame, copied summary.
- **21 trophies**, each shown with an explanation when won:
  - legal framework
  - adoption levels
  - reused rail
  - AI Block
  - open & sovereign
  - high trust
  - thriving ecosystem
  - across borders
  - survived an election
  - early delivery
  - gave back (DPG)
  - governed agents
  - bootcamp delivered
  - stack of rails
  - AI-integrated stack
  - many trains
  - case study
  - no one left behind
  - going global
  - trusted advisor

## 5. Content

**164 scenario definitions** (plus dynamic offers, lifelines and elections), 21 news or crisis events (11 of them A/B crises) and 28 follow-ups triggered by earlier choices.

**Themes:**

- procurement and vendor lock-in: turnkey, free pilot, middleman, ambassador
- +1 approach vs big bang, 100-day quick wins
- legal basis, safeguards (UN Universal DPI Safeguards) and their consequences when skipped
- cloud and sovereignty, DPG choice and forking, registering a DPG
- CDPI delivery models: Bootcamp, DaaS, DIY advisory
- AI: AI Blocks, DPI Workflows, public agents, model choice, escalation, safeguard blocks, delegated consent
- partners: World Bank, IDB, ADB, AfDB, UNDP, UNICEF, UN, Gates Foundation, Co-Develop, WEF/Davos, G20, DPGA, 50-in-5, DPI Global Summit
- champions: Nandan Nilekani, Pramod Varma (CDPI chair), Bill Gates
- bureaucracy and egos, integrity
- crises:
  - conflict: a war abroad, refugees, a violent border region
  - migration: a migration wave, diaspora
  - climate: drought, heatwave, rising seas for islands and low-lying coasts
  - pandemic, earthquake, floods, ransomware, deepfakes, economic crisis
- **Build on it:** the first decision in the 12 countries where CDPI already works, building on the real engagement.

**Use cases (13 + "Not decided yet"):**

- social protection
- health records
- farmer support
- skills & jobs
- MSME credit
- land & property
- business formalisation
- driving & transport
- pensions
- tax & revenue
- disaster response
- remittances
- birth to identity

## 6. Data and sources

- **CDPI decks (Sep 2026):** Exec Committee and Gates intro. Used for engagement status, pipeline and delivery models. Some of this is internal.
- **CDPI status per country:**

  | Status | Countries |
  |---|---|
  | DaaS | Trinidad & Tobago, Brazil, Peru, Togo, São Tomé and Príncipe |
  | Bootcamp | Colombia, Dominican Republic |
  | Advisory | India, Indonesia, Sri Lanka, Mexico, Jamaica, Ethiopia, Cambodia, PNG, Lesotho, Sierra Leone, South Africa, Liberia, Costa Rica, Senegal, Malawi, Timor-Leste |

- **CDPI wiki:** https://docs.cdpi.dev/ is the source of truth for concepts. DaaS means "DPI as a packaged Solution": kits (authentication, credentials, ID Account Mapper) that upgrade existing systems, often within existing procurement, at population scale.
- **DPI Map:** https://dpimap.org/data/, snapshot of 31 March 2026, with identity, payment and exchange JSON. Each rail is levelled 0–3 (none, planned/piloted, implemented, implemented DPI). Implemented rails are in place from day one and give a modest head start.
- **Real baselines from the user:**

  | Country | Starts at | Source | Note |
  |---|---|---|---|
  | India | 44% | Aadhaar about 1.4B, UPI about 900M | actions reach about 10% of the population |
  | Brazil | 85% | gov.br about 180M, Pix about 160M | |
  | Argentina | 64% | Mi Argentina about 30M | |
  | Peru | 95% | RENIEC digital DNI via DaaS, about 36M | |

- **Populations:** rounded 2025 estimates. The 45 extra countries (joinable during play) have placeholder starting stats derived from population.
- **IdLAC** (https://redgealc.org/idlac/): Red GEALC's regional infrastructure connecting national digital identities in Latin America and the Caribbean. Its regional consortium includes the IDB, the World Bank, Co-Develop and the OAS. 12 countries have committed: Argentina, Bolivia, Brazil, Chile, Colombia, Costa Rica, Ecuador, Guatemala, Paraguay, Peru, Dominican Republic and Uruguay. Brazil and Uruguay went from 39 cross-border procedures in 2024 to more than 300 in 2025. In the game, any LAC country with an ID can join through an identity broker (faster cross-border services, but about a 30% chance of a sovereignty backlash on public opinion), run a bilateral pilot (about a 15% chance of backlash), or stay out. Odds ignore influence, as with elections.
- **Border scenes** (border violence, refugees, a migration wave next door) only appear for countries with a land border. Island states are excluded, except those that share an island (Dominican Republic, PNG, Timor-Leste, Indonesia).
- **Country traits:**
  - Argentina: volatile economy, where the currency only falls inside a rare economic crisis.
  - Sri Lanka: debt crisis.
  - Peru: fragile politics, with presidents and prime ministers removed.
  - Many languages, islands, low-lying coast, federal, and others.

## 7. How it's built and tested

- **Architecture:** one HTML file with a data section (countries, blocks, use cases, scenarios, news, milestones, DPI Map, CDPI map) and a small engine: `pickScenario`, `choose`, `drift`, `driftGlobal`, `advance`, `endWindow`, `swapIn`/`swapOut`, `gambleWins`, `adviceTaken`, `privateWorks`, `score`. Rendering is plain template strings; all user text is escaped.
- **Design:** a transit-map "rails" metaphor, with each meter a metro line. Fonts are Big Shoulders Display, Public Sans and JetBrains Mono. There are light and dark themes, and it works at phone width.
- **Balance testing:** extract the script and run headless random-play simulations in Node, typically 1,000–3,000 games per change. There are two policies: random, and "smart" (reads the hidden effects).

  | Player | Win rate |
  |---|---|
  | Random advisor | about 0.5% |
  | "Smart" advisor | about 73% |
  | Program lead (India included) | 0%: one country can't reach a billion new people |

## 8. Open questions and ideas

- **Game length:** a full advisor game with a big portfolio runs well over 100 decisions. Options are auto-deciding advised countries, or capping decisions per quarter.
- **Real starting figures:** only India, Brazil, Argentina and Peru have them. Other countries use DPI Map-based estimates.
- **Mi Argentina:** decide whether it should count as a verifiable-credential rail.
- **Language:** a Spanish or Portuguese version.
- **Review before sharing outside CDPI:** internal pipeline data, the champion scenes (real people) and the extra countries' placeholder numbers.
- **Shared Hall of Fame:** it is per-browser today. A shared version would need the artifact's database capability.
