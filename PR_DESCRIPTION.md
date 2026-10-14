# Scf wealth gap (jvelaise/desktop-tutorial#1)

Pull request: https://github.com/jvelaise/desktop-tutorial/pull/1 (merged into `main`)

Compares median net worth of US families headed by a college graduate vs. by someone with a high-school diploma or less, using the Federal Reserve's Survey of Consumer Finances (1989–2025, released Oct. 9, 2026), in 2025 dollars.

**Findings**
- Median net worth: college $321k → $505k; high school or less $78k → $81k.
- Ratio of medians: 4.1× (1989) → 6.2× (2025); low 2.8× in 1995 (95% CI 2.4–3.3), 2025 CI 5.1–7.7.
- Within age groups the widening is clearest at ages 55–64 (3.3× → 11.4×); no clear widening under 35.

**Files**
- `get_data.py`: downloads summary extracts, replicate weights, historic tables, published SEs (raw files git-ignored).
- `estimates.py`: weighted medians overall and by age, with 95% CIs (bootstrap + imputation variance, per Fed documentation).
- `plot.py`: `figures/wealth_gap_education.png`, `figures/wealth_gap_by_age.png`.
- `export_year.py`: one year's records to CSV (`data/scf1998_records.csv` included).
- `README.md`: what the figures show, data sources, and how to rerun.

**Checks**
- Point estimates match the Fed's historic Table 4 for every year, education group and age group.
- Standard errors match the Fed's published 2022/2025 SEs to within $300.

**Caveats**
- Education group sizes shifted a lot over the period.
- "Head" is the SCF reference person.
- Net worth excludes Social Security and defined-benefit pensions.
- Results are descriptive, not causal.

🤖 Generated with [Claude Code](https://claude.com/claude-code)
