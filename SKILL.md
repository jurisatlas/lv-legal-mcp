---
name: lv-legal-mcp-skill
description: Official Latvia (LV) legislation, multi-tier court precedent research, and citation verification skill.
version: 2.0.0
author: JurisAtlas
license: MIT
---

# Latvia Legal Research & Multi-Tier Case Law Skill (`lv-legal-mcp`)

Use this skill whenever the user asks a legal question, drafts a pleading or contract, or researches case law across any judicial instance in **Latvia (LV)**.

## Verification & Research Rules

1. **Citation Verification:** Never fabricate a statutory provision or case citation. Query `search_legislation`, `search_case_law`, `search_tiered_court_decisions`, or `verify_citation` before citing any authority (e.g., `ECLI:LV:AT:2024:0101.SKC000124 or Likumi.lv`).
2. **Multi-Tier Judicial Coverage:**
   - **First Instance (Trial / Municipal / District):** 9 Rajona (pilsētas) tiesas (District/City Courts) & Administratīvā rajona tiesa
   - **Second Instance (Cantonal / Regional / Appellate):** 5 Apgabaltiesas (Rīgas, Kurzemes, Latgales, Vidzemes, Zemgales Regional Courts) & Administratīvā apgabaltiesa
   - **Supreme & Constitutional Instance:** Augstākā tiesa / Senāts (Supreme Court of Latvia) & Satversmes tiesa (Constitutional Court)
   - **Primary Tiered Database:** Latvijas Tiesu Portāls (eli.tiesas.lv — Anonymized Judgments of District, Regional & Supreme Courts) (`https://eli.tiesas.lv`)
