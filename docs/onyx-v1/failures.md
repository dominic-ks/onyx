# Onyx V1 — Failure Log

> **Instructions:** Log every failure here, immediately. No failure is too small. Do not edit past entries.

---

## Template

```
---

### F[N] — [Short Failure Name]

**Date:** YYYY-MM-DD
**Related Test:** T[N] (if applicable)

**What Failed:**
Describe what broke, stopped working, or behaved unexpectedly.

**Likely Cause:**
Best current understanding of why it failed.

**Fix Applied:**
What was done to address it (or "None — unresolved").

**V2 Prevention:**
How to avoid this in V2.
```

---

## Failures

---

### F1 — Waterproof Seal Reliability

**Date:** [TBC]
**Related Test:** T3

**What Failed:**
Seal did not reliably maintain watertight integrity under submersion.

**Likely Cause:**
[TBC — adhesive type, application method, surface prep, pressure differential]

**Fix Applied:**
Nitrile glue ordered as replacement. Not yet applied/tested.

**V2 Prevention:**
- Define and follow a seal validation protocol before any water test
- Test seal independently (without electronics) first
- Use a redundant sealing approach (glue + gasket or O-ring)

---

### F2 — Internal Component Orientation Conflict

**Date:** [TBC]
**Related Test:** [TBC]

**What Failed:**
Internal component layout incompatible with expected orientation — unit may need to run upside down for physical function.

**Likely Cause:**
Orientation constraints not fully mapped during design phase. Component placement done before orientation requirement was understood.

**Fix Applied:**
None — structural change required for V2.

**V2 Prevention:**
- Determine and lock orientation requirements before any physical layout
- Mock up layout with inert placeholders first
- Document orientation assumption explicitly in build notes

---

### F3 — Buoyancy / Stability Issues Underwater

**Date:** [TBC]
**Related Test:** T4

**What Failed:**
Unit did not achieve stable, controllable position underwater. [TBC — describe: rolled, pitched, sank too fast, floated too high, etc.]

**Likely Cause:**
[TBC — weight distribution, ballast placement, enclosure shape, centre of gravity vs. centre of buoyancy]

**Fix Applied:**
[TBC]

**V2 Prevention:**
- Calculate centre of gravity and centre of buoyancy before assembly
- Design ballast position to be adjustable
- Prototype buoyancy in open water before sealing electronics

---

### F4 — [Add Next Failure Here]

**Date:** [TBC]
**Related Test:** [TBC]

**What Failed:**
[TBC]

**Likely Cause:**
[TBC]

**Fix Applied:**
[TBC]

**V2 Prevention:**
[TBC]
