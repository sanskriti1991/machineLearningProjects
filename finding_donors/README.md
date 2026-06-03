# Finding Donors: A Retrospective

I built this as a Udacity student in 2018. I thought I was done. I wasn't.

## What This Project Was Originally

A Udacity machine learning nanodegree project training a supervised learning model to predict whether someone earns more than $50k per year as a proxy for charity donation likelihood for a fictional organization called CharityML. The model scored 85% overall accuracy. Project completed, grade received, notebook filed away.

## The Dataset

UCI Adult Income dataset extracted from the 1994 US Census by Barry Becker. Binary classification task predicting whether income exceeds $50k per year. Still available at UCI Machine Learning Repository.

## What I Did Not Know

The $50k threshold corresponds to the 76th income percentile overall in 1994, but the 88th percentile for Black Americans and 89th percentile for women. The model did not learn who donates. It learned who 1994 America paid well.

## The Research Connection

This dataset appeared in hundreds of research papers from 2006 to 2019 spanning AI fairness, privacy preservation, model debugging, and distributed systems. UC Berkeley researchers published Retiring Adult in 2021 at NeurIPS calling for the dataset to be retired and replaced.

## What the Original Evaluation Missed

Overall accuracy hides subgroup disparities. Asian-Pac-Islander males predicted as likely donors at 32%. White males at 26%. Black females at 4%. American Indian females at nearly 0%. False positive rates and false negative rates vary significantly across demographic groups.

## What GitHub Copilot Helped Fix

- Identified deprecated sklearn imports from cross_validation and grid_search modules and updated to model_selection.
- Fixed Python 2 print statement syntax throughout.
- Fixed integer division bug in visuals.py causing IndexError.
- Generated the fairness audit code from an inline comment.
- Produced the plain English fairness summary from the results.

## How to Run the Notebook

Clone the repository, install the required dependencies, and run `finding_donors.ipynb`. Use the following command to install dependencies:

```bash
pip install numpy pandas scikit-learn matplotlib scipy
```

## What the Demo (index.html) Shows

An interactive form to input census features and see how the model predicts donation likelihood. A fairness warning is displayed for demographic groups with known prediction disparities. Charts show prediction rates, false positive rates, and false negative rates by demographic group. Additional visualizations include the $50k threshold context chart and links to all referenced research papers.

## Original Assignment

The original Udacity assignment instructions are preserved in `ASSIGNMENT.md` for reference.

## Research Papers Referenced

- [The What-If Tool (Wexler et al. 2019)](https://api.semanticscholar.org/CorpusID:195848259)
- [Paired-Consistency (Horesh et al. 2019)](https://api.semanticscholar.org/CorpusID:199472592)
- [Automated Directed Fairness Testing (Udeshi et al. 2018)](https://api.semanticscholar.org/CorpusID:49559520)
- [Automated Data Slicing (Chung et al. 2018)](https://api.semanticscholar.org/CorpusID:57573817)
- [Helix Accelerating ML (Xin et al. 2018)](https://api.semanticscholar.org/CorpusID:51922545)
- [Confidence-Based Fairness (Fish et al. 2016)](https://api.semanticscholar.org/CorpusID:16135452)
- [Debugging ML Tasks (Chakarov et al. 2016)](https://api.semanticscholar.org/CorpusID:16479676)
- [Classification Without Discrimination (Kamiran and Calders 2011)](https://api.semanticscholar.org/CorpusID:14637938)
- [Retiring Adult (Ding et al. UC Berkeley 2021)](https://arxiv.org/abs/2108.04884)
