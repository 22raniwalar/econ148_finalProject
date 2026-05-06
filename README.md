# Econ 148 Final Project
## Group Members: Karina Parikh, Alex Chow, Ria Raniwala, Mona Abai, and Nithika Valluri
## Track B - Paper Reproduction: "The Fake News Effect: Experimentally Identifying Motivated Reasoning Using Trust in News" by Michael Thaler

This project replicates the experimental findings from Michael Thaler’s 2024 study on politically motivated reasoning. The study uses a novel experimental design to identify motivated reasoning by analyzing how subjects assess the truthfulness of news that either aligns with (Pro-Party) or contradicts (Anti-Party) their political motives.  


### 1. Prerequisites
To run the replication script (fake_news_econ148_proj.ipynb), ensure you have the following installed:

- Python 3.x

- Libraries: pandas, numpy, matplotlib, seaborn, scipy.

- Econometric Packages: linearmodels and pyfixest (used for fixed-effects regressions and instrumental variables).

### 2. Dataset Setup
The replication requires the experimental dataset, typically named cleaned_data.csv.

- Data Path: The notebook is configured to load data from a Google Drive path: /content/drive/MyDrive/Econ148_project_data/cleaned_data.csv.
- to run without a Google Drive shortcut, the original cleaned dataset can be downloaded via https://www.openicpsr.org/openicpsr/project/183845/version/V1/view?path=/openicpsr/183845/fcr:versions/V1/fake-news-effect_code&type=folder

Variables: The dataset contains 331 columns, including subject IDs, treatment groups, political leanings, and veracity assessments (prob_true).

### 3. Replication Steps
#### Step 1: Environment Preparation
Run the initial cells to mount your Google Drive and install the necessary econometric libraries (linearmodels, pyfixest) that are not standard in most environments.
- If the dataset isn't in your Google Drive, download the dataset and load it in using:
  - data = pd.read_csv('file path'/cleaned_data.csv')

#### Step 2: Motives Setup (Table 1)
The notebook manually defines the "Pro-Democrat" and "Pro-Republican" motives for the nine politicized topics (e.g., US crime, Climate change, Gun reform) to match Table 1 of the paper.

#### Step 3: Veracity Assessments (Figure 1)
The script filters the data for politicized news and generates an Empirical Cumulative Distribution Function (ECDF). This replicates Figure 1, demonstrating that subjects trust Pro-Party news significantly more than Anti-Party news.

#### Step 4: Motivated Reasoning Analysis (Figure 2)
The notebook calculates assessments to show that:
1. Pro-Party news is rated as more truthful than neutral topics.
2. Anti-Party news is rated as less truthful than neutral topics.
3. These effects are more pronounced in partisan subjects compared to moderates.

### 4. Key Findings to Verify
- The Fake News Effect: Bayesians should find the news uninformative (assessment = 0.5), but the paper finds Pro-Party news is rated ~9 percentage points more likely to be true than Anti-Party news.
- Confidence Intervals: The study explores how motivated reasoning leads to overprecision, where subjects' 50% confidence intervals often fail to contain the true answer.


Reference: _Thaler, M. (2024). The Fake News Effect: Experimentally Identifying Motivated Reasoning Using Trust in News. American Economic Journal: Microeconomics._

