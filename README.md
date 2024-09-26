# TikTok-Claims-Project

## Project Title
Classifying TikTok Videos' Claim Status Using Machine Learning Models

## Project Overview
This project aims to develop a predictive model capable of classifying whether a TikTok video contains a claim or an opinion. The machine learning models evaluated were XGBoost and random forest, with the final random forest model demonstrating consistently high precision, recall, and F1 scores. This enabled the identification of key features that distinguish claim-based videos from opinion-based ones. User engagement metrics such as views, likes, shares, and downloads emerged as the most significant predictors for determining the claim status of TikTok videos.

## Business Understanding
TikTok users can submit reports flagging videos and comments that contain claims, which moderators must review. The volume of reports is often too high to process quickly. A high-performing classification model can help prioritize these reports by determining whether a video likely contains a claim or an opinion. This would streamline the moderation process, enabling a faster review of content flagged as potential claims and reducing the backlog of user reports.

## Data Understanding
The data used for this project is a synthetic dataset created by TikTok for the Google Advanced Data Analytics Professional Certificate Course. It consists of 19,382 rows and 12 columns, where each row represents a video, and the columns capture various features like user engagement data and transcriptions. There were 298 rows with missing values, which were removed since they accounted for a small portion of the data. No duplicate rows were found, and the dataset's class balance for claims and opinions was approximately equal, so neither upsampling nor downsampling was necessary. Unnecessary columns such as video ID were dropped, and categorical variables (e.g., claim_status, author_ban_status, and verified_status) were encoded as numerical values. Feature engineering included the creation of a 'text_length' feature based on the 'video_transcripted_text' column to quantify the length of each video transcript.

## [Python Workbook](https://github.com/roenseed/TikTok-Project/blob/main/TikTok%20project5_Machine%20Learning.ipynb)

## Modeling and Evaluation
A random forest model with 75 trees was selected as the best-performing model to classify whether a video contains a claim or an opinion. The bar plot below highlights that user engagement metrics—views, likes, shares, downloads, and comments—were among the most important features for predicting claim status, in line with the earlier exploratory data analysis (EDA) findings.

<img width="629" alt="Screenshot 2023-11-13 at 9 20 08 PM" src="https://github.com/kayneong/TikTok-Claims-Project/assets/150570357/39e847af-bf27-4566-954c-a174fb594c2b">

The confusion matrix below shows that, from the 3,817 rows of test data, the model generated only 3 false positives and 16 false negatives.

<img width="511" alt="Screenshot 2023-11-13 at 9 25 20 PM" src="https://github.com/kayneong/TikTok-Claims-Project/assets/150570357/3600afe5-31e8-44da-9037-782e2e17a8a8">

## Conclusion
The model successfully classified videos by claim status, with user engagement features being the most predictive. Initial data inspection and EDA revealed strong correlations between these engagement metrics and claim status. Statistical testing and regression analysis, detailed in the repository's notebooks, provided additional insights. While the 'video_transcription_text' feature was excluded from the final model due to challenges in encoding it, future iterations could explore using natural language processing techniques, such as CountVectorizer, to transform this feature into a format that could enhance the model's performance.
