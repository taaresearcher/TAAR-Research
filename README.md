# TAAR-Research — Olfactory Modulation of Risky Choice in Humans

Trial-level behavioral dataset and codebook for the study
**"Olfactory Modulation of Risky Choice in Humans"**.

This repository provides the de-identified data needed to reproduce every analysis
reported in the study.

## Study in brief

Ninety-six healthy adults (48 women, 48 men) completed a binary economic lottery task
across five sessions. In each session they were exposed to one of six odorants or to a
no-odor (ambient-air) baseline while repeatedly choosing between a **sure option**
(100 monetary units) and a **risky option** (a lottery paying a larger amount with a
given winning probability). The odorants spanned confirmed and putative ligands of
trace amine-associated receptors (TAARs) plus two non-TAAR control odors of opposite
hedonic valence:

| Group | Odorant | Code |
|---|---|---|
| Confirmed TAAR5 agonist | trimethylamine | TMA |
| Putative (candidate) agonist | cadaverine | CDVR |
| Confirmed TAAR5 antagonist | Timberol® | TMB |
| Putative (candidate) antagonist | myrcene | MRCN |
| Control, pleasant (non-TAAR) | citral | CTRL |
| Control, unpleasant (non-TAAR) | caproic acid | CPRA |
| Baseline | ambient air (no-odor) | BPCL |

The no-odor condition and both controls were presented to all 96 participants; each
participant received only one agonist and one antagonist, so comparisons among the
four ligand odorants are **partly between-subject**.

## Files

| File | Description |
|---|---|
| `dataset_deidentified.csv` | Trial-level data — 28,800 rows (96 participants × 5 sessions × 60 trials), 27 columns (includes the derived `Subgroup` column). |
| `simple_effects_all_rewards.csv` | Complete grid of odorant-vs-no-odor simple effects (log-odds) at every observed reward (120–500 MU) × each winning probability, with 95% CIs and FDR-corrected p-values (interaction model, reward re-centred at the minimum). 360 rows. |
| `CODEBOOK.md` | Full variable-by-variable description (also provided as `codebook.docx`). |
| `codebook.docx` | Codebook in Word format. |
| `LICENSE` | Terms of use (CC BY 4.0). |

## Key facts about the data

- **One row = one lottery trial.** Dependent variable: `sure_choice_lottery` (1 = sure option chosen, 0 = risky option chosen).
- **Sure option = 100 MU** on every trial. The risky option pays `risky_amount_2` (120–500 MU) with probability `risky_prob_2` (0.25, 0.50, 0.75), else 0.
- Missing values are coded `NA`. The 180 missing values in the odor-rating columns mean the ratings-adjusted models are fitted on **28,620** observations.
- **De-identification:** direct identifiers (participant name and session timestamps) have been removed; participant IDs are pseudonymous integers. `Day_of_cycle` is retained but is **not used in any analysis** reported in the study.

## License

Released under the **Creative Commons Attribution 4.0 International (CC BY 4.0)**
license — see `LICENSE`. You may share and adapt the data with attribution.
