---
layout: default
title: Work
permalink: /work/
---
# Work

Three things I've built and run. Each one taught me something about controls, risk or compliance before I knew those were the words for it.

## SEED Toronto — a member platform and the rules behind it
<div class="tags"><span class="tag">Access control</span><span class="tag">PIPEDA</span><span class="tag">Governance</span><span class="tag">Next.js</span></div>

**What it is.** [seedtoronto.org](https://seedtoronto.org): a Korean/English hub of official student benefits (208 institutions, 125 government programs) with school-email-verified accounts and a members-only board. I'm the sole founder and built the site alone with AI coding tools (Claude Code, Codex, Lovable) on Next.js, Neon Postgres and Vercel. 13 verified members as of Nov 2026.

**The problem.** Students were handing me their school emails and dates of birth. I had no idea what I was legally allowed to keep, for how long, or who on my team should be able to see it.

**What I decided.**
- School emails are stored only as a SHA-256 hash. One email can verify one account, and I never need to read the address again, so I don't keep it.
- Admins are identified by account ID, not email. An email allowlist could be taken over by whoever registers that email first.
- Every secret (verification code, reset link, session token) is stored hashed, expires (15 min / 30 min / 12 h) and is single-use.
- 15 rate limits across sign-up, login, reset, posting and reporting. Unverified accounts are deleted after 24 hours.
- A privacy policy written against PIPEDA and CASL, with a retention table that matches the code. The code comments point at the policy and say "change both together."
- An access-control policy: founder approves admins, least privilege, 2FA, same-day revocation, quarterly review.
- An incident response plan: contain → assess → notify affected members and the Privacy Commissioner if there's real risk of harm → keep records 24 months → fix the cause.

**Governance.** 37 organisational documents, consolidated into one operating rulebook: tiered spending approvals (anything over CAD 50 needs two approvals in advance), the Head of Finance signs off on all founder expenses, two people count cash, receipts within 7 days, a quarterly access review, and an asset-and-account register with a second owner for everything in my name.

**What I'd do differently.** I turned on web analytics before updating the operations doc that said "no analytics." I caught it myself and logged it as an open item, but it's a reminder that policy drifts from practice the moment you stop checking.

## SOBOK — a bakery that stopped before it sold
<div class="tags"><span class="tag">Regulatory compliance</span><span class="tag">Cost model</span><span class="tag">Controls</span><span class="tag">Google Sheets</span></div>

**What it is.** A pickup-only home bakery in Toronto making financiers with Korean ingredients. 12 orders from 11 customers across two pre-order rounds in May–June 2026, 9 products.

**The systems.** Three separate ledgers became one Google Sheets workbook: orders flow in from a bilingual Google Form, and costs, inventory for 18 ingredients, production totals and monthly settlement calculate on their own. Input cells are yellow, formula cells are white, and the rule is you don't type in white. The form (built with Apps Script) requires allergen and terms consent, refuses to be edited once it has responses, and HTML-escapes customer input before putting it in a confirmation email.

**The cost model.** A $20 set earned $14.25 in cash but about $3 after valuing my own labour at $18/hour. So volume per round, not price, was the lever.

**The decision I'm proudest of.** Before the next round I listed every rule that applied: public health notice, inspected kitchen, food handler certificate, insurance, business registration, study-permit hour limits, tax thresholds, TTC bylaws. An AI tool told me about a nutrition-labelling exemption; I couldn't find it on the CFIA site, so I threw it out. Someone suggested framing sales as "donations" to skip the rules; I said no. Then I postponed the sale until the kitchen, insurance and registration were done. Not selling was the compliant choice.

## Auditing my own numbers
<div class="tags"><span class="tag">Evidence</span><span class="tag">Data integrity</span></div>

Before I put this site up, I traced every number on my resume and LinkedIn back to a file. Seven didn't hold: a time-saved claim I had never measured, a program count that was off by one, an ingredient count that was off by four, an order count that was off by one, and a revenue growth figure that conflicted with my own records. I removed or corrected all of them. If I'm going to work in a field where people have to trust what I write, that has to start with me.

---

<p><a class="btn" href="{{ '/assets/Jiyoung-Min-Resume.pdf' | relative_url }}">Resume (PDF)</a></p>
