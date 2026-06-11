# Say My Name: LLM Refusal Bias — Interactive Validation Dashboard

**Secondary analytical validation of Haq & Saldías (FAccT 2026)**  
Mario DeSean Booker, Ph.D. · Purdue University Global · School of Business and Information Technology

---

## What This Is

This repository contains an interactive data visualization dashboard supporting an independent secondary validation of:

> Haq, I., & Saldías, B. (2026). Dialect vs. demographics: Quantifying LLM bias from implicit linguistic signals vs. explicit user profiles. *Proceedings of the 2026 ACM Conference on Fairness, Accountability, and Transparency (FAccT '26)*. https://doi.org/10.1145/3805689.3812419

The original study found that large language models refuse requests from explicitly Black-identified users at rates 7.5–8.27 percentage points above those observed for White-identified users submitting identical prompts — and that writing in African American Vernacular English (AAVE) without stating race nearly eliminates that penalty, a pattern the authors term the "dialect jailbreak."

**No new model inference is conducted here.** All statistics derive from the study's published tables, reported coefficients, and the publicly available BOLD dataset (Dhamala et al., 2021).

---

## Live Dashboard

🔗 **[View the interactive dashboard](https://yourusername.github.io/say-my-name-llm-bias)**

> Replace the URL above with your GitHub Pages link after deployment.

---

## What the Dashboard Shows

Five interactive panels, all grounded in verified published data:

| Panel | Contents |
|---|---|
| **Overview** | All six identity conditions at a glance — refusal rates, soft vs. hard refusal breakdown, headline statistics |
| **Refusal Rates** | Toggle conditions on/off; click any bar for the exact arithmetic derivation; step through the z-test (Z = 6.35, p < .001) interactively |
| **Odds Ratio Gap** | Why the paper's "400% increase in odds" claim requires qualification — marginal OR (1.56×) vs. GLMM conditional OR (4.19–8.01×), ICC variance decomposition |
| **Subadditivity** | Novel finding: the AAVE dialect jailbreak falls 7.41pp *below* what an additive model predicts — synergistic, not sequential, filter degradation |
| **BOLD Dataset** | 2,380-prompt stratified sample — domain and category composition |

---

## Key Findings

### 1 — Racial refusal disparity confirmed
Black-identified users face a **28.9% refusal rate** vs. **20.7%** for White-identified users submitting identical prompts. The gap (+8.27pp) is independently confirmed via two-proportion z-test (Z = 6.35, p < .001). 706 of 2,201 prompts flipped between refusal and compliance based solely on stated identity.

### 2 — The "400% odds" claim requires qualification
The paper's headline odds ratio derives from a GLMM conditional estimate inflated by extraordinary prompt-level random effect variance (σ² = 100.44, ICC = .97). The raw marginal odds ratio is **1.56×** — a confirmed, meaningful disparity, but not the fourfold figure that travels into policy summaries. The distinction matters for how findings translate into audit standards and legal frameworks.

### 3 — The dialect jailbreak is synergistic (novel finding)
The AAVE implicit condition (5.4% refusal) falls **7.41 percentage points below** the additive prediction of 12.77% — meaning the combined effect of removing the explicit racial keyword and substituting dialect outperforms what either signal alone predicts. Safety filters indexed on explicit identity keywords do not degrade gradually; they collapse more sharply when signals combine.

---

## Data Sources

- **Haq & Saldías (2026)** — published Table 4 raw counts, GLMM coefficient tables (Appendix A.4), reported AME values
- **BOLD dataset** — Dhamala et al. (2021); 2,380 stratified prompts across Gender, Race, Politics, Religion domains
- All arithmetic independently verified; no statistics fabricated or estimated beyond what published data support

---

## Repository Contents

```
├── llm_bias_dashboard.html   # Self-contained interactive dashboard (no build step)
├── README.md                 # This file
└── BOLD_stratified_sample_cleaned.csv   # 2,380 base prompts, 4 domains (optional reference)
```

The dashboard is a single HTML file. It has no dependencies beyond a D3.js CDN import — no npm, no build process, no server required.

---

## Deployment (GitHub Pages)

See [`SETUP.md`](SETUP.md) for step-by-step instructions to publish this as a live site.

---

## Citation

If you use this dashboard or the validation findings in your own work:

```
Booker, M. D. (2026). Say my name: How declaring Black identity triggers the safety
filters that writing Black does not [Secondary validation dashboard]. GitHub.
https://github.com/yourusername/say-my-name-llm-bias
```

---

## References

Booker, M. D. (2022). *Empowering, engaging, and equipping technology through acceptance* [Doctoral dissertation, University of the Cumberlands]. https://doi.org/10.13140/RG.2.2.13108.77441

Crenshaw, K. (1989). Demarginalizing the intersection of race and sex. *University of Chicago Legal Forum*, *1989*(1), 139–167.

Dhamala, J., Sun, T., Kumar, V., Krishna, S., Pruksachatkun, Y., Chang, K. W., & Gupta, R. (2021). BOLD: Dataset and metrics for measuring biases in open-ended language generation. *Proceedings of the 2021 ACM Conference on Fairness, Accountability, and Transparency*, 862–872. https://doi.org/10.1145/3442188.3445924

Haq, I., & Saldías, B. (2026). Dialect vs. demographics: Quantifying LLM bias from implicit linguistic signals vs. explicit user profiles. *Proceedings of FAccT '26*. https://doi.org/10.1145/3805689.3812419

Neuhaus, J. M., Kalbfleisch, J. D., & Hauck, W. W. (1991). A comparison of cluster-specific and population-averaged approaches for analyzing correlated binary data. *International Statistical Review*, *59*(1), 25–35.

---

## Integrity Note

This project operates under strict scholarly integrity standards. No citations are fabricated. No statistics are invented. All effect sizes and p-values are derived from published sources with full derivations shown. The dashboard is a visualization of independently verified findings, not a platform for advocacy claims beyond what the data support.

---

*Last updated: June 2026 · Purdue University Global*
