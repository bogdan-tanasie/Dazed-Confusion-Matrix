# FRAMEWORK EXPLANATIONS
---
Relevant hyperlinks point to further details, locations of notebooks, and other documents.

## 1. Framing the Problem
*Define the objective in business terms*

> - “You’ve got corruption, excessive force and domestic surveillance” - Jeffrey Ross, criminologist at University of Baltimore 
>- Baltimore officers used “overly aggressive tactics that unnecessarily escalate encounters, increase tensions and lead to unnecessary force” stated a report on the police department in 2015 
>- More than 300 people have been killed every year since 2015 
>- There is a clear issue with crime and policing in Baltimore. Corruption and inefficiencies within the police department have caused an unsafe city and cost the city millions of dollars that could be used towards more crime preventative initiatives.  
>- This has caused calls for reform, the most extreme ones being defunding of the police department 
>- “The better answer is to give police departments the resources they need to implement meaningful reforms” - Joe Biden when talking about police reform 
>- The objective in this case is to better prepare officers for crime handling by predicting the nature of the crime before the officers arrive on the scene. >- We believe that officers that are more prepared for the type of incident that they will encounter, will be able to handle the incident more efficiently and without excessive use of force. 
>-_[With 58 murders per 100,000 residents in 2019, Baltimore is the deadliest U.S. city..."](https://www.wsj.com/articles/the-wire-is-finished-but-baltimore-still-bleeds-11581119104)_
>-_["The better answer is to give police departments the resources they need to implement meaningful reforms..."](https://www.usatoday.com/story/opinion/2020/06/10/biden-root-out-systemic-racism-not-just-divisive-trump-talk-column/5327631002/)_

*How will your solution be used?*

We propose that all officers in the Baltimore police department have access to our model through our dashboard. They can access it in their patrol cars, as well as at their desk. When the officer receives a call that they have to respond to, and it is vague as to what they are about to encounter, they can put the information they receive from the call (date, time, inside/outside, location, premise) and input it into the dashboard. Our model will show a prediction for which type of crime they are about to deal with (robbery, auto theft, shooting, etc). This will allow the officer to arrive on scene prepared (with correct equipment, mentally, etc), rather than being surprised by what they see upon arrival to the scene.  

*What are the current solutions/workarounds (if any)?*

Current predictive policing strategies focus on predicting when and where a crime will occur 
These tools include: 

1. Crime anticipation system (CAS) - Amsterdam   
2. PreCobs - Germany 
3. PredPol - Los Angeles 
4. Hunchlab - Philadelphia 

These tools also predict type of crime, but have very low accuracy (none above 33% accuracy) They are more so used for preventative measures, whereas our solution has the goal of increasing policing effectiveness.

*How should you frame this problem (supervised/unsupervised, online/offline, etc.)?*

This problem is supervised, we get the features and make a prediction for a target variable in real time.We have data, and want to train a model to make predictions on future data based on the patterns found in our data. 

*How should performance be measured?*

Since this is a multi-class classification problem, we will measure performance with the f1 score of our model. If this model were to be applied in the real world, and deployed by the Baltimore Police department, a good measure of success would be the rates of complaints against police in the city. If the police are better prepared because of our accurate model, the number of police related issues should decrease.
As we cannot explore the above point, we have gathered data for years following our training data, and will test the model’s performance on crime that if deployed, the model would have been responsible for predicting. 

*Is the performance measure aligned with the business objective?* 

The ideal performance metric of police complaint rates is aligned with the business objective because it captures the issue of ineffective policing. However, the pure accuracy performance of our model does not guarantee solving the business objective. This is due to the countless confounding variables that could result in the deployment of this model. These include misuse, rejection to change, an underestimation of preparedness’ effect on good policing practices.  

*What would be the minimum performance needed to reach the business objective?*

Other predictive policing methods have accuracies around 30%, showing that predictive policing has a low threshold for success.  We believe that if our model is able to accurately predict the type of crime an officer will encounter over 50% of the time, that we would be able to effectively prepare officers to act more efficiently. 

*What are comparable problems? Can you reuse experience or tools?*

- The comparable problems are the crime prevention strategies already used in predictive policing (CAS, PredPol, Hunchlab, PredCobs) 
- We can reuse the type of data that are used in these tools (time, date, location) 
- The main difference is that for crime prevention, these tools look for patterns in past data and predict when a crime occurs. Our solution, which deals with effective policing, makes predictions based on information from the notification of the police in real time 

*Is human expertise available?*

- There are crime experts that coupled with our predictions, can show police how to best prepare for different situations.
- This solution would not work in the real world if it is not coupled with emphasis on buy in and training  

## 2. Data Acquisition
*This project was developed with the purpose of beginning a research cycle into predictive policing for Baltimore. To do so, the team created an ideal situation under which data acquisition would be of a higher level so that future developments can build on our project towards this potential goal.*

###### __IDEAL SITUATION__
The ideal situation is based on the orginal design of the opportunity presented by our team, under the logical hypothesis. This is also the overseeing goal of this project, to provide a basis to work towards this [logical hypothesis](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Project_Framework/Hypotheses.md) long-term. 

###### __PRACTICAL SITUATION__
The practical situation is the situation under which this project was built, according to constraints such as time and resource availability. It follows the redesign of the hypothesis into an [empirical hypothesis](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Project_Framework/Hypotheses.md). 

##### _List the data you need and how much you need_ 
---
###### __IDEAL SITUATION__

> - Complete data data on crimes in Baltimore, inclduing information on arrests and calls that were made where no crime was committed.
>- Current and up to date dataset on local crime sprees by description (arsonry, sexual assault, robberies, homicide, etc.)
>- Criminal records data on known criminals and areas of their last crimes by type of crime. 
>- Would require at least complete datasets on the last three years for all three types of data described above. 

###### __PRACTICAL SITUATION__
>- Open source dataset from Kaggle containing limited varIables, and data, on crimes in Baltimore. 
>- Information on the two years worth of crime in Baltimore.

##### _Find and document where you can get that data_ 
---
###### __IDEAL SITUATION__
>- FBI dataset would contain the advanced type of data that would be required on crimes in Baltimore, current crime sprees, criminal records and even potentially expected movement of crime from other cities & states.
>- If a release of this FBI dataset would not be avaialble thne the local police force databases in Baltimore would be able to provide local information on crime in Baltimore, limited information on expected & known crime sprees in Baltimore and known re-offending criminals. 
>- The police force databases in Baltimore can be supplemented with prison (dependent on scope of the analysis) datasets to have complete access on criminal records and status. 
 
###### __PRACTICAL SITUATION__
>- Kaggle contained an open source limited dataset on crime in Baltimore. 
 
##### _Check how much space it will take_
---
###### __IDEAL SITUATION__
>- Expected that storage will require additional considerations due to privacy issues and how big the datasets are. Therefore, would expect potentially utilizing object storage in the form OF external hard drives. 

###### __PRACTICAL SITUATION__
>- Open source and small dataset, so easily downloadable, therefore requires limited storage. 

##### _Check legal obligations and get authorization if necessary_
---
###### __IDEAL SITUATION__
>- Requires heavy legal obligations and high clearance due to the fact that this data contains private information and information belonging to the government and government entities. 
>- Authorization to attain and use this dataset is necessary

###### __PRACTICAL SITUATION__
>- There are no legal obligations or authorization required since the information is open source and it contains no sensitive information. 

##### _Get access authorizations_
---
###### __IDEAL SITUATION__
>- Authorization to attain and use this dataset is necessary.
>- The authorization would be coming from the owners of the dataset (ie, FBI, Baltimore police force, prisons, etc.)

###### __PRACTICAL SITUATION__
>- No authorization is required, open source dataset from Kaggle.

##### _Create a workspace(with enough storage space)_
---
###### __IDEAL SITUATION__
>- Workspace created would have to meet the expectations of those providing datasets due to privacy concerns. 

###### __PRACTICAL SITUATION__
>- The use of laptops was appropriate for the work being conducted for the purpose of this proejct. 

##### _Get the data_
---
###### __IDEAL SITUATION__
>- *Would have to reach out to the required parties above*

###### __PRACTICAL SITUATION__
>- The data was downloaded from Kaggle. The link to it is included in the project description. 

##### _Convert the data to a format you can easily manipulate (without changing the data itself)_
---
###### __IDEAL SITUATION__
>- Would have to determine if the datasets should be compacted into cSV files or determine another means for analysis. 

###### __PRACTICAL SITUATION__
>- Data was already in a format that could be easily manipulated, csv. 


##### _Ensure sensitive information is deleted or protected (e.g. anonymized)_
---
###### __IDEAL SITUATION__
>- Would determine standards to do this according to the contraints presented by all active parties.

###### __PRACTICAL SITUATION__
>- There was no sensitive information included in the data. 

##### _Check the size and type of the data (time series, sample, geographical, etc.)_
---
###### __IDEAL SITUATION__
>- Determined once the data is retrieved. Should be somewhat similar to the *PRACTICAL SITUATION* data type below. 

###### __PRACTICAL SITUATION__
>- It is 39.27 MB in size and the data can be considered time series and geographical, as the crime is divided by area and is occurring with the passing of time.
>

### Data Augmentation - Demographic Data
In the second part of the project, we wanted to add to our dataset to make better predictions, and also understand the inherent bias of our model. Because our model is based on past data, and includes neighborhood as a predictor, it is very possible that the model would be biased towards neighborhoods with certain characteristics. Therefore, we decided to gather the following variables for each neighborhood in each year in our original dataset: 
- 	Median household income 
-	Median price of homes sold 
-	Percent of family households living below the poverty line 
-	Percent of population 18-24 
-	Percent of population 25-64 
-	Percent of population 65+ 
-	Percent of Asian residents 
-	Percent of African-American residents 
-	Percent of Hispanic residents 
-	Percent of White residents 
-	Racial diversity index 
-	Total number of households 

Baltimore collects this data by what they call a Community Statistical Area (CSA). Each CSA is composed of a few neighborhoods, and often times it is hard to determinne which CSA a neighborhood belongs to solely based off name. Therefore, we had to manually match each neighborhood to its corresponding CSA. The matching file can be found here: _[neighborhoods.csv](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/data/neighborhoods.csv)_

### Ethical AI - Demographic Data Inclusion
One of the main issues with the demographic data was that there was a ton of missing information. On one hand, there were some neighborhoods in our data that were not associated with a CSA. On the other hand, not all data was collected every year, so we had some years where we were missing all information. Imputing demographic data can come with its own ethical issues, because you don't want to improperly impute and thus mask or augment some of the bias in the model. Therefore, for the missing years, we imputed the data with the median value for the same CSA in the years we had the data for. The cleaning, matching, and merging of the demographic data for the training data can be found in this _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Cleaning/V2_Demographic_Data_Cleaning_Merging.ipynb)_. The same process was used for the test data and can be found in this _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Cleaning/Test_data_demo_merging.ipynb)_.

People inherently possess bias, and as analysts, data scientists and architects, we must recognize the bias that is being injected into our models. There is a fear with predictive policing that by including demographic data (socioeconomic, race, neighbourhood, etc.) that the use of police force on minorities will increase. While we are aware that there is some bias present in our model due to the nature of the demographic data itself, we also recognize that most of this information is relevant and has demonstrated statistically significant correlations. 

#### Poverty & Crime
> _[“… poverty is the dominant explanatory factor with regard to aggravated assault & burglary.”](https://mcgill.on.worldcat.org/oclc/5153758805)_
> _[“The findings imply that problems in neighborhoods begin to manifest themselves at much lower levels of poverty.”](https://mcgill.on.worldcat.org/oclc/5156616079)_

#### Urbanization & Crime
>_[“…urbanisation encourages crime as the rate of crime is higher in large cities and in urbanised areas.”](https://go.gale.com/ps/anonymous?id=GALE%7CA302769876&sid=googleScholar&v=2.1&it=r&linkaccess=abs&issn=00309729&p=AONE&sw=w#:~:text=From%20the%20economic%20point%20of,cities%20and%20in%20urbanised%20areas.)_


#### Baltimore Facts 
>_[Highest Youth Crime Rates](https://foxbaltimore.com/news/city-in-crisis/nearly-half-of-suspects-recently-arrested-by-bpd-for-violent-crimes-are-juveniles)_
>_[High Youth Homicide Rate](https://youthtoday.org/2018/10/baltimore-is-tackling-the-problem-of-youth-violence-with-its-ceasefire-movement/)_


### Data Augmentation - 911 Calls
After scanning through some studies on urban crime, we found 911 calls were often studied as a potential factor. So we downloaded 911 calls data from https://data.baltimorecity.gov/datasets/911-calls-for-service, and matched with our main crime datasets. The matching was performed based on two criteria:
- Exact match between the street address from the 911 call and the documented crime
- Assume 911 call was made within 24 hours of the documented crime time

Then we dropped all duplicated matches as we observed multiple calls were reporting for the same crime. This left us about 9000 unique matches, which is good enough to split a test and validation set.

## _[3. Data Exploration](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Cleaning)_

The majority of the data exploration was done in the first course. The data contains some 270,000 rows with features such as the date, time, location of crimes, as well as the type of weapons used. See this _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Cleaning/Cleaning_Part1.ipynb)_ for details. This _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Cleaning/Cleaning_Part2.ipynb)_ details some further data exploration and cleaning, researching what features could be dropped, and how the features were encoded for analysis. Further details are included in section 4 with subsequent analysis and new data sources, as these were the focus for the second half of the course.


## _[4. Data Preparation](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/Cleaning)_

### Data Re-cleaning

After attempting to train some new models with augmented demographic data, it was noticed that many categories in the "Premise" feature could be recategorized together, greatly reducing the number of categories, especially those with very few records. For example, "APT/CONDO" and "APT. LOCKE" were simplying merged into a single "APARTMENT" category. This _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Cleaning/Recleaning.ipynb)_ contains all of the changes, while this _[text file](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Cleaning/Data_transformations.txt)_ contains a record of all the modifications that were made for future iterations of this cleaning.

### Weekend and Holidays

Two features were added to the original data: binary variables denoting if a crime occurred on a weekend, and if it occurred on a holiday. The same _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Cleaning/Recleaning.ipynb)_ as above contains the modifications, beginning at cell 106, and this code was again stored in the _[text file](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Cleaning/Data_transformations.txt)_ for easier access, should this transformation need to be done on other data.

### Test Data Re-cleaning

One glaring issue was made apparent with the test data. Because we procured this data directly from the Baltimore PD website, it was in a slightly different format than the training data we had procured from kaggle. Apart from the transformations that we did already for the first part of the course, it was noticed that many of the fields in the test data were complete phrases/words, while our training data had many of them truncated. For example, the training data had a premise listed as "SINGLE HOU", while the test data listed it as "SINGLE HOUSE". This was the reason for the original mismatches in the label encoder that we faced in the first course, and these were all painfully changed manually one by one. To see the extent of what had to be done, please see this _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Cleaning/V2_test_data_cleaning.ipynb)_. 

### Missing Data

Unlike the original data where it was a bit questionable to impute features such as the premise of a crime, this was not the case with the demographic data. The demographic features are much more reliant on other features present in the original dataset such as the district, as well as longitude and latitude. The _[miceforest](https://github.com/AnotherSamWilson/miceforest)_ package was used to impute the missing demographic data after it was merged with the original dataset. Miceforest uses employs Multiple Imputation by Chained Equations, filling in missing data through an iterative series of models, in this case random forests. It uses something called predictive mean matching, where N original values closest to the predicted missing sample are chosen as candidates, from which a value is chosen at random. In this way the missing demographic data was filled in. The issue with imputing demographic data in this fashion is that it is measured by a constant by neighborhood, whereas the imputation is continuous. To account for this, the mean of the imputed values was calculated per neighborhood to mimic a neighborhood-level imputation. This imputation model was then saved to be used on the test data. Though this model is far too large to store on github, the imputation process can be seen in this _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Model_Development/Demographic_imputation_MICE.ipynb)_. 

The test data was imputed using the same miceforest model as for the train data. The neighborhood-level imputation was done similarly, taking the mean of the imputed values by neighborhood. See this _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Model_Development/Impute_test_data_demographics.ipynb)_ for details. 


## _[5. Modeling, Evaluation, Explainability](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/Model_Development)_

### Base Model With Newly-Cleaned Data

Once the original data had been re-cleaned with the premises grouped properly and variables for weekends and holidays introduced, we optimized a lightGBM model to see if these changes improved the predicitions. We now had the benefit of libraries such as hyperopt and mlflow, allowing for a more "intelligent" gridsearch, and a clear way to keep track of the hundreds of runs that we did for this and subsequent training tasks. To access these model logs, import mlflow in the python console, and then in the terminal type "mlflow ui". Be sure that the terminal is in the Model_Development folder directory as that is where the mlruns folder is located. This should prompt you to open the mlflow ui on a local address, most likely http://127.0.0.1:5000/#/. To our disappointment, the 5-fold CV F1 score did not improve. In fact, it was slightly worse: 0.39467. See this _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Model_Development/New_model_tuning_with_MLflow_and_Hyperopt.ipynb)_ for details of the process, along with pictures of the mlflow plots indicating optimal hyperparameter ranges for subsequent runs. 

This new model did perform better on the test data, however. The F1 score was 0.512, much better than our original 0.439. See this _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Model_Development/V2_Final_model_w_weekend_holidays.ipynb)_ for more detailed test scores and for a feature importance plot. The importance of the features did not change very much from our first model, but the weekend variable provided some benefit, while the holiday variable not so much. Removing any variables from this model significantly reduced training scores, so all of the features were kept.

### Demographic Augmentation Model

One of the main goals of continuing this project was to improve the original lightGBM model with the augmented data. The first completely new model that we trained was on the original data augmented only with the demographic data. This new model was ahain developed using hyperopt and mlflow, and the process is documented in this _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Model_Development/New_model_with_imputed_demo.ipynb)_. The optimal F1 5-fold CV score was worse, at 0.391, but we did notice that the "Premise" feature surged in importance. 

This _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Model_Development/Test_data_performance_demo_model.ipynb)_ details this model's performance on the test data, which is hilariously terrible, with very low accuracy and recall, but a precision score that is as high as it is silly. Looking at the confusion matrix, the horrible result is explained:

![image](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/images/Confusion_demo.png)

The model simply classifies everything as common assault and calls it a day. But come on, it can't be that common! So we went on to further augment the data with the 911 calls.

### 911 Calls Augmentation Model

Before doing any modeling with this data, it had to be very painfully cleaned. After applying all of the transformations from the previously-mentioned _[text file](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Cleaning/Data_transformations.txt)_, we noticed that the CallDescription variable was riddled with spelling mistakes. We were particularly astounded at the different ways of mispelling "CHECK WELL BEING". The entire cleaning, model tuning, and test set validation is located in this _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Model_Development/911_model_tuning_and_EVERYTHING.ipynb)_. 

The training 5-fold CV F1 score was 0.5731, achieved again using hyperopt and mlflow. The feature importance plot is rather telling as to why this score is so much better than before:

![image](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/images/feature_importance.png)

This makes a lot of sense. If a potential crime is matched to a 911 call, that call will contain very valuable information to infer its nature. The performance of this model on the test data is very good: an F1 score of 0.76795. Keep in mind that this test data is from a stratified split from the 2015 data we were able to match, which could be the cause of its spectacular performance. Nevertheless, the train score for this model is the best out of all the models we tested. 

### Explainability

The shap package was used to glean further insight from this 911-augmented model. The most easy-to-interpret output is the summary plot below:

<img src="https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/images/SHAP_values_911.png" width="640" height="760">

Even though the call description is the most important in the feature importance plot, it is actually dwarfed by the Weapon_NONE category, and this makes a lot of sense. If you look at the classes effected by it, those correspond to crimes like larceny and auto theft, which by nature don't use a weapon, and robbery and shooting, which by definition do. Another value of interest is common assault, the red category, and you'll notice that Weapon_HANDS is almost entirely red. For reference, the corresponding categories of crimes are listed below:

AGG. ASSAULT: 0  
ARSON: 1  
ASSAULT BY THREAT: 2  
AUTO THEFT: 3  
BURGLARY: 4  
COMMON ASSAULT: 5  
HOMICIDE: 6  
LARCENY: 7  
LARCENY FROM AUTO: 8  
ROBBERY - CARJACKING: 9  
ROBBERY - COMMERCIAL: 10  
ROBBERY - RESIDENCE: 11  
ROBBERY - STREET: 12  
SEXUAL ASSAULT: 13  
SHOOTING: 14  

Some other explainability details are included in this _[notebook](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Model_Development/SHAP_911_model.ipynb)_. An interactive force plot shows the model output across all records, while the dependence plots show how each pair of features interact.

### Additional Models

Following some literature review, our team also decided to test some neural networks, to determine their viability on our current dataset and creating predictions. There were 4 separate neural networks built, including a _[Bayesian Network](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Model_Development/Bayesian%20Network.ipynb)_. The other 3 networks, which also includes an AutoKeras neural network, can be found in this _[file](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Model_Development/Neural_Nets_Policing.ipynb)_. While we found that neural networks do have potential in predictive policing, as has been stated in the literature, in our work its accuracy is far below our lightGBM model. 


## _[6. Causal Inference](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/Causal)_
This section is related to the Ethical AI part explained above as we try to understand the effect of demographic data on our model.   
Our main code uses the Causal Lift package and can be found at _[CausalModel](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Causal/CausalModel.py)_  
The main notebook in this section is _[CausalResultsBinary.ipynb](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Causal/CausalResultsBinary.ipynb)_  
- It also has an associated HTML file with the same name
- All the results are detailed in the notebook and HTML files
- The other files are more for experimentation



## _[7. Solution Presentation](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/ppt/Dazed_Confusion_2_0_FINAL_PRESENTATION.pdf)_

Our powerpoint presentation can be accessed from the hyperlink above, and details the following:
- 	Document what you have done
-  Context
- Understanding of the business problem
- Framing of the problem
- Statistics about the current situation
- Objectives and benefits
- [Hypothesis](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Project_Framework/Hypotheses.md)
- Data
- Models	- Modeling Approach & Model Evaluation
- Results
- 	Explainability of Results
- 	[Threats to Validity](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Project_Framework/Threats_to_Validity.md)
- 	Conclusion
- 	[Lessons Learned and Next Steps](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Project_Framework/Future_Work.md)


## _[8. Dashboard](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/App)_
The main dashboard file is _[app.py](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/App/app.py)_. We use Streamlit for the front-end and you can run it from that directory using *streamlit run app.py*  
The app uses _[SessionState.py](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/App/SessionState.py)_ to handle password authentication when first landing on the page  
The main section of the dashboard can be broken down into a few parts:
- load_data takes in different files paths and will get all the data necessary (it stores into cache for efficiency)
- predict uses the _[911MODEL.txt](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/911MODEL.txt)_ to run the predictions based on input data
- The sidebar section consists of information about the team and taking user input
- The model info displays some essential model metrics
- In get predictions, we encode user input and run the model to output the predicted class and associated probabilities
- The causal lift section displays demographic causal results
- Other info displays a 3D map of baltimore with our initial data  
In addition, the _[.streamlit](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/.streamlit)_ folder is used for all front-end configurations

## _[9. Launching, Monitoring and Maintenance](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/ppt)_

Our main areas of focus have been on project deployment and testing.

In terms of deployment we first focused on Docker.  
- We have our _[Dockerfile](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Dockerfile)_ that builds the project and also runs Pytest
- We have a _[dockerbuild.txt](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/dockerbuild.txt)_ with steps to get requirements and pushing to Azure registry
- We have _[requirements.txt](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/dockerbuild.txt)_ for all the libraries used

Our second deployment step focuses on Continuous Integration (CI) with Jenkins:
- We have a server running on a Linux computer for Jenkins
- We configured the _[Jenkinsfile](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Jenkinsfile)_ using the Jenkins Blue Ocean plugin
- The Jenkins pipeline builds, tests, and then runs the Docker image  

We also have a _[testing](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/App/Testing)_ folder.
- Tests are run with Pytest which is lightweight and easy to use
- We have some basic tests as proof of concept for the dashboard inputs and model quality
- Future users can build on these by adding more coverage or extend it to the entire code
- These tests are automatically run in the Dockerfile

