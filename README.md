![](RackMultipart20210828-4-ac3ndh_html_3f2a21e1b28b13b9.gif)

# Covid-19

Submitted By: Sara k. Chandio

![](RackMultipart20210828-4-ac3ndh_html_700dc6d1d89c2a27.gif)

![](RackMultipart20210828-4-ac3ndh_html_f8aaa488af7ece8.gif)


**Covid-19**

In the current state of pandemic, where everyone is looking forward to getting vaccine and move ahead in normal life. It is a matter of concern to know the characteristics of people who need to get vaccine first. This project is based on this idea and attempts to answer the question _&quot;What are the demographics of covid-19 patients need to get Vaccinated first?&quot;._ Following are the objectivesdesigned to achieve through this project.

_ **Objectives** _

1. To classify covid-19 Patients into Dead/ Not Survived and Survived.
2. Profiling not Survived class of Covid-19 Patients based on their demographics.
3. To rank records of Covid-19 patients with highest propensity of not surviving.
4. Identify records with significant demographic determinants.

The _ **Data used for analysis is obtained** _ from centers of Disease Control and prevention website [CITATION Cen20 \l 1033]. The original data was of around three million observations and eleven variables. The subset of twenty thousand records was extracted with the same proportion of Yes (6%) and No (94%) of outcome variable in the original data refer Table:1; dataset as per outcome variable ratio in original data in Appendix.

_ **Clean and Prepressing** _ of data was done mainly through bar chart and pivot table. First, str function and summary statistics was run to explore the characteristics of variables and data. All variables in the dataset were categorical with many levels. There was not any duplication of records. Secondly, with the help of bar chart and pivot tables of each predictor variable with outcome variable; the frequency of levels of variables was determined. Refer Figure:1; Summary statistics of variables in Appendix.

Two approaches were used to handle missing value. First, Variables with missing values more than sixty percent were deleted and levels with less percentage of missing values were included into levels with highest frequencies. Refer Table: 2&amp;3 of missing values and Unknown values

_ **Dimension reduction** _ was done based on percentage of missing values and exhaustive search. Two columns with more than 60 % missing values were deleted. Transformed Race and ethnicity combined variable with 8 categories into Two variables, Race with 4 categories and Ethnicity with two levels. Reduced Age variable categories from 8 to 5 and few columns from 2 to 1 like- sex, current status, death, Ethnicity, and onset date. Transformed on set date column into binary variable 1= showed symptom and 0= no symptoms.

refer _ **Table:2** _ for missing value percentage in those columns in Appendix. At the end of data cleaning and processing process the new dataset of 20,000 records with 9 variables (excluding dummy variables).

The final data set have 8 predictors namely- Symptom date, case conformity, date of case recorded, hospitalized, gender, ethnicity, race and age and death outcome variable. Age and Race variable has two variants, one with 2 level and other with multiple levels. Created dummy variables and kept levels with lowest frequency as reference. While coding variables as binary, assigned 1 to levels with highest frequency. refer _ **Table:4** _ for Data Dictionary in Appendix. The High frequencies of levels as per predictor variables were as for Age group 20-39 and 40-59. Gender female, Races Others, Ethnicity as Non-Hispanic, in the month of July majority of cases were recorded. Refer **Figure 2.1, 2.3, 2.4, and 2.4** in Appendix. Overall, the ratio of no (Survived) class is high in data set. Predictors as per outcome variable is shown in **Figure 3:** Predictors as per outcome variable in Appendix

Four data mining tasks are determined as objectives of this project. Those tasks are 1) Classification of Covid-19 patients into Survived and Not survived class, 2) Profiling not Survived class of Covid-19 Patients based on their demographics, 3) To rank records of Covid-19 patients with highest propensity of not surviving and 4 ) Identify 3 records with significant demographic determinants.

Final data set was divided into two subsets on random sample. Training dataset represents sixty percent of records (12,000 observations) used for building models and rest forty percent of records represents validation dataset (8,000 observations) used to evaluate predictive performance of built models.

Two techniques have been used in this project to undertake the task defined for answering main question. Those two techniques are _**Logistic Regression and K-NN (K nearest neighbor)**_. Logistic regression helps in classification, profiling and ranking of records. Whereas, K-nearest neighbor was used to identify 3 sample records considering significant predictors.

Three logistic models were developed on training data set for classification, profiling and ranking of records. Refer **Table:5; Logistic Models**

_ **First Logit Model** _ to predict outcome variable (Death) into survived and not survived class, with all nine predictors (taking Age variable with 5 levels and Race with four levels). The output summary showed all five levels of age (19 &amp;below, 20-39 years, 40-59 years, 60- 79 years and 80 and plus years) and race levels dummy variables named as Black and white insignificant with P \&gt;0.05. rest of the five predictors symptoms, case status, gender, hospitalized, ethnicity and one dummy variable of race Other came significant with negative coefficients -1.2057, -1.2834, -0.5591, -2.3343, -0.871 and -0.7807 respectively. Refer **figure 5&amp;6:** Summary output and Confusion matrix of Logit Model 1

Second Logit Model to classify outcome variable replaces Age variable of 5 levels with Age variable of 2 levels (60 and below &amp; 60 and above) along with rest of the predictors. The outcome summary showed two dummy variables of race (Black and White) insignificant but all remaining predictors significant. All other coefficients were same except of Age. Age in this model showed significant positive coefficient (2.75487). **Refer figure 7&amp;8:** Summary output and Confusion Matrix of Logit Model 2

Third Logistic Model was suggested by exhaustive search. It used seven predictors Symptoms, gender, case status, hospitalized, ethnicity, Age (2 levels) and race (two levels) to classify outcome variable Death. The outcome summary represented all predictors significant age with positive coefficient and rest with negative coefficients. 2.77298, -1.32332, -0.39720, -1.20756, -2.45341, -0.73291 and -0.75948 respectively.

The results reflect that the patients those feel symptoms are less likely to not survived then the patients those does not feel symptoms. Its odds are 0.26624913, keeping all others constant. Coefficients of case status predictors shows that the patients with lab confirmed cases are less likely to not survive than probable conformed. With odds 0.29892580 considering all other variables as constant. Coefficients of gender with odds 0.67220113 reflects female patients less likelihood of not surviving than male patients taking all other predictors constant. Coefficients and odds 0.08599985 of hospitalized show that patients those are not hospitalized are less likely to not survive than those who are hospitalized. Keeping all other constant. **Refer figure 9 - 12:** Summary output, coefficients &amp; odds and Confusion matrix of Logit Model 3

Before selecting final model, confusion matrices were compared. Model with highest balance accuracy and accuracy rate was selected. (Accuracy 0.948, Balance Accuracy 0.78008), (Accuracy 0.9469, Balance Accuracy 0.7990), and (Accuracy0.947, Balance Accuracy 0.82128) respectively. Third model was selected for prediction at 0.7 cutoff. Accuracy, sensitivity and specificity was compared on cutoffs from 0.1 to 0.9, its predictive performance was checked through decile chart and accuracy chart. Refer **figure: 11** Model cutoff selection in Appendix.

**Logistic Regression Equation**

_**P (death=Not Survived) =1/1+e^- [-2.272 -1.323(symptom) -0.397 (Gender) -1.207(Case Status) -2.453 (hospitalized) - 0.732(Ethnicity) -0.759 (Race2) + 2.772 (AGE1)]**_

Confusion Matrix of selected model run on validation dataset reflected models Accuracy 0.947, Error Rate = 5.3%, Sensitivity 0.69167, Specificity 0.95089 and Balanced Accuracy 0.82128. The model predicted class of interest (not survived) correctly 83 cases and 7493 case of survived class. The model incorrectly predicted 387 cases as class of interest and 37 cases as survived class. These results helped in achieving objective of classifying records into survived and not survived class along with profiling significant determinants of not survived class. Odds 0.48050786 and coefficients of ethnicity shows that non-Hispanic are less likely to not survive than Hispanic. Keeping all others constant. Negative coefficient and odds 0.46791004 of race variable show that other races have less likelihood to not survive than black, white and Asians. Considering all others as constant. Whereas positive coefficient and odds 16.00619994 of age variable represents that patients of age 60 years and above are more likely to not survive than patients of age below 60 years. Considering all other variables constant.

Furthermore, for evaluating predictive performance of selected model lift chart and decile chart was conducted on validation data. The decile chat helps in getting the records with highest propensity of response in 10 percent. The decile chart of the model shows that the first 10 percent of the records generate 6.7 times more response than it would on selecting at random. The dotted diagonal line on lift chart shows the base line of Naïve rule, the lift curve away from benchmark shows model is doing well on separating high values from low values. It helps in looking for set of observations that gives the highest predictive values. With the help of lift chart and decile chart the third objective of data mining task is achieved. Refer **figure 13 &amp;14** model lift chart and decile chart

Second technique – K-NN was used to find sample records with determinants suggested significant through Logistic model. A table of Number of K accuracy was generated to choose the right number of K. I chose K=3 as per highest accuracy in odd number. Randomly selected a line from validation data with same determinants suggested significant by logistic model and run the logarithm of K-NN. The result showed exact 3 records and classified them as not survived. Refer **figure 15-16** for K-NN Summary, selected rows and K-Accuracy table in Appendix.

Patients with characteristics like, age above 60 years, gender male, ethnicity Hispanic, race black, white, &amp; Asian, hospitalized, with probably confirmed case and feeling no symptoms are at high risk and need to get vaccine first.

![](RackMultipart20210828-4-ac3ndh_html_6122d6056a7c2bd5.gif) ![](RackMultipart20210828-4-ac3ndh_html_e1e27af6a5c1062e.gif)

Figure 2.1, 2.3, 2.4, and 2.4 Frequency Bar Charts

Figure 3: All Predictors as per Outcome variable Classes

Figure: 4; Dummies

figure 5&amp;6: Summary output and Confusion matrix of Logit Model 1

figure 7 &amp;8: Summary output and Confusion Matrix of Logit Model 2

figure 9 - 12: Summary output, coefficients &amp;odds, cutoff accuracy and Confusion matrix of Logit Model 3

figure 13 &amp;14 model lift chart and decile chart

figure 15-16 for K-NN Summary, selected rows and K-Accuracy table

Table:1; dataset as per outcome variable ratio in original data in Appendix.

Table: 2&amp;3 of missing values and Unknown values

Table :4; Data Dictionary

**Table:5; Logistic Models**

Table :1; Dataset as per outcome variable ratio in original data

| _ **Outcome variable** _ | _ **Original data** _ | _ **%** _ | _ **New data** _ |
| --- | --- | --- | --- |
| _ **Yes** _ | 158,255 | 6 | 1,200 |
| --- | --- | --- | --- |
| _ **No** _ | 2,662,955 | 94 | 18,800 |
| _ **Total** _ | 2,821,210 | 100 | 20,000 |

_ **Table:2** _ for missing value percentage in each column

| _ **Death** _ | _ **Column1** _ | _ **medcond\_yn** _ | _ **icu\_yn** _ |
| --- | --- | --- | --- |
| _ **No** _ | Missing | 11167 | 11690 |
| --- | --- | --- | --- |
|
 | No | 2899 | 3455 |
|
 | Unknown | 2062 | 3514 |
|
 | Yes | 2672 | 141 |
| _ **Yes** _ | Missing | 525 | 544 |
|
 | No | 21 | 117 |
|
 | Unknown | 159 | 362 |
|
 | Yes | 495 | 177 |
| _Total_ |
 | 20000 | 20000 |
| _Percentage_ |
 | 70% | 81% |

| **Variables** |
 | **Missing** | **Unknown** |
| --- | --- | --- | --- |
| **cdc\_report\_dt** |
 |
 |
 |
| --- | --- | --- | --- |
| **onset\_dt** |
 |
 |
 |
| **pos\_spec\_dt** |
 |
 |
 |
| **sex&quot;** | Male=9477Female=10434 | 28 | 61 |
| **current\_status** | Laboratory confirmed =19170Probable=830 | Null | Null |
| **age\_group** |
 | Null | 17 |
| **Race.and.ethnicity..combined.** |
 | Null | 6073 |
| **icu\_yn** | No=3572Yes=318 | 12234 | 3876 |
| **hosp\_yn** | No :14128Yes : 2289 | 1455 | 2128 |
| **death\_yn** | No :18800Yes: 1200 | Null | Null |
| **medcond\_yn&quot;** | No =2920Yes = 3167 | 11692 | 2221 |

Table :4; Data Dictionary

| _ **variable** _ | _ **Description** _ | _ **Details** _ |
| --- | --- | --- |
| _ **onset\_dt** _ | On set date to report symptomsPredictor- Factor -2 categories | 1= symptoms0=no symptoms |
| --- | --- | --- |
| _ **current\_status** _ | Case statusPredictor- Factor -2 categories | 1= lab confirmed 0=probable |
| _ **hosp\_yn** _ | Been hospitalized Predictor- Factor -2 categories | 1= not hospitalized0= hospitalized |
| _ **death\_yn** _ | Died or not outcome- Factor -2 categories | 1= died0= survived |
| _ **Ethnicity** _ | Predictor- Factor -2 categories | 1= Non-Hispanic0= Hispanic |
| _ **Gender** _ | Gender of Patients Predictor- Factor -2 categories | 1= Female0= Male |
| _ **Months** _ | February -October |   |
| _ **Race** __ **Race 2** _ | Predictor- Factor -4 categoriesPredictor- Factor -2 categories | Black, White, others &amp; ref=Asians1= Others0= White/Asians/Black |
| _ **Age** __ **Age 1** _ | Predictor- Factor -5 categoriesPredictor- Factor -2 categories | 19 &amp; below Ref20-39, 40-59, 60- 79, 80 +1= 60 years &amp; above0= 60 years &amp; below |

**Figure 2.1, 2.2,3.3,2.4 and 2.5**

![](RackMultipart20210828-4-ac3ndh_html_f3b5a6ba518ec634.jpg) ![](RackMultipart20210828-4-ac3ndh_html_4199b7b3c1b81755.png)

![](RackMultipart20210828-4-ac3ndh_html_c60c815363326c09.png) ![](RackMultipart20210828-4-ac3ndh_html_be3ea698a91619e1.png)

![](RackMultipart20210828-4-ac3ndh_html_53404de1c3999b0b.png)

**Figure 3: All Predictors as per Outcome variable Classes**

![](RackMultipart20210828-4-ac3ndh_html_f362b5e0863c16de.gif)

**Figure : 4; Dummies**

![](RackMultipart20210828-4-ac3ndh_html_210b3e2aa71e8cd1.png)

**Table:4; Logistic Models**

| Model | variables | Significance | Accuracy | Balanced Accuracy |
| --- | --- | --- | --- | --- |
| Logit Model 1 | All variables | age groups and few race levels insignificant | 0.948 | 0.78008 |
| Logit Model 2 | All but age in 2 categories | Few insignificant race categories | 0.9469 | 0.7990 |
| **Step**** wise Logit **| Age 2, Race 2 rest same | All significant coefficients of predictors |** 0.947 **|** 0.82128** |

Figure 5: Summery Logit Model 1

![](RackMultipart20210828-4-ac3ndh_html_972f75b248d7b8ea.png)

Figure: 6; Confusion Matrix Logit Model 1

![](RackMultipart20210828-4-ac3ndh_html_6bf46b354136d9c9.png)

Figure:7 Summery Logit Model 2

![](RackMultipart20210828-4-ac3ndh_html_122524f6479b6314.png)

**Figure:8 ; Confusion Matrix Logit Model 2**

![](RackMultipart20210828-4-ac3ndh_html_79d7942ba0257940.png)

**Figure 9 – 12: Summary output, coefficients &amp;odds , cutoff accuracy and Confusion matrix of Logit Model (Selected Model)**

![](RackMultipart20210828-4-ac3ndh_html_77d79fb8bf2aa045.gif)

**Cutoff Accuracy-Logit model 3**

 ![](RackMultipart20210828-4-ac3ndh_html_79571415c53bd0d.png)

Coefficients and odds of Main Model

![](RackMultipart20210828-4-ac3ndh_html_aec5d450aef60693.png) ![](RackMultipart20210828-4-ac3ndh_html_b946b439d7e64897.png)

**Confusion Matrix Logit Model 3**

![](RackMultipart20210828-4-ac3ndh_html_c9c4758dfc377b75.png)

**Figure 13: Lift Chart Model**

![](RackMultipart20210828-4-ac3ndh_html_ca6ea93c1ea2d053.png)

**Figure 14: Decile Chart Logit Model 3**

![](RackMultipart20210828-4-ac3ndh_html_cc2fc7703e68a3f0.png)

Figure 15 &amp; 16 K-NN Model Output, k-accuracy &amp; sample Records

| K-NN Model |
| --- |
| k | Balance Accuracy | Sensitivity | Specificity |
| 1 | **0.911** | **0.831** | **0.991** |
| 2 | **0.900** | **0.812** | **0.989** |
| **3** | **0.911** | **0.833** | **0.989** |
| 4 | **0.892** | **0.796** | **0.989** |
| 5 | **0.896** | **0.802** | **0.989** |
| 6 | **0.891** | **0.794** | **0.987** |
| 7 | **0.897** | **0.807** | **0.988** |
| 8 | **0.891** | **0.795** | **0.987** |
| 9 | **0.890** | **0.793** | **0.986** |


![](RackMultipart20210828-4-ac3ndh_html_89d80835e5190b6d.png)

Sample records

![](RackMultipart20210828-4-ac3ndh_html_7dccce8e6a61c7f7.png)
