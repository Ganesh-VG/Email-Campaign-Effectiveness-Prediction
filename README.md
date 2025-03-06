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
