# CareerVillage Questions Matching Recommendation System
## I. Problem Statement
CareerVillage.org, a non-profit dedicated to career guidance, seeks to elevate its platform by implementing a data-driven recommendation system. This system will match student queries with the most appropriate volunteers, fostering connections between aspiring minds and experienced professionals. The project uses powerful data science techniques to optimize engagement and ensure students receive relevant, valuable advice from motivated mentors. This initiative holds the potential to significantly enhance CareerVillage's impact, empowering underserved youth with essential career role models.

The CareerVillage Question Recommendation Model is designed to efficiently connect students with professionals by assigning a career-related question to a set of professionals most likely to answer. 

## II. Methodology
When it comes to recommending new content, there are three main types of systems at play: **Content-based Filtering**, **Collaborative Filtering**, and **Hybrid Approach**. 
For privacy concerns, users’ information, such as personal and usage information, is neither stored nor utilized for training purposes. Consequently, a **content-based** approach will be employed for this project.

## III. Data
This project utilizes data provided by CareerVillage, retrieved from Kaggle. The full dataset can be found at: https://www.kaggle.com/competitions/data-science-for-good-careervillage/data

### 1. Data Description
A brief description of the dataset
![dataset description](https://github.com/dqminhv/careervillage-question-recommendation-system/blob/47da7338f5311d52ab5701ca777ae00e75e6e336/document/images/careervillage.org_database.png)

Some key feature tables of the dataset
* **questions**: Capturing the concerns and inquiries posed by young individuals seeking career guidance, which has 23931 questions
* **professionals**: Delving into basic information of the volunteers, which includes 28152 professionals
* **answers**: Unveiling the insights and advice shared by professionals in response to student questions, which contains 23110 records
* **emails** and **matches**: The matches table reveals the assignment of questions to an email ID, while the emails table specifies which emails were dispatched to professionals. The amalgamation of data from these tables unveils details about the questions assigned to specific professionals. **matches** and **emails** are in long data format
* **tags**, **tag_questions**, and **tag_users**: Categorizing individuals and inquiries based on relevant keywords and topics. Those tables are in long data format.

### 2. Data Cleaning & Preprocessing

### 3. EDA
**Some interesting findings in the EDA step that provide great business insights for CareerVillage.**
* The number of daily questions peaked in May, which was reasonable since May was the graduation month. January and August also had a higher number of daily questions asked compared to the other months.
  ![](https://github.com/dqminhv/careervillage-question-recommendation-system/blob/47da7338f5311d52ab5701ca777ae00e75e6e336/document/images/No_daily_question_by_month.png)
* There was a significant increase in the number of questions asked daily since the first half of 2016, which was due to the increase in the number of new users in 2016.
  ![](https://github.com/dqminhv/careervillage-question-recommendation-system/blob/47da7338f5311d52ab5701ca777ae00e75e6e336/document/images/Cummulative_No_daily_question.png)
* On average, a question is first answered within 65 days. About 25% of questions are answered within 24 hours after posting. Half of the questions are answered within 2 days.
* The mean response time for a question changed over time, and there was a big drop in the mean response time from 2018 to 2019.
  ![](https://github.com/dqminhv/careervillage-question-recommendation-system/blob/47da7338f5311d52ab5701ca777ae00e75e6e336/document/images/mean_response_time.png)
* Most responses garnered a score of 1, primarily due to the answer rating system prompting users to either upvote or downvote. This rating approach complicated the evaluation of answer quality, as lower scores could be attributed to fewer people reading a specific response. On the other hand, higher scores might be the result of answers being present on the platform for an extended duration. Adopting a more effective answer rating scheme is highly recommended.
  ![](https://github.com/dqminhv/careervillage-question-recommendation-system/blob/8a75fc2983882f2b950a3611c2d18fadd9ec1858/document/images/answer_score.png)
* Common question topics: I create a word cloud for most-frequent-words in questions
  ![](https://github.com/dqminhv/careervillage-question-recommendation-system/blob/98d2bee8be0add70bd3d61d6012c6bc958eb0db9/document/images/question_wordcloud.png) 
## IV. Modeling
Two content-based filtering models were built. One used the **content** of the questions, and the other used the **tag names** associated with the questions.

Steps involved:
* TF-IDF Vectorization: The textual content of questions in the train set was transformed into numerical vectors using TF-IDF (Term Frequency-Inverse Document Frequency) vectorization.
* Model Training: The model was trained using the TF-IDF vectors and professional response data. During training, the system learned the relationships between the questions' content features and the professionals' preferences. This training phase aimed to establish a model capable of making accurate and personalized question recommendations.
* Recommendation Generation: The recommendation generation process involves assessing the content similarity between questions the professional has answered and those in the question pool using cosine similarity. The system identifies questions with similar content attributes and recommends them to the professional based on their historical preferences. The model generated a recommendation of 10 professionals for each question.

## V. Model Evaluation
Models were compared based on the mean response rate of the questions in the test set.

![](https://github.com/dqminhv/careervillage-question-recommendation-system/blob/98d2bee8be0add70bd3d61d6012c6bc958eb0db9/document/images/model_comparison.png)
## VI. Future Steps
* Integrate the response time into the successful metric.
* Consider professional activeness (the amount of time between each activity of a user) as a feature for the model.
* Comprise professionals' previous responses into the training phase.
* Dynamic tagging: Implement a dynamic automatic tagging system to adapt to evolving professional expertise.
* User feedback loop: Develop a mechanism to collect and incorporate user feedback for continuous improvement.
* Improve user rating mechanism.
* Enhanced collaborative filtering: Explore advanced collaborative filtering techniques to improve personalized recommendations.

