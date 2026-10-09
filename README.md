# AI Zero to Hero

Practical notebooks and worked exercises from the **AI Zero to Hero** short course: a two-day, hands-on introduction to data analysis and machine learning in Python. The course moves from exploring data, through unsupervised learning (clustering), to supervised learning (classification and regression), and ends with a practical assessment that combines all three.

## Course at a glance

| Day | Session | Topic | Notebook |
|---|---|---|---|
| 1 | Lab 1 | Getting started: Google Colab, Google Drive, Python basics, a first analysis of `mtcars` | [Day1_Lab1_Introduction_Colabs](Notebooks_local/Day1_Lab1_Introduction_Colabs.ipynb) |
| 1 | Lab 2, Part 1 | Descriptive statistics and hypothesis tests (drug costs, West Nile virus data) | [Day1_Lab2_Exploring_Data_Part1](Notebooks_local/Day1_Lab2_Exploring_Data_Part1.ipynb) |
| 1 | Lab 2, Part 2 | Graphical data exploration | [Day1_Lab2_Exploring_Data_Part2](Notebooks_local/Day1_Lab2_Exploring_Data_Part2.ipynb) |
| 1 | Lab 3 | Clustering: distances, hierarchical clustering, k-means | [Day1_Lab3_Clustering](Notebooks_local/Day1_Lab3_Clustering.ipynb) |
| 2 | Lab 5 | Classification | [Day2_Lab5_Classification](Notebooks/Day2_Lab5_Classification.ipynb) |
| 2 | Lab 6 | Regression and predictive modelling | [Day2_Lab6_Regression](Notebooks/Day2_Lab6_Regression.ipynb) |
| – | End of course | Practical assessment: EDA, prediction and clustering on one dataset | [End_Of_Course_Assessment_Diabetes_Fixed](Notebooks_local/End_Of_Course_Assessment_Diabetes_Fixed.ipynb) |

Notebook file names keep the instructors' numbering (Labs 1–3 and 5–6).

## What each session covers

### Day 1: Exploring data and unsupervised learning

**Lab 1: Introduction to Google Colab**
- Colab basics: code cells and text cells, running cells in order, Markdown.
- Mounting Google Drive and creating a course folder structure.
- Variables and calculations, importing `numpy`, `pandas` and `matplotlib`.
- Loading and saving CSV and Excel files.
- A complete mini-analysis of `mtcars`: summary statistics, the highest-horsepower car, a scatter plot of fuel consumption against weight, a vehicle-size category with `pd.cut`, and saving the modified data and figure.

**Lab 2, Part 1: Descriptive statistics and tests**
- Drug costs: mean, median, variance, standard deviation, quartiles and IQR, shown with a box plot, histogram and density plot.
- West Nile virus surveillance data: dates, counts and proportions, group means, age groups and cross-tabulation.
- Chi-square and Fisher's exact tests, the odds ratio, and how to read a p-value.

**Lab 2, Part 2: Graphical exploration**
- Choosing a graph by variable type: bar charts, pie charts, histograms, box plots, scatter plots, line plots and maps.
- Customising colour, shape and labels; faceting into panels.
- Checking data types, summaries and missing values before plotting.
- Reading a graph carefully: bin width, scale and grouping can change the picture, and association is not causation.

**Lab 3: Clustering**
- Euclidean distance and why variables must be standardised first (z-scores).
- Hierarchical clustering with `scipy`: linkage, dendrograms, and cutting the tree into clusters.
- K-means clustering on Iris and `mtcars`: choosing `k` with the elbow plot and silhouette score.
- Comparing clusters with known labels (crosstab and Adjusted Rand Index), and the limitations of clustering.

### Day 2: Supervised learning

**Lab 5: Classification**
- Logistic regression, the sigmoid function and regularisation (`C`).
- Classification thresholds, confusion matrices, accuracy, recall, precision and F1.
- ROC curves and AUC.
- Multiclass classification with Iris, feature selection, decision trees and random forests, permutation importance.
- Cross-validation, and overfitting versus underfitting as tree depth grows.

**Lab 6: Regression and predictive modelling**
- Simple and multiple linear regression on the scikit-learn diabetes data.
- Evaluation with R², MAE, MSE and RMSE; residual plots.
- L1 versus L2 loss and the effect of outliers; gradient descent and convergence.
- Polynomial regression and overfitting; k-fold cross-validation.
- Regression trees and pruning, bootstrapping, bagging and random forests, feature importance, and prediction bias.

### End-of-course assessment

A practical on the diabetes dataset that brings the course together: exploratory data analysis, regression and classification models, hierarchical clustering with dendrograms, and a short written summary.

## Datasets

| Source | Dataset | Used in |
|---|---|---|
| `Data/` | `drugcosts.csv`, `drugcosts.xlsx`: costs of 84 drugs | Lab 1, Lab 2 Part 1 |
| `Data/` | `wnv.csv`: West Nile virus surveillance records | Lab 2 Part 1 |
| `Data/` | `mtcars.csv`: 32 cars, 11 design and performance variables | Lab 1, Lab 2 Part 2, Lab 3 |
| `Data/` | `iris.csv`: 150 flowers, 3 species (the notebooks load Iris from scikit-learn instead) | Course data folder |
| `Data/` | `updated_costs.csv`, `updated_costs2.csv`: files written by the Lab 1 exercises | Lab 1 |
| scikit-learn | Breast cancer (569 samples), Iris, Diabetes (442 samples), synthetic `make_classification` data | Labs 3, 5, 6 and the assessment |

## Repository layout

```
Notebooks/        Original notebooks, written for Google Colab.
                  The Day 2 labs need no Google Drive, so they run locally as they are;
                  the completed Day 2 exercises are in this folder.
Notebooks_local/  Notebooks adapted to run locally with Jupyter (no Google Drive): Day 1, the Day 2 copies
                  and the assessment. It has its own copy of Data/ and a Lab1_workspace/ folder for the
                  files Lab 1 writes. The completed Day 1 exercises are in this folder.
Data/             Datasets used by the notebooks.
```

Slides are not part of this repository.

## Running the notebooks

### Option 1: Google Colab (as taught)

1. Open [colab.research.google.com](https://colab.research.google.com) and upload a notebook from `Notebooks/`.
2. Create the Drive folders the notebook expects and upload the files from `Data/` (the Day 1 notebooks read from `AI_Zero_To_Hero/...` and `Stuff/` on your Drive).
3. Run the cells from top to bottom and approve the Drive access request.

### Option 2: Locally with Jupyter

```bash
pip install notebook matplotlib seaborn scikit-learn scipy plotly openpyxl
cd Notebooks_local
jupyter notebook
```

Use the notebooks in `Notebooks_local/` for Day 1 and the assessment. They read from the local `Data/` folder and save files next to the notebook instead of using Google Drive. The Day 2 labs run from either folder, and the completed Day 2 versions are in `Notebooks/`. Developed with Python 3.12 and scikit-learn 1.9.

## Key ideas from the course

- Look at the data (summaries, missing values, plots) before modelling.
- Put variables on a comparable scale before using distance-based methods such as clustering.
- Judge a model on data it has not seen: use a test set or cross-validation, not training error.
- More flexible models fit the training data better but can overfit; compare the train and test gap.
- Accuracy is not enough: look at recall, precision and the cost of each kind of error, and treat the classification threshold as a decision.
- Feature importance and correlation describe what a model uses, not what causes an outcome.
- Results depend on the analytical choices made (features, scaling, distance, number of clusters), so state them.

## Credits

The course notebooks and datasets are the instructors' course materials. This repository is a learner's workspace, with worked answers added to some notebooks in cells labelled "My answer" or "My answers".
