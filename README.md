# DeskSide

**On-device presence check for shared clinic workstations.**

If a person leaves a shared clinic computer and the session stays open, DeskSide shows a **local lock prompt**. Camera frames stay on the machine. No cloud upload. No face identification. No reading of clinical records.

| Item | Value |
| --- | --- |
| Contest | [ASUS UGen AI League Innovation Hackathon](https://contest.bhuntr.com/en/39jg9vimiynrhlksze/home/) |
| Theme | Workplace AI |
| Battlefield | Lightning — ASUS UGen300 USB AI Accelerator (Hailo-10H) |
| Track | Global Online |
| Team | Nana Safo Duker · Kumasi, Ghana |
| Stage | **I — design documentation.** The accelerator is not in hand yet. |
| Repository | https://github.com/Nana-Safo-Duker/deskside |

> This is **not** a diagnosis tool, **not** a patient-identity system, and **not** the GeneHus genomic risk model. GeneHus is separate founder work and is outside the scope of this entry.

---

## Problem

Shared hospital desk PCs often stay unlocked when clinicians are called away. The next person—or a visitor—can see the last screen. Cloud session checks fail when the ward network drops.

## Solution (Stage II target)

1. A USB webcam looks at the chair.
2. Frames go to a Python service on the clinic PC (not uploaded).
3. Inference runs on the **ASUS UGen300** USB accelerator (Hailo-10H).
4. The model returns **person present** or **person absent**.
5. If absent and the OS session is still open → local lock prompt.
6. Staff locks or dismisses. A local log may store time + present/absent only—**no image kept**.

### Stage I substitute

Stage I does **not** require the UGen300. A laptop may simulate the present/absent decision so the prompt and log can be exercised. That simulation is **not** a Hailo result and is **not** reported as device accuracy.

---

## Repository layout

| Path | Contents |
| --- | --- |
| [docs/01-scenario-and-problem.md](docs/01-scenario-and-problem.md) | Workplace scenario and problem |
| [docs/02-architecture.md](docs/02-architecture.md) | System architecture |
| [docs/architecture.svg](docs/architecture.svg) | Architecture diagram |
| [docs/03-model.md](docs/03-model.md) | Model class (exact zoo file deferred to Stage II) |
| [docs/04-hardware-software.md](docs/04-hardware-software.md) | USB UGen300 and host software |
| [docs/05-privacy.md](docs/05-privacy.md) | Desk-camera data protection rules |
| [docs/06-stage-i-and-stage-ii.md](docs/06-stage-i-and-stage-ii.md) | What Stage I covers vs Stage II |
| [docs/07-performance.md](docs/07-performance.md) | Validation protocol — results **not measured** yet |
| [docs/08-references.md](docs/08-references.md) | Sources |

---

## Privacy (summary)

- **Purpose:** only whether a person is at the workstation.
- **Ghana Data Protection Act, 2012 (Act 843):** minimise frames; process on the PC; do not retain for upload; do not read names, folder numbers, or diagnoses.
- **Session lock pattern:** NIST SP 800-53 Rev. 5, control AC-11.
- Contest demos use the builder or an empty chair. **No patients.**

---

## Status / honesty

| Claim | Stage I |
| --- | --- |
| Trained or converted Hailo model | Not done |
| Measured accuracy | Not claimed |
| Video on real UGen300 | Stage II only (if shortlisted) |
| Exact Hailo zoo filename | Deferred until SDK is in hand |

If shortlisted (Stage II: 6 Nov – 4 Dec 2026): install the SDK, run a Hailo zoo person-detection model on the UGen300, fill the performance table in `docs/07-performance.md`, and record a hands-on device demo.

---

## Contact

Nana Safo Duker · Kumasi, Ghana  
Contest contact for this entry: `safoduker@genehus.bio`
