# AI Build Log — Razorpay Recover

**Project:** Razorpay Recover | **Track:** Recover and Grow with AI  
**Deliverable:** AI-assisted product concept and clickable prototype | **Date:** 13 October 2026

> **Disclosure:** This is a concept prototype using synthetic lender and loan data. Its call is a staged demo recording. No real loan recovery, model-predicted uplift, or production banking integration is claimed.

## 1. AI tools and models used

| Tool | How we used it |
| --- | --- |
| **OpenAI ChatGPT (including GPT-6 in later iterations)** | Product ideation and critique, workflow and decision design, AI-assisted HTML/CSS/JavaScript prototyping, writing and revising the product note, drafting and refining demo scripts, and identifying edge cases. |
| **Web research and public documentation** | Investigated Razorpay Agent Studio, payment/retry capabilities, Razorpay's Blade/RazorSense UI references, Credgenics' collections workflows, and relevant RBI recovery constraints. Sources were used for design inputs; external claims and regulatory interpretation still require formal validation. |
| **Browser-based prototype checks and media-editing utilities** | Checked interactions and generated screen/video assets. These are engineering/editing tools, **not** proof of deployed AI or real transactions. |

We examined public voice-AI options as references; **the prototype does not use a live Sarvam/ElevenLabs calling API**. The final staged borrower-agent recording and narrated screen recording were supplied by the project owner.

## 2. Key prompts, workflows, and AI setup

The iterative workflow was **problem discovery → critique → product decisions → prototype → pressure test → revise → demo**. Representative prompts/instructions from our work:

1. **Validate the economics and permissions:** “If we give provision for restructuring in the loan by the lender, is it bad for lender?” This led to *lender-approved restructuring*, not autonomous AI changes to loan terms.
2. **Define the product:** Expand Razorpay's existing agents to manage repayment problems end to end, competing with specialist debt-collection software. Separate prevention, borrower engagement, recovery execution, and escalation.
3. **Design human control:** “If a borrower asks for human, bot can ask for reason … there will be a time/try limit so that borrower don't get stuck in loop.” We added a direct handoff path, limited AI attempts, and case ownership.
4. **Make conversations consequential:** For a salary-delay scenario, check lender rules and repayment history, confirm the intended date, and explain that the contractual due date, EMI and interest rate do not automatically change. This informed the sample call and the promise-to-pay state machine.
5. **Design lender review:** Show separate **call audio + AI insights** for calls, **read-only transcript/history** for chat, and **lender-only manual takeover**. Remove the lender-facing message composer.
6. **Pressure-test:** Review from both a Razorpay senior-PM and an NBFC Head-of-Collections perspective. We used that critique to prioritise payment intelligence, promise-to-pay follow-through, compliance controls, and a test/control recovery funnel.

**Agent behaviour represented in the prototype:** interpret the borrower's issue → consult *simulated* lender-authorised account/payment context → recommend an action → run **deterministic** policy checks → execute a simulated permitted action or request human approval → verify a simulated ledger outcome. A language model is **not** making live lending decisions in this build.

## 3. An AI output we rejected or significantly improved

**Initial direction:** *Bounce-to-Cure* framed the product around bounced EMIs and a **seven-day cure rate**. A generic voice/chat agent and hardcoded recovery-uplift figures risked looking like a reminder bot with unverified results.

**What we changed, and why:**
- Renamed and repositioned the concept as **Razorpay Recover**, covering pre-due mandate issues, early and later recovery, and human handoff—not just the first seven days.
- Shifted the core claim from “a persuasive AI conversation” to **payment-signal diagnosis → appropriate lender-approved action → verified outcome**.
- Added a promise-to-pay lifecycle: commitment recorded, payment status reconciled, commitment kept or broken, then a policy-checked next step.
- Reframed recovery numbers and uplift as **illustrative synthetic data**, with a proposed holdout comparison rather than claimed business results.
- Rejected the robotic browser-generated voice as the demo experience; replaced it with the project owner's supplied staged two-persona recording and their own narrated screen capture.

These changes came from user judgment, direct feedback, and AI-assisted revisions—not from a validated lender pilot.

## 4. What AI did versus what we decided or supplied

| AI assistance | Human-owned decisions / inputs |
| --- | --- |
| Suggested and compared recovery workflows, risk cases, copy, UX, measurements and implementation options. | Chose the end-to-end recovery strategy, Razorpay Recover branding, and voice-plus-chat direction. |
| Helped create and revise the static lender console, case views, simulations, call logs, insights, approval flows and policy checks. | Selected key borrower situations, demanded manual handoff/time limits and lender-controlled approval, and rejected misleading UX. |
| Drafted call scripts, product-note wording, and demo storyboards; helped edit and synchronise demo media. | Provided the actual staged call audio, spoken narration and recorded prototype walkthrough; reviewed outputs and requested corrections. |
| Helped interpret a separately supplied two-persona pressure test and prioritise changes. | Evaluated product trade-offs and decided which enterprise features to defer. |

## 5. Limitations, risks, and verification

- **No production integration.** There are no live Razorpay payment APIs, lender loan-management/ledger systems, telephony systems, borrower authentication services, or WhatsApp delivery integrations.
- **No live generative agent.** Prototype cases and conversation histories are scripted/simulated. Call audio is staged; playing a recording is not autonomous voice calling.
- **Synthetic metrics.** Recovery propensities, portfolio figures, and holdout examples are illustrative. The product has **not** demonstrated a causal uplift or validated pricing/unit economics.
- **Compliance is a design constraint, not a certification.** Identity verification before loan disclosure, outreach hours, opt-outs, grievance pathways, recording notices and approval rules would need lender-specific implementation plus legal/security review under applicable RBI guidance.
- **Data boundaries matter.** Payment data available to Razorpay is not automatically a complete cross-merchant purchase history or permission to profile borrowers for collections. Production signals require clear legal basis and appropriate lender/borrower authorisation.
- **Operational gaps.** Full DPD campaign management, offline reconciliation, field/legal collections, SLA-backed specialist routing and cross-system audit exports remain future work.
- **Public sharing:** This repository/demo is intended for public viewing. Only staged or synthetic assets should be committed; no credentials, live borrower information or proprietary lender records.

**Next validation:** interview lender collections operators and borrowers; audit possible payment-data integrations and policies; run a permissioned, DPD-stratified test versus the lender's current process; track attempted → connected → promise to pay → promise kept → verified cure, **incremental 30-day net recovery**, longer-horizon recoveries, borrower complaints and cost per recovered account.

---
*This log documents an AI-assisted product design and prototype process; it does not claim a deployed or independently validated AI lending product.*
