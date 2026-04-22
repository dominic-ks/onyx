# Onyx V1 — Submersion Testing Record

This file records the water tests performed during V1 and the observations that should carry forward into V2.

Unlike the build notes, this is not a component-by-component design record. It is a practical test history: what was put in the water, what happened, and what that means for the next stage.

---

## Summary

The V1 submersion tests confirmed that the submarine could be assembled, sealed, placed in water, and actuated, but not with enough reliability or stability to continue developing V1.

The main outcomes were:

- Bluetooth control is not viable underwater; the connection is lost as soon as the unit submerges.
- The hull seal is not reliable enough for electronics-first testing.
- The Schrader valve did not seal gas properly during syringe operation.
- The syringe ballast mechanism itself was mechanically promising.
- Ballast distribution and internal layout produced poor balance.

V1 should therefore be treated as complete. V2 should begin with empty-hull seal validation, then buoyancy and ballast tests, before any powered electronics are installed.

---

## Test Record

### T1 — Initial Powered Submersion

**Date:** [TBC]

**Goal:**
Confirm whether the assembled submarine could be controlled while submerged.

**Setup:**
- Full V1 hull assembled with internal chassis installed.
- Pi Pico, HC-05 Bluetooth module, motor driver, power bank, ballast syringe, and lead shot ballast fitted.
- Control attempted from an Android phone using the SerialConnector app.
- Environment, depth, and duration were not formally recorded.

**Result:**
Bluetooth control was lost as soon as the submarine submerged.

**Observations:**
- The electronics and control stack worked in air.
- Submersion immediately removed the ability to control the vehicle in real time.
- This changed the practical scope of V1 from a remotely controlled submarine to a short autonomous dive/resurface test platform.

**Conclusion:**
Bluetooth is unsuitable for underwater control. V2 needs a different communication strategy before real-time underwater control can be treated as an objective.

**Issues to Carry Forward:**
- Choose communication method before V2 architecture is locked.
- Treat underwater communication as a design constraint, not an implementation detail.

---

### T2 — Autonomous Dive / Resurface Attempt

**Date:** [TBC]

**Goal:**
Test whether the submarine could perform a simple dive and resurface cycle without maintaining live Bluetooth control underwater.

**Setup:**
- Full V1 hull assembled.
- Control logic modified so one command initiated an autonomous sequence: dive, hold for approximately 10 seconds, then resurface.
- Syringe ballast actuator installed and driven by timed motor pulses.

**Result:**
The workaround avoided the need for active underwater communication, but did not produce a stable, repeatable operating vehicle.

**Observations:**
- The syringe actuator was the strongest mechanical success of V1.
- Timed motor pulses were fragile because there were no physical end-stops.
- The syringe travel was constrained to roughly half of its nominal 60ml capacity by the chassis layout.
- The tube run contained air and was routed awkwardly through the hull.

**Conclusion:**
The syringe ballast concept is worth carrying forward, but V2 needs proper travel limits, better tube routing, and measured displacement performance.

**Issues to Carry Forward:**
- Add end-stop switches or equivalent hard limits.
- Measure useful ballast volume rather than relying on syringe nominal capacity.
- Design the ballast tube path before the chassis layout is fixed.

---

### T3 — Seal and Gas Leakage Observations

**Date:** [TBC]

**Goal:**
Observe whether the assembled hull maintained a watertight seal during submersion and ballast operation.

**Setup:**
- Full V1 hull assembled with acrylic tube, custom acrylic lids, O-ring seals, Schrader valve, and syringe tube penetration.
- Ballast syringe operated while submerged.

**Result:**
The hull was not considered reliably sealed.

**Observations:**
- O-ring sealing remained an ongoing point of failure.
- The Schrader valve allowed gas to pass during syringe operation; bubbles were observed when the syringe was being drawn out.
- The syringe tube hole performed better than expected and appeared to seal by tube fit alone.
- There is no recorded pressure or vacuum test data for the empty hull.

**Conclusion:**
V1 did not establish a validated waterproofing method. V2 must prove seal reliability on an empty hull before electronics are installed.

**Issues to Carry Forward:**
- Create a dedicated empty-hull seal test.
- Test pressure or vacuum retention, not only static water contact.
- Replace improvised O-ring placement with a controlled groove, gasket, or other repeatable sealing method.
- Properly seal or replace the Schrader valve.

---

### T4 — Buoyancy and Balance Observation

**Date:** [TBC]

**Goal:**
Assess whether the assembled submarine sat level and behaved predictably in water.

**Setup:**
- Full V1 hull assembled with internal chassis and lead shot ballast.
- Ballast placed around the remaining internal space rather than in a designed ballast compartment.

**Result:**
The submarine did not achieve stable, controlled balance.

**Observations:**
- The internal chassis occupied most of the tube diameter.
- There was no proper ballast floor or separated ballast volume.
- Lead shot placement was constrained and uneven.
- The vehicle tilted rather than sitting level.

**Conclusion:**
V2 needs ballast distribution designed into the hull from the start. Balance cannot be solved reliably after the chassis fills the available volume.

**Issues to Carry Forward:**
- Add a dedicated low ballast floor or compartment.
- Keep internal chassis clearance separate from ballast space.
- Verify centre of gravity and centre of buoyancy before propulsion testing.

---

## V2 Test Protocol

Use this progression for V2 testing:

1. Empty hull dry assembly check.
2. Empty hull pressure or vacuum seal test.
3. Empty hull static submersion test.
4. Unpowered buoyancy test with ballast only.
5. Ballast mechanism bench test.
6. Ballast mechanism wet test without control electronics.
7. Powered dry integration test.
8. Powered shallow-water test.
9. Communication test underwater.
10. Propulsion test only after sealing, buoyancy, and ballast are stable.

Each test entry should record:

- Date.
- Goal.
- Exact hardware configuration.
- Environment, depth, and duration.
- Whether electronics were installed and powered.
- Observed leaks, bubbles, tilt, resets, signal loss, or mechanical binding.
- Decision made after the test.

