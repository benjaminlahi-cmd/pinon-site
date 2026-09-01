# Piñon

HRSN practice management for New Mexico Turquoise Care — a prototype.

Live: **https://USERNAME.github.io/pinon-site/** *(replace USERNAME after enabling Pages)*

## What it is

Medicaid 1115 demonstration waivers now cover health-related social needs (HRSN): produce
prescriptions, medically tailored meals, housing tenancy supports, non-emergency transport,
and traditional healing practices. The organizations best positioned to deliver that care
are small community-based and tribal-serving providers — who are also the least equipped to
handle eligibility verification, documentation gating, claim scrubbing, and X12 submission.

Piñon is the back office that closes that gap: verify coverage before delivery, block a
claim until its documentation is complete, catch what a payer would reject, submit, and
track the money back to the encounter that earned it.

## Scope

Modelled on **New Mexico Turquoise Care** — the four managed care plans (BCBSNM,
Presbyterian, Molina, UnitedHealthcare Community Plan) plus NM Medicaid fee-for-service,
which is where AI/AN members who decline managed care enrollment are billed.

Two roles, switchable from the rail:

- **Community health worker** — participants, eligibility, service delivery, claims
- **Program director** — A/R, denial patterns, plan scorecards, tribal FMAP reconciliation

## What it demonstrates

- **Eligibility (270/271)** in bulk via Stedi, with the response driving claim routing —
  managed care plan vs. fee-for-service is read off the 271, never chosen from a dropdown
- **Documentation gating** — each catalog service carries its own required attachments and
  cannot join a claim until every one is present
- **Claim scrubbing** — coverage on date of service, payer routing, screening currency,
  Z-code support, prior authorization units, benefit limits, rendering provider identity,
  timely filing, duplicates, AI/AN cost-share suppression
- **X12 lifecycle** — 837P out, 277CA acknowledgement, 835 remittance, with CARC/RARC
  denials translated into a specific next action
- **Traditional healing billing** — practitioners without an NPI billed under the group NPI
  against a tribal credentialing letter, with a state-assigned local modifier
- **100% FMAP tracking** — AI/AN encounters delivered through an I/T/U facility or under a
  written care coordination agreement, per CMS SHO #16-002, tagged at the point of delivery

## Important

Everything in this prototype is **demonstration data**. Participants, dollar figures,
HCPCS codes, modifiers, rates, benefit limits, and plan behaviour are plausible
placeholders — not a New Mexico fee schedule. The U7, U8, and UD modifiers stand in for
state-assigned local modifiers. Nothing here has been verified against NM Health Care
Authority guidance or any plan contract, and none of it should be used to build a real
claim without that reconciliation.

## Running it

It is one self-contained HTML file. Open `index.html` in a browser — no build step, no
server, no dependencies. The only external request is to Google Fonts; without a network
connection it falls back to system faces and everything still works.
