# Onyx V1 Documentation & Review Process

This plan outlines how we will collaboratively document the entire Onyx V1 project, ensuring all details, decisions, and lessons are captured for future development.

---

## Phases & Steps

### Phase 1: Preparation
1. Review the structure and purpose of each doc file (README.md, build.md, tests.md, failures.md, lessons.md, v2-plan.md)
2. Identify which files have the most unknowns or require the most user input
3. Agree on the order to tackle the files (recommend: overview → build → tests → failures → lessons → v2-plan)

### Phase 2: Iterative Documentation (per file)
1. For the current file:
    - Read through the template and placeholders
    - Discuss each section with the user, prompting for details, clarifications, and stories
    - Fill in all [TBC] and placeholder content with concrete project data
    - Refine structure or add sections if needed
2. After completing a file, review for clarity and completeness
3. Commit and push changes (optional, or batch at end)

### Phase 3: Cross-File Consistency & Finalization
1. Review all files for consistency (terminology, references, lessons learned)
2. Ensure all key events, tests, and failures are captured and cross-referenced
3. Add any missing links or index entries
4. Final review with user for sign-off

---

## Verification
- Each file is complete, actionable, and clear to a future developer
- All major events, tests, failures, and lessons are documented
- V2 planning reflects all V1 learnings

## Decisions
- Work file-by-file, not all at once
- User provides details, Copilot structures and refines
- Commit/push cadence is flexible (after each file or at end)

## Further Considerations
1. Recommend starting with README.md for context, then build.md, then tests.md, etc.
2. Allow for iterative revisiting of files as new details emerge
3. Use discussion to surface forgotten details and insights
