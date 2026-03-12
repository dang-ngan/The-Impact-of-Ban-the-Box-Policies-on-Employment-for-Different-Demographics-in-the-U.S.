# The Impact of "Ban the Box" Policies on Employment for Different Demographics in the U.S.

## Project Overview
This project investigates the heterogeneous impacts of **"Ban the Box" (BTB)** legislation — specifically the **2018 California Fair Chance Act** — on employment outcomes for low-skilled workers. 

Utilizing a **Difference-in-Differences (DiD)** framework, the study compares employment probability changes in California (Treatment) against Texas (Control) across various racial and gender demographics. The core objective is to determine if removing criminal history inquiries from initial job applications successfully lowers barriers for marginalized groups or leads to unintended **"statistical discrimination."**

***

## Key Findings
| Demographic Group | Coefficient ($\beta$) | Impact | Significance |
| :--- | :---: | :---: | :---: |
| **Aggregate (Non-College)** | `0.0013` | **+0.13%** | $p < 0.01$ |
| **Black Workers** | `-0.0851` | **-8.51%** | $p < 0.01$ |
| **White Workers** | `0.0226` | **+2.26%** | $p < 0.01$ |
| **Male Workers** | `0.1104` | **+11.04%** | $p < 0.01$ |
| **Female Workers** | `-0.1107` | **-11.07%** | $p < 0.01$ |

* **Marginal Aggregate Gain:** A small but statistically significant increase in employment for the general non-college population.
* **Racial Heterogeneity:** Evidence of statistical discrimination; while White employment rose, Black workers experienced a significant decrease in employment probability.
* **Gender Divergence:** A sharp contrast between genders, with significant gains for males but equal losses for females, suggesting job substitution within low-skilled sectors.



***

## Methodology
The analysis utilizes **Weighted Least Squares (WLS)** regression on CPS microdata (2016–2019).

### Econometric Specification
$$Employed_{it} = \alpha + \beta(Treat_{i} \times Post_{t}) + \gamma X_{it} + \delta_{s} + \theta_{t} + \epsilon_{it}$$

**Where:**
* **$Treat_{i} \times Post_{t}$**: The interaction term (Difference-in-Differences) representing the policy effect.
* **$X_{it}$**: Vector of individual-level controls (age, sex, race, and education).
* **$\delta_{s}$ and $\theta_{t}$**: State and Year-Quarter fixed effects to control for geographic and temporal trends.

***

## Data Sources
* **Primary Data:** Current Population Survey (CPS) data via [IPUMS](https://cps.ipums.org/cps/).
* **Target Population:** Non-college-educated adults (Ages 25–54).
* **Timeframe:** 2016 Q1 – 2019 Q4.

> **Note on Data Access:** Due to file size constraints, the raw data is hosted externally. Please download the dataset from **[this link](https://drive.google.com/file/d/1hLCHJKpVdDVQc4wInAudFaI0V5zszkpe/view?usp=sharing)** and place it in the root directory as `data_ban_the_box.csv`.

***

## Repository Structure
| File Name | Description |
| :--- | :--- |
| [📂 Ban_the_Box_Impact.ipynb](Ban_the_Box_Impact.ipynb) | **Main Analysis:** Data cleaning, WLS regressions, and all Python-based visualizations. |
| `results_data.zip` | Archive containing all CSV result outputs for reproducibility. |
| `tableau_results_subgroup_did.csv` | Regression results for the primary aggregate sample. |
| `tableau_results_racial_impact.csv` | Coefficients for racial heterogeneity analysis. |
| `tableau_results_gender_impact.csv` | Coefficients for gender-based substitution effects. |
| `tableau_results_full_did.csv` | Comprehensive results from the full high-dimensional model. |

***

## How to Reproduce
1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/dang-ngan/The-Impact-of-Ban-the-Box-Policies-on-Employment-for-Different-Demographics-in-the-U.S..git](https://github.com/dang-ngan/The-Impact-of-Ban-the-Box-Policies-on-Employment-for-Different-Demographics-in-the-U.S..git)

2.  **Install Dependencies:** Ensure you have `pandas`, `statsmodels`, `matplotlib`, and `seaborn` installed.

3.  **Download Raw Data:** Download `data_ban_the_box.csv` from the link provided in the Data Sources section and place it in the project root.

4.  **Extract Results:** Unzip `results_data.zip` to access the regression tables.

5.  **Run the Analysis:** Open and execute the cells in the `.ipynb` file.
