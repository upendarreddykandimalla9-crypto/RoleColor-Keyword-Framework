# RoleColorAI (RCAI) - AI Engineer Take-Home Assignment

This repository contains a lightweight NLP prototype that:
1) Takes raw resume text as input
2) Scores the resume across four RoleColor traits:
   - Builder
   - Thriver
   - Enabler
   - Supportee
3) Outputs:
   - A normalized RoleColor score distribution
   - A rewritten resume summary aligned to the dominant RoleColor

No UI is included (not required). The focus is clarity, reasoning, and clean code.

---

## Part 1 :- RoleColor Keyword Framework

### Builder
**Keywords:** strategy, vision, roadmap, architecture, scalable, innovation, modernization, optimization, platform, system  
**Why:** Signals long-term thinking, system design, and shaping technical direction.

### Thriver
**Keywords:** fast-paced, deadline, urgent, ownership, deliver, execution, turnaround, ambiguity, sprint, resilient  
**Why:** Signals speed, pressure-handling, and ownership-driven execution.

### Enabler
**Keywords:** collaboration, cross-functional, stakeholder, alignment, communication, coordination, partner, facilitate, influence, mentorship  
**Why:** Signals bridging teams, coordinating execution, and aligning stakeholders.

### Supportee
**Keywords:** reliability, stability, monitoring, documentation, testing, maintenance, refactoring, uptime, quality, runbook  
**Why:** Signals stability work, operational excellence, and consistent support.

---

## Part 2 :- Resume RoleColor Scoring

### Method
- Lowercase + tokenize resume text using a simple regex
- Count keyword matches per RoleColor
- Normalize scores so totals sum to 1.0

This is intentionally explainable and easy to extend.

---

## Part 3 — Resume Summary Rewrite

### Method
- Choose the dominant RoleColor (highest score)
- Use a RoleColor-specific template to create a 4–6 line summary
- Template-based rewriting avoids adding facts not present in the resume

---

## How to Run

### 1) Files
- `rcai_score.py` (main script)
- `sample_resume_builder.txt` (sample input 1)
- `sample_resume_thriver.txt` (sample input 2)

### 2) Run
```bash
python rcai_score.py --resume sample_resume_builder.txt
python rcai_score.py --resume sample_resume_thriver.txt
