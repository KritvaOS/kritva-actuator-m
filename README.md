# Kritva Actuator Kritva-M

Proprietary and confidential. Copyright (c) 2026 Kritvaos. All rights reserved.

Child repository of `KritvaOS/kritva-actuator` (the parent). Owner: Mechanical Intern 2.

**Status: Concept.** `sizing/inputs.json` is the existing baseline from the parent. M is the reference: S and L copy its structure. At Stage 4 `MECHANICAL_BOM.csv` and the M-specific results are imported from the parent.

The common interface, CAN protocol, units and the shared sizing engine are owned by the parent and are **not** redefined here. Read `docs/interfaces/INTERFACE_CONTROL_DOCUMENT.md` in the parent first.

## Layout

| Folder | Content |
|---|---|
| `sizing/` | `inputs.json` (variant inputs) and `results/` (outputs with the parent commit used) |
| `cad/` | CAD (Git LFS for binaries): housing, shafts, brackets, encoder mount, assembly |
| `drawings/` | Released drawings (PDF plus native) |
| `assembly/` | Assembly procedure for this variant |
| `bom/` | `MECHANICAL_BOM.csv`, item prefix `MB-NNN` |
| `tests/` | Mechanical test plans |
| `results/` | Raw evidence: measurements, inspection records |
| `docs/` | Variant design specification, copy of the design review checklist and its result |
| `scripts/` | Vendored checks (`check_bom.py`, `check_inputs.py`) |

## Variant class (provisional, parent ACT-DEC-025)

M: 10 N·m continuous, 20-25 N·m peak, 45 RPM. This is the elbow baseline and the A0 reference (ACT-DEC-008 and 009).

## Workflow

1. Work on a branch; open a pull request; the owner and reviewer approve.
2. `make check` must pass (BOM schema, sizing inputs).
3. Status moves Concept, Designed, Fabricated, Bench-tested, Validated only by independent review. CI success does not promote a design.
4. Loaded, peak-torque and fault tests only on a restrained, guarded, instrumented fixture.
5. Do not edit common interface documents here; raise a design change request in the parent.
