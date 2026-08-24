# Executive product review — Creator Voice Studio

Student: Hoàng Tuấn Hưng (2A202601911) · Group G01 · Industry: content-creator
Prepared: 2026-08-24 · Source snapshot: 2026-08-24

## Product decision

- **Product / stage:** Creator Voice Studio — pilot (invited cohort, max 50 creators)
- **User problem and value hypothesis:** Creators lose non-native audience because
  re-recording a video in another language costs days and a voice they do not have.
  If localisation takes under one hour in the creator's own cloned voice, they will
  localise most uploads. Believed when at least 60% of pilot creators localise more
  than half their new uploads within 8 weeks with no drop in audience trust.
- **AI role and automation level:** semi-automated. AI translates the script and
  renders synthetic speech; the creator reviews and confirms every render before
  export. Decision reversibility: partially-reversible — the model can be deleted,
  but audio already published off-platform cannot be recalled.
- **Target milestone:** 2026-11-02 launch/review date; next review 2026-11-30.
- **Proposed decision:** **conditional-go** — pilot only, capped cohort, Viet Nam
  and the EU excluded until the GAP-04 review clears them.

## Top production risks

| High-risk moment | Affected stakeholder | Harm | Current control | Residual risk |
|---|---|---|---|---|
| A user uploads someone else's sample and requests a voice model | Performer whose voice is cloned (affected-non-customer) | Voice sold as synthetic performance without consent, credit or pay; dignity and financial loss discovered only after publication | Self-declaration checkbox, reactive email takedown | Sev 4 / Lik 2 after a hard consent gate; enforcement still depends on the performer noticing |
| Cloned voice of a real identifiable person exported and distributed off-platform | Public receiving the audio, and the impersonated person (public-society) | Recipients act on words the person never said; audio cannot be recalled once distributed | Static named-figure prompt filter, general support inbox | Sev 4 / Lik 2; protected-voice matching is imperfect against a determined attacker |
| Creator cancels while voiceprint, samples and model remain in vendor storage and backups | Creator whose biometric voiceprint is retained (user-customer) | A usable clone of a person survives their withdrawal of consent | Primary-database record deletion only | Sev 3 / Lik 2 pending evidenced cascade deletion |
| Sponsored-segment script asserts first-hand product claims the creator never made | Consumers acting on the segment (affected-non-customer) | Fabricated endorsement in a trusted voice drives purchases | Help-centre accuracy note, editable draft | Sev 2 / Lik 3 after per-claim confirmation |
| Synthetic segment published with no AI disclosure | Creator and channel (user-customer) | Platform enforcement, demonetisation, advertising-disclosure exposure, trust loss | Documentation page only | Sev 2 / Lik 2 once disclosure is the default |

## Release gates

| Gap ID | Must-have product requirement | Acceptance evidence | Owner | Status |
|---|---|---|---|---|
| GAP-01 (blocking) | No model trained or used for generation without a stored, auditable consent artifact: liveness-checked enrolment by the sample owner, or a signed rights grant naming them | Refusal logs over a negative test set; sampled audit showing a consent artifact per active model; timed claim-response drill | Trust and Safety Product Owner | in-progress |
| GAP-02 (blocking) | Durable machine-readable provenance on every export plus default audience-facing disclosure; disclosure removal refused for cloned real-person voices | Export inspection across every format; override attempt logs; counsel confirmation against the obligation text in force | Creator Experience Product Owner with Platform Engineering | planned |
| GAP-03 (blocking) | Voice and likeness data treated as sensitive personal data: declared lawful basis, retention limit, cascade deletion across vendor systems and backups, creator deletion receipt | Data map; completed deletion audit with receipts; written vendor deletion confirmation | Data Protection Officer | planned |
| GAP-04 (blocking) | Independent legal, privacy **and** security sign-off as one gate, covering jurisdiction classification, obligation list, the biometric data path and the vendor transfer | Written legal opinion per market; obligation checklist with owners; security report covering exfiltration and injection testing; explicit market exclusions | Legal and Privacy Counsel with Security Engineering lead | not-started |
| GAP-05 | Impersonation defence on the audio, not the prompt string: voice-similarity matching at enrolment and generation, refusal plus on-call escalation | Red-team report with bypass rate and known residual bypasses; escalation response-time log | Trust and Safety with Security Engineering | not-started (pilot gate 2) |
| GAP-06 | Testimonial and review templates withdrawn; sponsored scripts unrenderable until each first-hand claim is confirmed or removed | Weekly human-review sample with unverified-claim rate; refusal logs from the claim gate | Content Quality Product Owner | not-started (pilot gate 2) |

## Value and guardrails

- **Success KPI + target:** ≥60% of pilot creators localise more than half their new
  uploads within 8 weeks; median finished-edit to localised-export under 1 hour.
- **Risk KRI + target:** substantiated impersonation or non-consent claims per 1,000
  active voice models per month — target zero; median claim resolution under 48h.
  Rising unsubstantiated claim volume is reviewed as a leading indicator.
- **Hard guardrail + limit:** 100% of active voice models backed by a verified consent
  artifact, and 100% of exports carrying durable provenance marking. Never traded off
  for activation, conversion or localisation volume. A single breach pauses new
  enrolments and reopens the release decision — it does not become a backlog item.
- **Fallback experience:** on refusal, low confidence or outage the creator still gets
  the translated script as text and subtitles over the original audio, plus an
  optional clearly-labelled stock narrator voice. Consent or protected-voice checks
  that cannot complete are queued to a human reviewer. Every refusal states its reason
  and the appeal route.
- **Monitoring / review cadence:** weekly Trust and Safety and product metric review
  during the pilot; monthly risk review with the risk acceptance owner; full re-review
  on any substantiated claim, guardrail breach, new market, new vendor or model
  version, scope change toward visual likeness or full automation, or new VN/EU guidance.

## Accountability

- **Accountable Product Owner:** Product Owner, Creator Voice Studio
- **Risk acceptance owner:** VP Product and Trust, authority for a limited pilot
- **Independent reviewer(s):** Legal and Privacy Counsel (outside the product line),
  Data Protection Officer, Security Engineering lead
- **Residual-risk rationale:** two residual risks are accepted knowingly. Export is a
  one-way door — provenance and disclosure reduce deception but cannot undo it, so
  impersonation residual severity stays at 4. And protected-voice matching plus consent
  verification are imperfect against a determined attacker, with GAP-05 red-teaming
  deliberately at gate 2, so the pilot is capped at 50 invited creators with political
  content excluded to keep the exposed population small while that evidence is gathered.
- **Next review trigger:** earlier of 2026-11-30 or a substantiated impersonation or
  non-consent claim, a guardrail breach on consent coverage or export provenance, a
  successful protected-voice bypass in red-teaming, a new market or vendor, a scope
  change toward visual likeness or automated publishing, or new VN/EU guidance.
- **Decision/approval needed today:** VP Product and Trust to accept the residual risk
  for a 50-creator pilot with VN and EU excluded, and to confirm that a single
  guardrail breach reopens this decision. Legal, privacy and security to commit to the
  GAP-04 sign-off date, since the pilot cannot start without it.

## Scope limits of this pack

Structural validation is not fact-checking, legal advice or compliance certification.
The Viet Nam status is deliberately `uncertain-requires-legal-review`; the EU
`limited-transparency` reading is a product judgement from a summary policy page, not
counsel's opinion. Legal classification was not derived from the risk snapshot.
