# **RISK ANALYSIS**


I have analyzed data from an online lending platform, Lending Club (www.lendingclub.com). 
The goal is to develop models to predict which loans are at risk of default. 
Such a model can then be used to devise investment strategies.
Lending Club (LC) offers an online platform for matching borrowers seeking loans and lenders looking to make an investment. With lower operational costs than traditional lenders (banks), such online lending platforms leverage technology, data and analytics to bring quicker and more convenient financing for individual and small business borrowers from investors looking for attractive investment yields. 
With increasing volumes, what started as peer-to-peer platforms for connecting individual borrowers and individual investors has today evolved to include institutional investors, hedge funds, etc. 
Also called marketplace lending or alternate lending, such fintech platforms have seen significant growth in recent years. It is estimated that in 2018, 38% of all personal loans in the US were issued through fintech firms, growing from 5% in 2013 11. 
Some estimate the global online lending market to grow from ~$42B in 2018 to ~$460B in 2022 22. Lending Club, a pioneer in fintech, is one of the largest online lending platforms, with over $50B in total loans issued till date 33.


# DATASET

LC issues personal loans between $1000 and $40,000 for 36 to 60 month durations.
Interest rates on these loans are determined based on a variety of information, including credit rating, credit history, income, etc. 
Based on this, LC assigns a grade for each loan, ranging from A for safest loans to G for highest risk; subgrades are also assigned within each grade. Loans are split into $25 notes, which investors can purchase. 

I will use a data extract on loans issues in the first 6 months of 2015.
The data carries information on 36 month loans, which will all have completed their term by now. 
Some loans were fully paid back, while others were “charged off” (defaulted).

Dataset has 120791 entries with 145 columns. I have done a complete data analysis and data engineering on this dataset.
I have removed variables which are not available at the time of loan application. Dataset was highly imbalanced. So I have used SMOTE technique on the minority class to balance the dataset.

# DATA MODELING

I have created 3 models using 66 independent variables. As the dataset was higly imbalanced, I have used PR curve and F1 score for model evaluation.

### 1. Decision Tree
DT model's prediction was my baseline. This model gave an F1 score of 0.86. The PR curve is shown below.
![alt text](https://github.com/anchit23/LendingClub/blob/master/PRcurve_DT.png)
This shows the model is not performing well.
### 2. Random Forest
My second model is Random Forest. This model performed better than DT with the F1 score of 0.91. The PR curve of the model is shown below
![alt text](https://github.com/anchit23/LendingClub/blob/master/PRcurve_RF.png)
### 3. XGBOOST
My last model is XGboost. This model performed best with the F1 score of 0.93. The PR curve of the model is shown below.
![alt text](https://github.com/anchit23/LendingClub/blob/master/PRcurve_XG.png)







