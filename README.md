# Exploration of Prosper Loan Dataset
## by Yuta Sekiguchi


## Dataset

We analyze the dataset from Prosper, which consists of the information on 113937 loans with 81 variables, including the loan amount, the period of loans, the borrowers' data and so on. The dataset can be found [here](https://www.google.com/url?q=https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv&sa=D&ust=1554484977406000). The variable definitios are available [here](https://www.google.com/url?q=https://docs.google.com/spreadsheet/ccc?key%3D0AllIqIyvWZdadDd5NTlqZ1pBMHlsUjdrOTZHaVBuSlE%26usp%3Dsharing&sa=D&ust=1554484977407000).

## Summary of Findings

Among 81 variables, we chose 12 features. They include the basic information on the loans, such as `BorrowerAPR`, `LoanOriginalAmount`, and `Term` and the borrowers' data, such as `StatedMonthlyIncome`, `ProsperRating (Alpha)`, and `Occupation`. In particular, `BorrowerAPR` is of our great interest, since a proper amount of APRs is essential not only in order to make the repayment of loans, but also in order for the Prosper to get returns as efficiently as possible. Moreover, we were interested how this variable is correlated with the amount of loans and the length of loan periods, as well as the customer's rating scores and so on.

After surveying the distributions of variables, we performed bivariate explorations depending on the data types of two variables. As a result, the `BorrowerAPR` seemed to be negatively correlated with `LoanOriginalAmount` and `StatedMonthlyIncome` whilst positively correlated with `DebtToIncomeRatio`. Moreover, the major range of APR values (i.e. IQR) was negatively correlated with both `ProsperRating (Alpha)` and `ProsperScore`.

Next, we carried out the multivariate analysis to find more details of correlations of APRs with other features. For each class of `ProsperRating (Alpha)`, the positive correlation of APRs with `DebtToIncomeRatio` got less manifest. Also, the correlation between APRs and `LoanOriginalAmount` changed depending on Prosper rating scores. While the correlation became positive for high scores (`AA` and `A`), we found negative correlations for the rest of scores. According to the slopes of fitting lines, the negative correlation got slightly stronger as the score got lower.

Moreover, with Prosper rating scores varied, different behaviors of statistics of APRs were observed in terms of `Term`. Unlike in the bivariate analysis, the range of APR values got higher as the Prosper scores got lower. In addition, the features of boxes, such as the values of Q2 and the IQRs also became different by varying the length of terms for each rating score. For example, Q2 got larger as the duration of loan periods got longer for high scores (`AA` and `A`), but this relation was reversed for low scores.

Lastly, let us mention a relationship between `LoanOriginalAmount`, `ProsperRating (Alpha)`, and `Term`. When comparing only `LoanOriginalAmount` and `Term`, the boxes for `AA`, `A`, `B`, and `C` looked similar while the other boxes are located in lower positions, taking lower APRs. However, for each class of rating scores, the statistics of APRs got different depending on the length of loan periods. As the score got lower, the median and the IQRs of boxes for `36` and `60` months got shunk. On the other hand, the median and the IQR for `12` months did not change much across the scores. More interestingly, as for higher scores `AA`, `A`, and `B`, their boxes `36` months took the Q1 around `5K`, the median around `10K`, and the Q3 around `15K`. Also, the boxes `60` months took the Q1 around `10K`, the median around `15K`, and the Q3 around `20K`. These values matched the loan values, where spikes were found in the univariate exploration.

## Key Insights for Presentation

For the presentation, we will focus on the features of the APR and its relations to other variables which showed visible correlations. As for the bivariate analysis, we will emphasize the relations of the APR to numerical variables `LoanOriginalAmount`, `StatedMonthlyIncome`, and `DebtToIncomeRatio` depicted in the heat map. Moreover, we explain how the APR is related to `ProsperRating (Alpha)`, and also how the `LoanOriginalAmount` and `ProsperRating (Alpha)` were correlated. Then we focus on the correlations of the APR with `LoanOriginalAmount`, `ProsperRating (Alpha)` and `Term`.
