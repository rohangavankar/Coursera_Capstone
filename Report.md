# Coursera_Capstone
Project for IBM coursera capstone. Will build and test models for Seattle Car Accident Data. IBM certification in data science.

# Report

# Introduction/Business Problem
The data that is provided represents a series of accidents in the Seattle area, including many specific features and details of these accidents and a severity code, measuring the extremity of the accident. There are many problems that arise from an accident, especially a severe one, including traffic, use of emergency vehicles, congestion in the area, delays, and more. The data is provided by the Seattle Police Department. We can use this data to learn how to limit accidents and prevent especially severe ones. The data would most benefit a group like the Seattle Department of Transportation in managing a huge city and trying to prevent severe collisions. It could also warn passengers about the likelihood of an accident based on some of the features in the dataset including weather and road conditions. A group like the Seattle Dept of Transportation would be able to learn from these models and help prevent accidents that are severe.

# Data Understanding and Prep
There were 37 attributes in the dataset provided in this course. However many of these attributes were insignificant to the severity score which is the label in the dataset. At first I used all of the data and replaced NaN values with zeroes for some binary columns like speeding and right of way granted to the pedestrian. For the columns that I felt were insignificant and included many NaN's I dropped them. After encoding the data into numbers and getting rid of NaN values I was able to test the correlation of each of the features with the label severitycode. I found that many features, especially ones that I felt would not work, did not have high correlation scores. I went back into the code and selected features that I felt would impact the severeity of an accident. Repeating the process again, I came across low correlations all throughout, but the P-values were low and thus good for some attributes. These included road condition, weather, light condition, speeding, under the influence, and the code of the type of accident. Even though they all had really good P-values, I felt that speeding and dui's were unrecognizable and that obviously had good P-values with severity. Because these are unavoidable from the passengers viewpoint, I felt that I should remove the instances of speeding and driving under the influence from the dataset, and then drop those columns. If the model was to include these atrrbiutes then essentially one is saying that you can predict when a person speeds or is drunk, which is not possible. At the end I was left with four attributes, mostly predictable and natural. This would help the DOT of Seattle to warn drivers and are good attributes to build a model off of. Weather without a doubt can impact driving, along with road conditions and light conditions, which are my attributes.

Attributes Used in Feature Selection:
Weather
Roadcond
Lightcond

Label:
Severitycode

# Methodology
I created a dataframe with columns that only included weather conditions, road conditions, light conditions, and, of course, the severity code. After this I used Pearson Coefficient and Correlation to determine the strength of the relationship of each feature and the label. Then I was confident that these features would make a good model. I decided to use Logistic Regression, because the label only had 2 outcomes, a severity code of 1 or 2. 

# Results
Using Logistics Regression I got an accuracy or Jaccard Similarity score of 71% and an F1score of 0.41. 

# Discussion
We are able to see many accidents on clear days due to the large amount of clear days in the dataset. The most important thing in this was feature selection. Realizing that although speeding and driving had a nice correlation, those are uncontrollable features and would not help the Department of Transportation. However analyzing that light, road, and weather conditions played a role and proving that shows that these are features that passengers could take into account when driving. The model was a good model, with an accuracy of 70% but the biggest factor of this analysis was seeing the correlation between natural conditions and accidents. We can conclude that the way to make passengers get into less accidents is by making them aware of light road and weather conditions.

# Discussion
We are able to see that weather, road, and light conditions most impact accident severity, thus we should report to the Seattle Dept of Transportation that the way to prevent severe accidents is by letting drivers know the road, weather, and light conditions.
