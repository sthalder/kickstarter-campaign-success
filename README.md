# Kickstarter campaign success analysis

## About Kickstarter
Kickstarter, launched in April 2009, is an online crowd-funding platform for entrepreneurs to raise funds from the online community. Campaigns are intended to turn ideas into reality. It’s where creators share new visions for creative work with the communities that will come together to fund them. Project creators from across 22 countries can launch campaigns that are open to backers all over the world for funding. So far, Kickstarter has launched over 480,000 projects across 15 categories, collecting over USD 4.8 billion. The platform charges a 5% commission on successfully funded projects. Project backers receive rewards in the form of limited-edition product copies, exclusive user experiences etc. in return (It is not an equity-sharing model)


## Kickstarter Campaign Overview 
Any person or team of people launching their kickstarter campaign or project have to go through the following five step process: 

1.	Conceptualise
Pick a sub-category/theme that increases the chance of successful funding

2.	Curate content
Decide the project name, create description(“blurb”) and upload videos, photos, demo tools

3.	Set targets 
Decide campaign duration, set optimum goals and create reward packages

4.	Initiate follower links 
Build and grow online/offline networks and link social media channels and blog pages 

5.	Plan launch 
Plan week, day and time of launch to maximise initial views and notify followers 

## Project Scope 
Identify factors that contribute to campaign success and predict success probability pre-launch and post-launch

## Objective 
•	Recommend creators on planning campaign content and launch to maximize the probability of success

•	Identify projects that are below the threshold score for “success”, notify them about possible improvements

## Data Overview
Our dataset has information on 211271 kickstarter campaigns (rows) and 38 columns. Of which, we have sub-categorized relevant columns as columns having data for dimension and columns not having data for dimension:

•	Project Creation
Creator ID, Location, Creation date, Project ID, Category/Sub-category. All columns have data for dimension

•	Content 
Description, Multimedia, Network, Ad/Social media pages, Reward. Only the column on description has data for dimension

•	Launch Plan
Launch date and launch time are the columns having data for dimension whereas the column ‘notification list’ does not have data for dimension

•	Leading indicators 
Number of backers, Amount pledged and staff pick. All these columns have data for dimension

## Overall Framework
Create a recommendation framework based on the success propensity:
•	Estimate the probability of success before launch based on content uploaded

•	Suggest improvement tips for a good launch

•	Monitor response and refresh probabilities using a post-launch model with new predictors


## Detailed Approach:
•	Text Mining: 
Basically, we intend to use NLP algorithms for converting text fields viz. project name, blurb et al to have an output in the form of flesch readability score or keyword search/tokenization which then can be used as predictors for our models

•	Model building: 
Building two models, firstly a pre-launch success prediction model by using pre-launch campaign attributes like Project theme, content quality, campaign creation time, planned duration and goal amount to predict probability of success. Secondly, a post-launch success prediction model for tracking leading indicators such as number of backers, amount pledged, staff pick and additional predictors to refresh probabilities and revise recommendations

•	Model Training: 
Training ensemble tree-based models to obtain variable importance: by way of firstly creating feature set from all the text, numeric and categorical fields available. We’ll split the data into training and testing samples in the ratio 80:20. Post which, pass the feature matrix and response vector(train) into candidate models viz. Random Forest, AdaBoost and XGBoost for analysing variable importance results. 

•	Model Validation & Testing: 
Using the identified important variables as the final set of predictors for predicting the probability of success before and after the launch of the campaign. Also, cross-validation on the training sample will be used for model selection. And, model performance will be tested on an out-of-sample test data. 

•	Performance Metrics
Since no real investment is made until the project succeeds, a symmetric misclassification rate will be primary metric to measure performance along with AUC, model lift percentage and K-statistic

## Recommendation Framework 
•	Develop a rule-based rubric on the basis of variable importance results

•	Categorize campaigns under “High”, “Medium” and “Low” risk of failure

•	Select “Medium” and “Low” risk campaigns and evaluate campaign attributes as per the rubric

•	Reach out to creators with targeted suggestions

•	Monitor early indicators: Number of backers, Staff pick flag, Percentage of goal pledged