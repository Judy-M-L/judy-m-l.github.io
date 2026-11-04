---
layout: default
title: Work
permalink: /work/
---
# Work

Two organisations I started and still run, taken apart by aspect. Each section opens into the same four parts: what it is, the problem, what I decided, and what I'd do differently. The "why" for each lives in [Writing](/writing/).

## SEED Toronto {#seed}
<div class="tags"><span class="tag">Sep 2026 –</span><span class="tag">Sole founder</span><span class="tag">seedtoronto.org</span></div>

A Korean/English hub of official student benefits for students in Canada — 208 institutions, 125 government programs — with school-email-verified accounts, a members-only board and a 5-person team. I built the site alone with AI coding tools and wrote the rules the organisation runs on.

<details markdown="1">
<summary>GRC <span class="sub">— rules, privacy, risk</span></summary>

<div class="h">What it is</div>
A privacy policy aligned to PIPEDA and CASL, an access-control policy, an incident response plan, a finance rulebook with segregation of duties, and the controls in the code that back them up.

<div class="h">The problem</div>
Students were handing me their school emails and dates of birth. On 15 October someone pointed out that SEED had no personal-data policy at all. I had no idea what I was legally allowed to keep, for how long, or who on my team should be able to see it. A week later I was asking my tools to re-check security because "if someone tries to hack this, not one line can leak."

<div class="h">What I decided</div>
- School emails are stored only as a SHA-256 hash. One email verifies one account, and I never need to read the address again, so I don't keep it. Unverified accounts are deleted after 24 hours.
- Admins are identified by account ID, not email, because an email allowlist could be taken over by whoever registers that address first.
- Every secret (verification code, reset link, session) is hashed, expires, and works once. Fifteen rate limits across sign-up, login, reset, posting and reporting.
- The policy has a retention table, and the code comments point at the policy: change both together.
- Access control: I approve admins, least privilege, 2FA, same-day revocation, quarterly review. Incident response: contain, assess, notify affected members and the Privacy Commissioner if there's real risk of harm, keep records 24 months.
- Money: anything over CAD 50 needs two approvals in advance, the Head of Finance signs off on all founder expenses, two people count cash. The same person never requests, approves and settles a payment.
- Two hard lines I won't move, even as everything else stays flexible: we never hand out student contacts, and we never take referral fees from agencies. Those break trust.
- Honest wording everywhere: SEED is "a not-for-profit student organisation, not yet incorporated." No tax receipts, no invented numbers, no testimonials we don't have.

<div class="h">What I'd do differently</div>
I turned on web analytics on 21 October and the product spec still said "no analytics." I caught it and logged it as an open item, but it taught me that policy drifts from practice the moment you stop checking. Also: thirty-seven governance documents for a student club was too many. By November I'd cut them to one-page guides, because "if it's complicated, nobody will do it."
</details>

<details markdown="1">
<summary>Leadership <span class="sub">— team, titles, saying no</span></summary>

<div class="h">What it is</div>
Building a team from nothing, deciding who holds which title, and learning to decide alone without hiding that I did.

<div class="h">The problem</div>
Things grew faster than I could communicate them. In mid-October I wrote to my team: "I've been deciding and moving on some things alone... I'm sorry if that's confusing. This is my first time doing this too." I'd also handed out a co-founder title early, before I'd set any standard for what co-founder meant.

<div class="h">What I decided</div>
- Took the co-founder and vice-president titles back and rewrote the founders' agreement as sole founder. My reasoning, in my own words at the time: a co-founder shares the same risk and builds the same hours. The site, the documents and the hours were mine. The person stayed on as Head of External Relations, a role that fit what they actually did.
- Set my own rule afterwards: titles come with responsibilities, and the responsibilities get written down first.
- Delegated finance properly: "I give the final sign-off, so don't carry the weight. I won't touch the process. I need interim updates and results."
- Declined a 12-month role a sponsor offered me, because I was already at capacity with SEED and school. I kept the relationship and the smaller commitment. What I wrote: "If this is my organisation, I have to fight through the hard parts myself, fall down, and learn."
- Hiring rule: I don't recruit friends just because they're around. I'd watched a club collapse when public and private blurred.

<div class="h">What I'd do differently</div>
Share more, earlier. I kept verbal agreements to myself because they weren't signed yet, and that left my team with less than they needed. And I'd set the standard before giving the title, not after.
</details>

<details markdown="1">
<summary>Operations / SCM <span class="sub">— data, verification, process</span></summary>

<div class="h">What it is</div>
A dataset of official benefits that has to be correct, a process for keeping it correct, and an approval flow for how the organisation spends and decides.

<div class="h">The problem</div>
"The information schools give out is so vague... checking every one of these links is nothing like easy." Every school's page is different, half the programs have eligibility rules buried three clicks deep, and the content changes without notice. A teammate suggested pulling data automatically from school APIs. I asked: so I have to go fix every change by hand anyway?

<div class="h">What I decided</div>
- Official sources only. Blogs, Reddit and AI answers are leads, not evidence.
- No automatic content changes. A wrong deadline is worse than a stale one, so the code detects and a person fixes.
- A daily job checks one-seventh of all official links and hashes each page's text to catch silent changes. A report lands in SEED's inbox every Monday. Two schools block bots, so they're checked by hand each term. One false "broken" flag turned out to be a misconfigured certificate on the school's side; I fixed the check rather than the data.
- Re-check cadence: deadline-based opportunities weekly, ongoing services quarterly, broken links immediately.
- Approval flow: department plan → finance budget check → President sign-off.
- Scale went 1 school → 7 → 12 → 22 → 209 across 13 provinces and territories in a month, and the verification process is what let it.

<div class="h">What I'd do differently</div>
The first user feedback was blunt: "it was only links, information you could find with ChatGPT." I'd been building a directory when students wanted other students' experiences. I cut dead features the same day and pivoted toward a community board, but I'd ask users earlier next time.
</details>

<details markdown="1">
<summary>Building <span class="sub">— AI tools, code, deployment</span></summary>

<div class="h">What it is</div>
A Next.js site on Neon Postgres and Vercel, built by someone who doesn't write code, using Codex for the first version, Claude Code for features and deployment, Lovable for design.

<div class="h">The problem</div>
It started as a Discord bot in July. A friend said "I don't know how to use this, don't you need a website?" and I agreed. My first week on GitHub: "I don't understand a word you're saying," "if I upload something this bad, won't people make fun of me?" I wanted more than a page, though. "I want to touch the software itself. Build a login. Take security seriously."

<div class="h">What I decided</div>
- Gave each tool one job and kept final review and deployment for myself. Deploys are manual, after a checklist: both languages, links, auth flows, admin visibility, and whether the privacy policy still matches what the code does.
- Everything private on GitHub, from the first day I understood what public meant.
- Every working conversation is saved automatically to a private repo, with secrets redacted, so the project has a memory that isn't only mine.
- When school-email verification was hard, I kept it anyway. It's the one thing that makes the community trustworthy.

<div class="h">What I'd do differently</div>
I'm the only person who can deploy. That's the top risk in my own risk register, and the second admin role is still open. I'd have started recruiting for it before launch, not after.
</details>

---

## SOBOK {#sobok}
<div class="tags"><span class="tag">Apr 2026 –</span><span class="tag">Solo</span><span class="tag">Toronto, pickup only</span></div>

A small bakery making financiers with Korean flavours — mugwort, black sesame, injeolmi, smoked cheese. 12 orders from 11 customers in two pre-order rounds, 9 products, one workbook that runs the whole thing. It started as GUUM, a cost-only "sharing" project, and became a business I'm trying to run properly.

<details markdown="1">
<summary>GRC <span class="sub">— regulation, consent, saying no to shortcuts</span></summary>

<div class="h">What it is</div>
A regulatory checklist of ten items, consent built into the order form, and a few decisions about what I won't do.

<div class="h">The problem</div>
In spring I baked in my dorm kitchen. By October I'd listed what actually applies to selling food in Toronto: public health notice, inspected kitchen, food handler certificate, liability insurance, business registration, study-permit hour limits, tax thresholds, even a transit bylaw about hand-offs inside stations. Most of it I hadn't done.

<div class="h">What I decided</div>
- "Better to do it properly than get kicked out for doing it illegally." Home kitchen was out; I picked a licensed shared kitchen.
- Someone suggested calling sales "donations" to skip the rules. No.
- An AI tool told me about a nutrition-labelling exemption. I couldn't find it on the CFIA site, so I threw it out and marked it "don't trust."
- Every order form requires allergen acknowledgement (wheat, egg, dairy, tree nuts, sesame, soy, shared-kitchen cross-contact) and terms agreement.
- Pushed the first November round back until the kitchen contract, insurance and registration were in place, instead of selling first and fixing later.
- Customer data never goes into GitHub. Work logs are pseudonymised before they're saved.

<div class="h">What I'd do differently</div>
The order form collects email, phone and Instagram handle but still has no privacy notice or retention period. I know, because I found it auditing my own bakery. That's the next fix.
</details>

<details markdown="1">
<summary>Decisions <span class="sub">— how a one-person business decides</span></summary>

<div class="h">What it is</div>
A decision log with eighteen entries, each with who decided and why, and a two-AI setup where one tool builds and the other verifies.

<div class="h">The problem</div>
"Not by guesswork. I want to do everything properly, so it stays mine." But I'm one person with two AI assistants that will happily build anything, including a 25-entity data model for a bakery that sells twenty boxes a month.

<div class="h">What I decided</div>
- Formulas only. No scripts, no database, no AI in the ledger. Cost: $0. The 25-entity model went in a drawer.
- One tool builds, the other reviews. Every change goes to a copy of the live ledger first and reaches the original only after I approve it.
- Rules decide payment, inventory and order confirmation. People decide refunds, price changes, purchases and bulk messages. AI decides nothing.
- Short, final calls, recorded: payment at order time; fixed pickup time and place; 20 boxes per round; cutoff noon the day before; refunds until 48 hours before pickup.
- Keep SEED and SOBOK apart. Different organisations, different rules, no cross-promotion.

<div class="h">What I'd do differently</div>
I printed business cards and insert cards before the flavour list and storage instructions were final. The cards say five flavours and "refrigerated"; the truth is six and "frozen." Paper is a release, and I shipped it early.
</details>

<details markdown="1">
<summary>Operations / SCM <span class="sub">— ledger, inventory, round economics</span></summary>

<div class="h">What it is</div>
Three ledgers became one Google Sheets workbook: orders flow in from the form, and recipes, ingredient inventory, packaging, overhead, cost and monthly settlement calculate from them. Yellow cells are inputs, white cells are formulas, and you don't type in white.

<div class="h">The problem</div>
"The quantities I make are always different... there's no 'sell this many, earn this much.'" I was adding up each order by hand, buying ingredients by feel, and had no idea whether a $20 set made money.

<div class="h">What I decided</div>
- Counted physical stock by weighing containers minus tare, then let the sheet do it: remaining = opening + purchases − used − waste, with a reorder flag.
- Korean-won purchases entered raw and converted by one exchange-rate cell. Prices recorded before discount. Real cash spend kept separate from standard cost. "The ledger is the latest; if anything disagrees, fix it to match the ledger."
- Built the cost model with my own labour in it: a $20 set earned $14.25 cash but about $3 once I valued my time at $18/hour. So volume per round, not price, is the lever. Break-even is 7–9 sets; below that, cancel the round and refund.
- Round rules: cutoff noon the day before, payment within 24 hours, 20-box cap, pickups along one subway line.
- Pricing I set myself: 6-piece set $30, singles $4.50–5.00, benchmarked against a survey of 100 Toronto bakeries.

<div class="h">What I'd do differently</div>
The "3 hours to 30 minutes" I used to say about admin time was an estimate, not a measurement. The next round gets a stopwatch. My own planning doc says not to promise savings I haven't measured, and I should have listened to it sooner.
</details>

<details markdown="1">
<summary>Building <span class="sub">— form, script, what broke</span></summary>

<div class="h">What it is</div>
A bilingual Google Form generated by Apps Script, with an on-submit trigger that totals the order and emails the customer a confirmation with payment instructions.

<div class="h">The problem</div>
"Can you make the form email people automatically when they submit?" Then: an unverified-app permission wall, a crash on the "closed" message, preview HTML pasted into the wrong file. "It's not even an app, it's a Google Form, why is it like this."

<div class="h">What I decided</div>
- The form ID lives in script properties, not in the code. The script refuses to edit a form that already has responses, so existing orders can't be damaged.
- Customer input is HTML-escaped before it goes into the email.
- Quantities validated by pattern, email validated, consent checkboxes required.
- I edited the script myself for the Korean copy and asked for the English to be matched, instead of letting the tool rewrite both.

<div class="h">What I'd do differently</div>
The payment email address is hard-coded in the local script. It never reached GitHub, but it's a secret-in-source pattern and it should be a property. Found that in the same audit.
</details>

---

## Auditing my own numbers {#audit}
<div class="tags"><span class="tag">Nov 2026</span><span class="tag">Evidence</span></div>

Before this site went up, I traced every number on my resume and LinkedIn back to a file. Seven didn't hold: a time-saved figure I'd never measured, a program count off by one, an ingredient count off by four, an order count off by one, and a growth figure that conflicted with my own records. I corrected or removed all of them. If I'm going to work in a field where people have to trust what I write, that starts here.

<p><a class="btn" href="{{ '/assets/Jiyoung-Min-Resume.pdf' | relative_url }}">Resume (PDF)</a></p>
