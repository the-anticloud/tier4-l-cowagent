# Radon_Complexity_Lab_Results
**Project:** `L_COWAGENT` | **Status:** `PASS` | **Run:** `2026-09-30T17:14:20.030944+00:00`

**Framework:** [Radon — Cyclomatic Complexity & Maintainability Index](https://radon.readthedocs.io/)

## Key Metrics

- **files_analyzed:** `10`
- **average_complexity:** `{'grade': 'A', 'score': 2.575}`
- **complexity_grade:** `A`
- **complexity_score:** `2.575`
- **mi_output:** `E:\fenta\Downloads\The Anticloud\TIER_4_INFERENCE_AGENTS\L_COWAGENT\UPSTREAM\camel\generators.py - A (65.56)
E:\fenta\Do`

## Raw Output (first 50 lines)
```
E:\fenta\Downloads\The Anticloud\TIER_4_INFERENCE_AGENTS\L_COWAGENT\UPSTREAM\camel\generators.py
    C 156:0 RoleNameGenerator - A (5)
    M 172:4 RoleNameGenerator.__init__ - A (5)
    M 34:4 SystemMessageGenerator.__init__ - A (4)
    C 21:0 SystemMessageGenerator - A (3)
    M 125:4 SystemMessageGenerator.from_dicts - A (3)
    M 198:4 RoleNameGenerator.from_role_files - A (3)
    C 210:0 AISocietyTaskPromptGenerator - A (3)
    C 285:0 SingleTxtGenerator - A (3)
    C 312:0 CodeTaskPromptGenerator - A (3)
    M 330:4 CodeTaskPromptGenerator.from_role_files - A (3)
    M 85:4 SystemMessageGenerator.validate_meta_dict_keys - A (2)
    M 231:4 AISocietyTaskPromptGenerator.from_role_files - A (2)
    M 262:4 AISocietyTaskPromptGenerator.from_role_generator - A (2)
    M 292:4 SingleTxtGenerator.__init__ - A (2)
    M 302:4 SingleTxtGenerator.from_role_files - A (2)
    M 98:4 SystemMessageGenerator.from_dict - A (1)
    M 218:4 AISocietyTaskPromptGenerator.__init__ - A (1)
    M 320:4 CodeTaskPromptGenerator.__init__ - A (1)
    M 362:4 CodeTaskPromptGenerator.from_role_generator - A (1)
E:\fenta\Downloads\The Anticloud\TIER_4_INFERENCE_AGENTS\L_COWAGENT\UPSTREAM\camel\human.py
    C 23:0 Human - A (3)
    M 53:4 Human.display_options - A (3)
    M 77:4 Human.get_input - A (3)
    M 97:4 Human.parse_input - A (3)
    M 42:4 Human.__init__ - A (1)
    M 115:4 Human.reduce_step - A (1)
    M 140:4 Human.clone - A (1)
E:\fenta\Downloads\The Anticloud\TIER_4_INFERENCE_AGENTS\L_CO
```

---
_Anticloud Independent Benchmark — 2026-09-30T17:14:20.030944+00:00_