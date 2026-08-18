# Codebook — `dataset_deidentified.csv`

Dataset for the study *Olfactory Modulation of Risky Choice in Humans*.

The file contains **28,800 rows**: 96 participants × 5 sessions × 60 trials. One row = one lottery trial.
Sure option = 100 MU on every trial. The risky option pays `risky_amount_2` with probability `risky_prob_2`, and 0 otherwise.
MU = monetary units; one randomly selected trial was paid out at the end of the study.
Missing values are coded `NA`. The 180 missing values in the odor-rating columns correspond to sessions in which ratings were not recorded; models including these covariates are therefore fitted on 28,620 observations.
Direct identifiers (participant name, session timestamp) have been removed.

| Variable | Description | Values / range | NA |
|---|---|---|---|
| `participant` | Participant identifier (pseudonymous integer). 96 unique values. | 1–103 (not contiguous) | 0 |
| `session` | Experimental session number. Each participant attended five sessions, ≥48 h apart. | 1–5 | 0 |
| `odour` | Odor condition. BPCL = no-odor (ambient air); CDVR = cadaverine; CPRA = caproic acid; CTRL = citral; MRCN = myrcene; TMA = trimethylamine; TMB = Timberol®. | BPCL, CDVR, CPRA, CTRL, MRCN, TMA, TMB | 0 |
| `task` | Task label; the same value in every row. | lottery | 0 |
| `rank` | Trial number within the session. | 1–60 | 0 |
| `sure_amount` | Payoff of the sure option, in MU. Constant. | 100 | 0 |
| `location_sure` | Horizontal screen position of the sure option (negative = left, positive = right). | -0.3, 0.4 | 0 |
| `risky_amount_1` | Payoff of the losing outcome of the risky option, in MU. Constant. | 0 | 0 |
| `risky_prob_1` | Probability of the losing outcome. Equals 1 − `risky_prob_2`. | 0.25, 0.5, 0.75 | 0 |
| `risky_amount_2` | Payoff of the winning outcome of the risky option, in MU. Twenty levels in steps of 20. Continuous predictor. | 120–500 | 0 |
| `risky_prob_2` | Probability of winning the risky option. Categorical predictor (reference: 0.25). | 0.25, 0.5, 0.75 | 0 |
| `evrisk` | Expected value of the risky option, in MU. Derived: `risky_amount_2 × risky_prob_2`. | 30–375 | 180 |
| `location_risky` | Horizontal screen position of the risky option. | -0.3, 0.4 | 0 |
| `chosen_button_lottery` | Side of the screen chosen. | left, right | 0 |
| `sure_choice_lottery` | **DEPENDENT VARIABLE.** 1 = sure option chosen; 0 = risky option chosen. Overall proportion of sure choices: 0.494. | 0, 1 | 0 |
| `reaction_time_lottery` | Response time, in seconds. | 0.07–77.59 | 0 |
| `Sniffing_test` | Sniffin' Sticks olfactory acuity score (16-point scale), measured at screening. | 7–16 | 600 |
| `Day_of_cycle` | Self-reported day of the menstrual cycle (female participants only). **NOT used in any analysis.** | 1–41 | 17160 |
| `Intensity_pre` | Perceived odor intensity rated before the task (0 = none, 10 = very intense). | 0–10 | 180 |
| `Intensity_post` | Perceived odor intensity rated after the task, same scale. | 0–10 | 180 |
| `Familiarity` | Perceived odor familiarity (0 = unfamiliar, 10 = familiar). Covariate. | 0–10 | 180 |
| `Valency` | Perceived odor valence / pleasantness (−5 = very unpleasant, +5 = very pleasant). Covariate. | -5–5 | 180 |
| `Gender` | Participant gender as recorded at screening. 48 women, 48 men. | F, M | 0 |
| `Age` | Participant age in years at screening. | 18–41 | 0 |
| `odor` | Duplicate of `odour`; identical in all rows. Retained as recorded. | BPCL … TMB | 0 |
| `Intensity_avg` | Mean perceived intensity. Derived: `(Intensity_pre + Intensity_post) / 2`. Covariate. | 0–10 | 180 |
| `Subgroup` | Ligand subgroup: which agonist and antagonist the participant received (derived from the odour conditions present for that participant). Four groups of 24. Not used in the main models; used only in the subgroup sensitivity analysis. | Cadaverine+Myrcene, Cadaverine+Timberol, Trimethylamine+Myrcene, Trimethylamine+Timberol | 0 |
