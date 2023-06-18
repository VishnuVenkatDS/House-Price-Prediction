# House-Price-Prediction


e in machine learning at the same time.

Objective & Data
The competition goal is to predict sale prices for homes in Ames, Iowa. You’re given a training and testing data set in csv format as well as a data dictionary.

Training: Our training data consists of 1,460 examples of houses with 79 features describing every aspect of the house. We are given sale prices (labels) for each house. The training data is what we will use to “teach” our models.

Testing: The test data set consists of 1,459 examples with the same number of features as the training data. Our test data set excludes the sale price because this is what we are trying to predict. Once our models have been built we will run the best one the test data and submit .

You can familiarize yourself with the data on the competition page.

Task: Machine learning tasks are usually split into three categories; supervised, unsupervised and reinforcement. For this competition, our task is supervised learning.

Supervised learning uses examples and labels to find patterns in data

It’s easy to recognise the type of machine learning task in front of you from the data you have and your objective. We’ve been given housing data consisting of features and labels, and we’re tasked with predicting the labels for houses outside of our training data.

Tools
I used Python and Jupyter notebooks for the competition. Jupyter notebooks are popular among data scientist because they are easy to follow and show your working steps.

Please be aware this code is not for production purposes, it doesn’t follow software engineering best practices. I’ve sacrificed that somewhat for explainability.

Libraries: These are frameworks in python to handle commonly required tasks. I Implore any budding data scientists to familiarise themselves with these libraries:

Pandas — For handling structured data

Scikit Learn — For 




Libraries: These are frameworks in python to handle commonly required tasks. I Implore any budding data scientists to familiarise themselves with these libraries:

Pandas — For handling structured data

Scikit Learn — For machine learning

NumPy — For linear algebra and mathematics

Seaborn — For data visualization



Data Cleaning
To provide users with clean data. However, we mustn’t become lazy, there are always surprises in the data.

Warning! Don’t skip the data cleaning phase, it’s boring but it will save you hours of headache later on.

Duplicates & NaNs: I started by removing duplicates from the data, checked for missing or NaN (not a number) values. It’s important to check for NaNs (and not just because it’s socially moral) because these cause errors in the machine learning models.

Categorical Features: There are a lot of categorical variables that are marked as N/A when a feature of the house is nonexistent. For example, when no alley is present. I identified all the cases where this was happening across the training and test data and replaced the N/As with something more descriptive. N/As can cause errors with machine learning later down the line so get rid of them.

Date Features: For this exercise dates would be better used as categories and not integers. After all, it’s not so much the magnitude that we care about but rather that the dates represent different years. Solving this problem is simple, just convert the numeric dates to strings.

Decoded Variables: Some categorical variables had been number encoded. See the example below.




















Exploratory Data Analysis (EDA)
This is where our data visualisation journey often begins. The purpose of EDA in machine learning is to explore the quality of our data. A question to keep in mind is; are there any strange patterns that leave us scratching our heads?

Labels: I plotted sales price on a histogram. The distribution of sale prices is right skewed, something that is expected. In your neighborhood it might not be unusual to see a few houses that are relatively expensive.

Here I perform my first bit of feature engineering (told you the process was messy). I’ll apply a log transform to sales price to compress outliers making the distribution normal.

Outliers can have devastating effects on models that use loss functions minimising squared error. Instead of removing outliers try applying a transformation.
