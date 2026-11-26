<div align="center">

#  resQ

### Animal Rescue Coordination Platform

**Report in seconds. Rescue with confidence.**

*Product Design · UX case study & prototype designs*

</div>

---

## Table of Contents

1. [Overview](#overview)
2. [The Problem](#the-problem)
3. [The Solution](#the-solution)
4. [Core Flow](#core-flow)
5. [Research](#research)
6. [Three Connected Surfaces](#three-connected-surfaces)
7. [Pain Points → Design Responses](#pain-points--design-responses)
8. [Scenarios Covered](#scenarios-covered)
9. [Information Architecture](#information-architecture)
10. [Brand & Design System](#brand--design-system)
11. [Wireframes & Screens](#wireframes--screens)
12. [Repository Structure](#repository-structure)
13. [Limitations & Next Steps](#limitations--next-steps)

---

## Overview

**resQ** is a central rescue platform that lets an NGO **receive, verify, prioritise, assign and track** animal rescue cases. It connects three people involved in every rescue (the person who spots the animal, the volunteer who reaches it, and the dispatcher who coordinates) through one shared case record.

> **The promise:** the reporter doesn't have to rescue the animal. They only need to start the chain of help.

This repository contains the full UX case study: research, personas, affinity maps, user flows, site maps, brand guidelines, and low- and high-fidelity wireframes for two mobile apps and one web dashboard.

## The Problem

People regularly see animals in need, but they often:

- don't know **who to contact**,
- don't have **time to stay** with the animal, or
- are **afraid to intervene**.

## The Solution

A single platform where a reporter can raise a case in a few taps, an NGO dispatcher can triage and assign it, and a field volunteer can be guided from dispatch to hospital handover, with a live status visible to everyone and an audit trail at the end.

## Core Flow

```
SEE  ›  REPORT  ›  VERIFY  ›  ASSIGN  ›  RESCUE  ›  TREAT  ›  RECOVER
```

## Research

### Primary research

A **Google Form survey** with **20 responses**, mainly 18–24-year-olds, covering both pet owners and non-pet owners. It asked about rescue behaviour, barriers, trust, reporting, and desired features.

| Finding | Result |
|---|---|
| Had encountered a stray or injured animal | **16 / 20** |
| Would quickly report through an app in a rushed situation | **15 / 20** |
| Did not know whom to contact when an animal needed help | **14 / 20** |
| Said real-time updates on the animal's status would matter | **16 / 20** |

### Key pain points

- Don't know whom to contact
- Limited time to stay with the animal
- Fear of approaching an injured animal
- Uncertainty about whether help will arrive
- Concerns about trust
- Reporting should not feel like a long form

### What users and the NGO need

| User | NGO |
|---|---|
| One quick reporting path | Centralised, verified reports |
| Automatic location + photo + condition | Prioritisation & rescue assignment |
| Emergency priority & NGO contact | Tracking, records & accountable closure |
| Real-time status & confirmation | |

## Three Connected Surfaces

| # | Surface | Platform | Journey |
|---|---|---|---|
| 1 | **Public Reporter app** | Mobile | Report → Confirm → Track |
| 2 | **Field Volunteer app** | Mobile | Dispatch → Navigate → Handover |
| 3 | **Dispatcher (Ops) dashboard** | Web | Triage → Assign → Verify |

All three share one case record: **a report becomes a task, then an audit entry.**

## Pain Points → Design Responses

### Reporter

| ID | Pain point | Design response |
|---|---|---|
| P1 | Panic and time pressure make long forms feel impossible | Five-step wizard, one decision per screen, visible progress |
| P2 | Not sure how to name the animal or its condition | Species cards and multi-select conditions in plain language |
| P3 | Taking photos can put the person in danger | Safety reminder on the photo step and a "Skip for now" option |
| P4 | Vague or wrong location sends responders to the wrong spot | GPS detect, adjustable pin, landmark and "last seen" time |
| P5 | No feedback after submitting | Case ID, live status timeline, and a *Track Rescue Status* action |
| P6 | Fear of mistakes right before sending | Review screen with per-section Edit and "Save and exit" |
| P7 | Nowhere to turn if the app is not enough | 24/7 emergency helpline pinned on the home screen |

### Volunteer

| ID | Pain point | Design response |
|---|---|---|
| P8 | Alert overload: which incident should I take? | One urgent dispatch card plus nearby incidents ranked by severity and distance |
| P9 | Arriving without the right gear or context | Condition, notes, ETA and recommended gear before accepting |
| P10 | Hard to confirm it is the same animal that was reported | Reported vs on-site photo with match confidence and a safety checklist |
| P11 | Animal has moved before arrival | 200 m search protocol, drone-sweep request, coordinator review |
| P12 | Handover has no proof of care | Hospital intake summary, vet sign-off, dispatcher verification |

### Dispatcher

| ID | Pain point | Design response |
|---|---|---|
| P13 | Duplicates and unverified reports flood the queue | Triage queue with duplicate flag and AI species / urgency score |
| P14 | Wrong volunteer gets dispatched | Ranked match by distance, vehicle, tier and rating |
| P15 | No visibility of volunteer safety in the field | Live telemetry, check-in pings and a one-tap voice call |

## Scenarios Covered

Nine scenarios, covering the happy paths **and** the exceptions that usually break rescue apps.

| # | Scenario | Actor | Outcome |
|---|---|---|---|
| S1 | Report an injured animal | Reporter | Case ID + live status |
| S2 | Report without a photo | Reporter | Report still submitted |
| S3 | Edit, pause or cancel a report | Reporter | Draft kept, step re-opened |
| S4 | Accept and complete a rescue | Volunteer | Animal handed to a clinic |
| S5 | Decline an assignment | Volunteer | Back to nearby incidents |
| S6 | Animal not found on arrival | Volunteer + Dispatcher | Search, drone or expand radius |
| S7 | Duplicate or low-priority report | Dispatcher | Merged or queued |
| S8 | Hospital handover and closure | Volunteer + Dispatcher | Case archived with audit trail |
| S9 | Monitor a volunteer en route | Dispatcher | ETA and safety visible |

## Information Architecture

**Reporter app** (bottom tabs: Home · My Reports · Help)
- Home → Report injured animal · Recent community rescues · 24/7 helpline
- Report flow → Animal → Condition → Photos → Location → Review → Confirmation
- My Reports → Case status
- Help → Help content

**Volunteer app** (bottom tabs: Home · Tasks · Profile)
- Home → Urgent dispatch · Nearby incidents
- Active rescue → Incident details → Assigned + protocol → Navigation → Arrival check → Not found / search → Hospital handover
- Tasks → All · Active · Completed
- Profile → Stats & credentials · Coordinator hotline

**Ops dashboard** (persistent dark sidebar, ten destinations)
- Intake → Overview · Incoming reports · Verification & triage
- Dispatch → Volunteer allocation · Live monitoring · Not-found review
- Close-out → Handover verify · Case history
- People & alerts → Volunteer roster · Notifications

## Brand & Design System

**Essence:** *Report in seconds. Rescue with confidence.*
**Personality:** Calm · Direct · Trustworthy · Urgent only when it counts

### Principles

1. **Calm in an emergency**: one decision per screen
2. **Evidence over assumption**: photo, GPS, AI confidence
3. **Safety first**: for people and animals
4. **Always show status**: nobody waits in the dark

### Voice

| Do | Don't |
|---|---|
| Short, active, reassuring: *"Your report is logged and sent."* | Panic, jargon or blame: avoid "Error 500", "Invalid input" |
| Name the next step: *"Coordinator review in progress."* | |

### Colour palette

| Name | Hex | Use |
|---|---|---|
| Rescue Teal | `#2AA898` | Primary, CTAs, active |
| Ink | `#181A1E` | Text, dashboard sidebar |
| Critical | `#E5484D` | Urgent, destructive |
| Caution | `#F5A524` | Warnings, safety |
| Info | `#3B82F6` | En route, links |
| Slate | `#5B6470` | Secondary text |
| Mint | `#D8F3EC` | Selected state |
| Mist | `#F4F6F8` | Surfaces |

### Type, layout & accessibility

- **Typeface:** Inter or system sans (Display 28 Bold · Title 22 Bold · Body 14 Regular · Caption 12 Medium · Label 11 Semibold)
- **Grid:** 4 pt grid, 20 px screen margins
- **Radius:** 12 (cards) · 16 (sheets) · pill (tags)
- **Touch targets:** ≥ 44 px
- **Icons:** one outlined icon set
- **Status** is always paired with text, never colour alone

## Wireframes & Screens

Low-fidelity and high-fidelity wireframes are provided for all three surfaces.

| Surface | Screens |
|---|---|
| **Reporter** | Home · Animal · Condition · Photos · Location · Review · Confirmation |
| **Volunteer** | Home · Incident details · Assigned + protocol · Navigation · Arrival check · Search protocol · Hospital handover · Tasks · Profile |
| **Ops dashboard** | Overview · Incoming reports · Verification & AI triage · Volunteer allocation · Live monitoring · Not-found review · Handover verify · Volunteer roster · Case history · Notifications |

<!-- Replace the paths below with your actual image files -->
<!--
![Reporter flow](./screens/reporter-flow.png)
![Volunteer flow](./screens/volunteer-flow.png)
![Ops dashboard](./screens/ops-dashboard.png)
-->

## Repository Structure

> Adjust this to match your actual folders.

```
resQ/
├── README.md
├── case-study/
│   └── resQ_case_study.pdf
├── screens/
│   ├── reporter/
│   ├── volunteer/
│   └── dashboard/
├── wireframes/
│   ├── low-fidelity/
│   └── high-fidelity/
└── assets/
```

## Limitations & Next Steps

Being upfront about where this work stands:

- The survey has a **small sample (n = 20)**, skewed to 18–24-year-olds.
- Personas and affinity maps are **proto-personas / hypothesised observations**, built from the product brief and not yet validated through interviews.
- Deliverables are **wireframes and design artefacts**, not a working app.

**Next steps**

- [ ] Validate personas with interviews (reporters, volunteers, NGO coordinators)
- [ ] Usability-test the five-step report flow against the "under 2 minutes" success goal
- [ ] Build out the *My Reports* and *Help* tabs (shown as dashed, unbuilt nodes in the site map)
- [ ] Prototype the AI triage and volunteer-matching logic
- [ ] Test the field experience: one-handed, on a scooter, at night

---

<div align="center">

*resQ: because the reporter only needs to start the chain of help.*

</div>
