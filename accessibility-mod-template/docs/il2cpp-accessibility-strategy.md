# IL2CPP Accessibility Strategy

This document defines the canonical workflow for analyzing and improving accessibility
in Unity IL2CPP-based games (for example Unity 2021+ / Unity 6 titles using MelonLoader).

This strategy assumes that source-level C# logic is NOT available and that all analysis
must be based on runtime behavior, metadata, logs, and UI structure.

---

## Core constraints

- Method bodies and UI logic are compiled into native code.
- Decompiled C# files are wrappers, not real implementations.
- Accessibility work must rely on runtime observation and interception.

---

## Phase 1: Establish runtime visibility

Required artifacts:
- logs/
- managed/il2cpp/
- loader/net6/

---

## Phase 2: UI structure discovery

- Dump active UI hierarchy
- Identify panels, buttons, text, selectables

---

## Phase 3: Input and focus behavior

- Track navigation and focus changes
- Build independent accessibility navigation model

---

## Phase 4: Text extraction

- Extract visible text and roles at runtime
- Map to screen reader output

---

## Phase 5: Hooking strategy

- Prefer panel activation and UI refresh points
- Avoid blind native hooks

---

## Phase 6: Validation

- Verify spoken output vs UI
- Regression test panels

---

## Out of scope

- Reconstructing original source code
- Decompiling native binaries