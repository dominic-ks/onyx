# Onyx V1 — Lessons Learned

> Higher-level insights extracted from the V1 build. These inform V2 design and process.

---

## Engineering Insights

### 1. Physical design dominates software
In small underwater robotics, mechanical and physical constraints are the primary challenge. Software is the easy part. Time should be front-loaded on enclosure, buoyancy, and layout — not firmware.

### 2. Fixed solutions don't survive contact with reality
Every component that was fixed (non-adjustable) eventually needed to move. Design for adjustment from the start, especially for ballast and internal layout.

### 3. Orientation must be decided before layout
Discovering that the unit may need to run upside down — after the layout was done — cascaded into multiple rework problems. Orientation is a first-order constraint, not an afterthought.

### 4. Seal failure mode is pressure differential, not just water contact
Seals that hold in static immersion may fail under pressure or during entry/exit. A seal protocol should test pressure, not just surface contact.

### 5. Tight enclosures force serial problem-solving
When space is very constrained, you cannot solve problems in parallel — fixing one thing displaces another. This compounds iteration time significantly. More internal volume reduces this.

### 6. Runtime is a hard constraint with small LiPo
~150mAh is not much. Any test requiring sustained operation will hit this limit fast. Power profiling must happen early in V2.

---

## Process Lessons

### 1. Test incrementally, not all-at-once
Testing everything together (sealed, in water, powered) makes it impossible to isolate failures. Each subsystem should be validated independently before integration.

### 2. Log failures immediately
Insights decay fast. "I'll remember that" doesn't work. Write it down when it happens.

### 3. Define a test protocol before running the test
Without a written protocol, results are inconsistent and not comparable across iterations. Even a short setup description matters.

### 4. Treat end of V1 as a deliberate checkpoint
V1 is complete not because it's done, but because it's time to reset, review, and plan. The transition to V2 should be explicit and documented.

---

## What Would Be Done Differently

| Decision | What Happened | What to Do Instead |
|----------|--------------|-------------------|
| Internal layout | Placed before orientation was confirmed | Fix orientation first, then layout |
| Sealing | Applied before testing protocol existed | Define seal test, run it on empty enclosure first |
| Ballast | Designed as fixed system | Design as adjustable from day one |
| Testing | Mixed system tests | Subsystem-first, integration after |
| Documentation | Informal / post-hoc | Log in real time, use structured templates |

---

## Notes

- [Add additional insights here as they are recalled or discovered]
