# Onyx V2 — Forward Plan

> Derived from V1 lessons, failures, and unresolved problems. This is a living document — update it as planning progresses.

---

## Must-Fix (Blockers for V2)

These are not optional. V2 cannot succeed without addressing these.

| # | Issue | Source |
|---|-------|--------|
| 1 | Waterproofing reliability | F1, multiple tests |
| 2 | Internal orientation must be resolved before layout | F2 |
| 3 | Buoyancy and balance must be stable before propulsion testing | F3 |
| 4 | Ballast system must be installed and validated | T5 incomplete |
| 5 | Seal validation protocol needed (test before electronics go in) | lessons.md |

---

## Improvements

Things that would significantly improve V2 but aren't hard blockers:

| Area | Improvement | Notes |
|------|-------------|-------|
| Enclosure | More internal volume if possible | Reduces layout friction |
| Ballast | Fully adjustable positioning | Not fixed-mount |
| Power | Profile actual current draw | Determine real runtime |
| Power | Larger LiPo if volume allows | ~300–500mAh target |
| Sealing | Redundant seal method | Glue + O-ring or gasket |
| Assembly | Document assembly sequence | Prevent rework loops |
| Testing | Run subsystem tests before integration | Bench → dry seal → wet seal → water |

---

## Experiments to Run

These need structured test entries in [tests.md](./tests.md) when executed:

| Experiment | Goal |
|------------|------|
| Seal pressure test (empty enclosure) | Validate seal holds before electronics go in |
| Buoyancy profile (no ballast) | Understand baseline before adding ballast |
| Ballast range test | How much volume change is needed to submerge? |
| Power draw measurement | Real runtime under load |
| Stability test (ballast installed) | Can it hold a stable depth? |
| IR range test underwater | Does IR penetrate water at operating distances? |
| Orientation test | Confirm upside-down mount works mechanically |

---

## Unknowns

Things V2 will need to answer that V1 didn't:

- [ ] Does IR reliably work through the enclosure walls underwater?
- [ ] What is the minimum ballast volume change needed for meaningful depth control?
- [ ] What is the actual power draw under full operation?
- [ ] Can the unit achieve neutral buoyancy with current weight budget?
- [ ] What seal method reliably holds at [target depth]?
- [ ] Is the syringe ballast mechanism reliable under pressure?
- [ ] What is the stability behaviour when propulsion is active?

---

## V2 Design Principles

Based on V1 experience, V2 should be designed around these rules:

1. **Orientation first** — lock the mounting orientation before anything else
2. **Seal before electronics** — validate the empty enclosure is watertight before installing components
3. **Adjustable over fixed** — every positional parameter should be adjustable
4. **Incremental testing** — bench → dry → static water → powered water
5. **Document as you go** — don't rely on memory

---

## Backlog / Ideas

Low-priority items to consider for V2 or beyond:

- [ ] Active depth hold (PID control with pressure sensor)
- [ ] Camera integration
- [ ] WiFi/BLE control instead of IR (range limitations of IR)
- [ ] 3D-printed custom enclosure
- [ ] External ballast weight system (removable lead/tungsten)
- [ ] LED status indicator (visible through enclosure)
