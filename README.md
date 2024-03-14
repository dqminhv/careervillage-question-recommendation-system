# CareerVillage Questions Matching Recommendation System
## Problem Statement
CareerVillage.org, a non-profit dedicated to career guidance, seeks to elevate its platform by implementing a data-driven recommendation system. This system will match student queries with the most appropriate volunteers, fostering connections between aspiring minds and experienced professionals. The project uses powerful data science techniques to optimize engagement and ensure students receive relevant, valuable advice from motivated mentors. This initiative holds the potential to significantly enhance CareerVillage's impact, empowering underserved youth with essential career role models.

The CareerVillage Question Recommendation Model is designed to efficiently connect students with professionals by assigning a career-related question to a set of professionals most likely to answer. 

## Methodology
When it comes to recommending new content, there are three main types of systems at play: Content-based Filtering, Collaborative Filtering, and Hybrid Approach. 
For privacy concerns, users’ information, such as personal and usage information, is neither stored nor utilized for training purposes. Consequently, a content-based approach will be employed for this project.

## Data
This project utilizes data provided by CareerVillage, retrieved from Kaggle. The full dataset can be found at: https://www.kaggle.com/competitions/data-science-for-good-careervillage/data

### Data Description
A brief description of the dataset
![dataset description](https://github.com/dqminhv/careervillage-question-recommendation-system/blob/main/document/careervillage.org_database.png?raw=true)
### Data Cleaning & Preprocessing
### EDA
Some interesting findings in the EDA step that provide great business insights for CareerVillage
* The number of daily questions peaked in May, which was reasonable since May was the graduation month. January and August also had a higher number of daily questions asked compared to the other months.
  ![] ()
* There was a significant increase in the number of questions asked daily since the first half of 2016, which was due to the increase in the number of new users in 2016.
  ![] ()
* On average, a question is first answered within 65 days. About 25% of questions are answered within 24 hours after posting. Half of the questions are answered within 2 days.
* The mean response time for a question changed over time, and there was a big drop in the mean response time from 2018 to 2019.
  ![] ()
* Most responses garnered a score of 1, primarily due to the answer rating system prompting users to either upvote or downvote. This rating approach complicated the evaluation of answer quality, as lower scores could be attributed to fewer people reading a specific response. On the other hand, higher scores might be the result of answers being present on the platform for an extended duration. Adopting a more effective answer rating scheme is highly recommended.
  ![] ()
## Modeling
## Model Evaluation
## Future Steps
