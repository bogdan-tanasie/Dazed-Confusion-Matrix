# Project Framework

## _[5.1 Framing the Problem](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Project_Framework/Framing_the_Problem.md)_
- Define the objective in business terms
- How will your solution be used?
- What are the current solutions/workarounds (if any)?
- How should you frame this problem (supervised/unsupervised, online/offline, etc.)?
- How should performance be measured?
- 	Is the performance measure aligned with the business objective? 
- 	What would be the minimum performance needed to reach the business ob- jective?
- 	What are comparable problems? Can you reuse experience or tools?
- 	Is human expertise available?
## _[5.2 Data Acquisition](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Project_Framework/Data_Acquisition.md)_
- 	List the data you need and how much you need
- 	Find and document where you can get that data
- 	Check how much space it will take
- 	Check legal obligations, and get authorization if necessary
- 	Get access authorizations
- 	Create a workspace (with enough storage space)
- 	Get the data
- 	Convert the data to a format you can easily manipulate (without changing the data itself)
- 	Ensure sensitive information is deleted or protected (e.g. anonymized)
- 	Check the size and type of the data (time series, sample, geographical, etc.)
- 	Sample a test set, put it aside, and never look at it (no data snooping!)
## _[5.3 Data Exploration](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Model_Development/Visualization.ipynb)_
- 	Create a copy of the data for exploration (sampling it down to a manageable size if necessary)
- 	Create a Jupyter notebook to keep a record of your data exploration
- How do you profile your data?
- Download a dataset and provide: Missing Data (%), Quantile Statistics, Descriptive Statistics, Correlations
- Study each attribute and its characteristics
- Name Type (categorical, int/float, bounded/unbounded,text,structured, etc.)
- % of missing values
- Noisiness and type of noise (stochastic, outliers, rounding errors, etc.)
- Possibly useful for the task?
- Type of distribution (Gaussian, uniform, logarithmic, etc.)
- For supervised learning tasks, identify the target attributes
- 	Visualize the data
- 	Study the correlations between attributes
- 	Study how you would solve the problem manually
- 	Identify the promising transformations you may want to apply
- 	Identify extra data that would be useful (go back to ???Get the Data???)
- 	Document what you have learned
## _[5.4 Data Preparation](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/Cleaning)_
- 	Dealing with missing data
- 	Cleaning data
- 	Outlier detection
- 	Data preprocessing
- 	Feature selection
- 	Feature engineering
- 	Feature Scaling
- 	Clustering
- Can be utilized to group outliers against the main data points
- It can be leveraged to come up with most relevant instances to use for training, validation, and testing
- Obviously it can be used for unsupervised learning
- Dealing with imbalanced data
## _[5.5 Modeling](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/Model_Development)_
- 	Train many quick and dirty models from different categories (e.g.,linear, na??ve Bayes, SVM, Random Forests, neural net, etc.) using standard parameters
- 	Measure and compare performance:
- For each model, use N-fold cross-validation and compute the mean and standard deviation of the performance measure on the N folds.
- 	Analyze the most significant variables for each algorithm
- 	Analyse the types of errors the models make
-  What data would a human have used to avoid these errors?
- 	Have a quick round of feature selection and engineering
- 	Have one or two more quick iterations of the five previous steps.
- 	Short-list the top three to five most promising models, preferring models that make different types of errors.

## _[5.6 Model Evaluation](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/Model_Development)_
	SOTA Supervised Learning SECTION

## _[5.7 Model Selection](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/Model_Development)_
- 	Evaluation metrics
- 	Simplicity
- 	Explainability and interpretability
- 	Offline vs. online
- 	Batch vs. Real-time
## _[5.8 Model Fine-Tuning](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/Model_Development)_
- 	Fine-tune the hyperparameters using cross-validation
- Treat your data transformation choices as hyperparameters, especially when you are not sure about them (e.g., should I replace missing values with zero or with the median value? Or just drop the rows?)
- Unless there are very few hyperparameter values to explore, prefer random search over grid search. If training is very long, you may prefer a Bayesian optimization approach(e.g.,using Gaussian process priors, as described by Jasper Snoek, Hugo Larochelle, and Ryan Adams).
- 	Try Ensemble methods. Combining your best models will often perform better than running them individually
- 	Once you are confident about your final model, measure its performance on the test set to estimate the generalization error
## _[5.9 Solution Presentation](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/ppt)_
- 	Document what you have done
- Context
--   Context should present your understanding of the business problem
--  You should frame the problem such that is understandable for different stakeholders
-- It should cover a bried resume of 5.1.Framing the problem
-- It should give statistics about the current situation
-- It should present objectives and benefits
- [Hypothesis](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Project_Framework/Hypotheses.md)
- Document and communicate the hypotheses in terms of 
--What can be predicted/optimized
-- What are the actions can be taken
-- What are the possible outcomes
-- Communicate your hypothesis testing strategy to the right audience
--Null hypothesis
--Outcomes and types of errors
-- P-values and confidence intervals			
--Multiple testing and p-hacking
- Data
- Model	- Modeling Approach & Model Evaluation
- Results
-- 	Explainability of Results
- 	[Threats to Validity](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Project_Framework/Threats_to_Validity.md)
- 	Conclusion
- 	[Lessons Learned and Next Steps](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/blob/master/Project_Framework/Future_Work.md)
## _[5.10 Launching, Monitoring and Maintenance](https://github.com/McGill-MMA-EnterpriseAnalytics/Dazed-Confusion-Matrix/tree/master/ppt)_
- Get your solution ready for production (plug into production data inputs, write unit tests, etc.)
- W- te monitoring code to check your system???s live performance at regular intervals and trigger alerts when it drops.
- Beware of slow degradation too: models tend to ???rot??? as data evolves
- Measuring performance may require a human pipeline (e.g. via a crowdsourcing service)
- Also monitor your inputs??? quality (e.g., a malfunctioning sensor sending random values, or another team???s output becoming stale). This is particularly important for online learning systems
- Retrain your models on a regular basis on fresh data
