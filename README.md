# Email-Campaign-Effectiveness-Prediction
This project leverages machine learning to optimize email marketing by analyzing recipient interactions and predicting engagement patterns. This enables smarter audience segmentation, ensuring tailored content delivery for improved engagement and conversions.


## Variable Description
1. **Email ID** – Unique identifier for each recipient.
2. **Email Type** – Categorizes emails as marketing (1) or important updates (2).
3. **Subject Hotness Score** – A score measuring the effectiveness of the email subject line.
4. **Email Source Type** – Indicates whether the email is from sales/marketing or admin updates.
5. **Email Campaign Type** – The type/category of the email campaign.
4. **Total Past Communications** – The total number of emails sent to the recipient in the past.
5. **Customer Location** – Demographic location of the recipient.
6. **Time Email Sent Category** – Time of day when the email was sent (morning, evening, or night).
7. **Word Count** – Number of words in the email body.
8. **Total Links** – Count of hyperlinks included in the email.
9. **Total Images** – Number of images present in the email.
10. **Email Status** – Target variable indicating whether the email was ignored, read, or acknowledged.


## Important Visualizations
1. Subject Hotness Score Analysis
   
   ![image](https://github.com/user-attachments/assets/e536a289-912a-442d-9781-96977c581257)

   From the above data it is clear that we are lagging far away in maintaining good subject hotness score for the email that we are sending. And the box plot which is pointing data towards the lower subject hotness score is because of most of the emails having lower subject hotness score.

2. Customer Location Analysis

   ![image](https://github.com/user-attachments/assets/c227f983-0bc6-405e-acc9-fda5f7b8f153)

   Further work need to be carried out in acquiring more customers in less explored regions. As we can see that more number of mails are leading to more number of conversions, its necessary to increse the quantity of emails sent. The important aspect is to strictly capture the customer location data in further sprints.

3. Customer Past Communication Analysis

   ![image](https://github.com/user-attachments/assets/2a49445e-0ea7-4adf-95a0-3e3ca9ed6c8d)

   In histogram there is a spike in total past communication at values 20, 30 and 40. From Box plot we can see that acceptance is higher for people with more past communications.The analysis helps in maintaining the total past communication at a moderate level so that the customer should not get overwehlmed and we should'nt have sent too less mails.

4. Word Count Analysis

   ![image](https://github.com/user-attachments/assets/a4f64fb6-81c5-4bc9-9ff3-e0824eab1c2e)

   Although emails sent is on higher side where word count is 700. The ignored emails also lie at word count of 700 and acceptance is higher when word count comes down to 500 to 600.


## Hypothesis Testing

1. Null Hypothesis (H₀): There is no significant difference in the Subject Hotness Score between emails that were "Read" and those that were "Ignored".
   Alternative Hypothesis (H₁): There is a significant difference in the Subject Hotness Score between emails that were "Read" and those that were "Ignored".

   Result:  T-statistic: -23.5589
            P-value: 0.0000
            The difference in Subject Hotness Score between Read and Ignored emails is statistically significant.

2. Null Hypothesis (H₀): There is no significant difference in the Total Past Communications between emails that were "Read" and those that were "Ignored."
   Alternative Hypothesis (H₁): There is a significant difference in the Total Past Communications between emails that were "Read" and those that were "Ignored".

   Result:  T-statistic: 51.4987
            P-value: 0.0000
            Reject the Null Hypothesis: Total Past Communications significantly affects whether an email is read or ignored.


## Feature Importance Diagram:

![image](https://github.com/user-attachments/assets/01d9ea62-ac6e-4c9f-b862-29c4a4757ed7)


## Model Building

### Random forest Classifier

Result: 
- Class 0 (Majority Class)

    Precision = 0.82, Recall = 0.97, F1 Score = 0.89 → The model is excellent at classifying this class.

- Class 1 (Minority Class)

    Precision = 0.41, Recall = 0.13, F1 Score = 0.19 → Poor recall means the model is missing many actual class 1 instances.

- Class 2 (Rare Class)

    Precision = 0.11, Recall = 0.02, F1 Score = 0.03 → Extremely poor performance, meaning the model almost ignores this class.

![image](https://github.com/user-attachments/assets/947296d8-b556-4e8d-827a-d81fd72a32cc)


### XGBoost Classifier

Result :
### **Class-wise Performance**
| **Class (Email Status)** | **Precision** | **Recall** | **F1 Score** | **Support (Samples)** |
|----------------|------------|--------|-----------|----------------|
| **Not Read (0)** | **83%**  | **98%**  | **90%**  | 10,988 |
| **Read (1)** | **48%**  | **14%**  | **22%**  | 2,208 |
| **Acknowledged (2)** | **22%**  | **1%**  | **2%**  | 475 |

![image](https://github.com/user-attachments/assets/7883b3d9-b772-406f-9af4-097eff916f9d)


### Clustering Model for Customer Segmentation

![image](https://github.com/user-attachments/assets/12eda18f-59b8-4a62-8eb1-cfe061ebabe2)


## Metrics for further use

| Feature                    | Importance Score | Best Range (Q1 - Q3)  |
|----------------------------|-----------------|----------------------|
| Total_Past_Communications  | 0.148944        | 20.00 - 38.00       |
| log_Total_Links            | 0.109470        | 1.95 - 2.71         |
| Subject_Hotness_Score      | 0.104532        | 0.20 - 1.80 (Biased)|
| Total_Links                | 0.101495        | 6.00 - 14.00        |
| Word_Count                 | 0.098067        | 521.00 - 880.00     |
| Word_Per_Link              | 0.097017        | 41.35 - 101.33      |
| Word_Per_Image             | 0.096630        | 101.33 - 704.00     |
| Total_Images               | 0.085549        | 0.00 - 5.00         |
| Time_Email_sent_Category   | 0.079400        | 1.00                |


## Experiment design for further data collection:
1. To analyze customer responses effectively, a separate dataset should be created exclusively from email responses, maintaining a distinct set of emails for this study.
2. The study dataset should ensure an equal distribution of emails across all categorical variables to eliminate bias.
3. Continuous variables should be binned, with the dataset maintaining an equal number of emails in each bin to ensure balanced representation.
4. Tests should be conducted separately for each customer location, considering behavioral differences across regions.
5. Additional marketing metrics, such as email content urgency score, positivity score, and sentiment analysis, should be incorporated to examine psychological factors influencing customer engagement.
