
Demand Forecasting: 

![DF](https://github.com/user-attachments/assets/8706bcab-edc0-4c95-aa70-70b21a5ccebe)


Business Requirement: 

Build, evaluate and deploy time-series based models (Autoregressive Integrated Moving Average 
(ARIMA), Seasonal ARIMA for seasonal products/services and Exponential Smoothing) for forecasting 
products / service demand and pricing with historical transactions data. 

Proposed solution: 

Business can leverage demand forecasting to enhance inventory management by anticipating future 
sales based on historical sales data and strategic planning. This approach aids in making informed 
decisions on inventory planning, storage needs, executing flash deals, and meeting consumer 
expectations. 
Forecasting demand for future timelines allows sellers to accumulate sufficient supplies in anticipation 
of demand surges, enabling them to participate and fulfill orders on time.

Solution Consumption: 

The Qlik dashboards are designed to display demand forecasting for L1, L2, L3, and L4 categories. Users 
can select specific categories to view historical quantity data up to the last month and forecasted values 
for the next 12 months.  
These dashboards are updated monthly to ensure they reflect the most current data. 

![demand forecasting ](https://github.com/user-attachments/assets/303de5b5-d24c-418e-9ac5-1ffa3501b11d)

Data: 

Historical purchase quantities for each category dating back to November 2018. 

Model Methodology:  

1. The module operates by aggregating the demand for a category over a specified time period 
(monthly), pre-processing the data, and then forecasting future demand. 
2. Time series forecasting is employed to make scientific predictions based on historical time-stamped 
data. This process involves building models through historical analysis and utilizing them to generate 
insights that inform future strategic decision-making

• Methodology1: (Shipment Date) 

Use the created_at column as the delivery date from the inb_prcs table. If created_at is 
missing in the inb_prcs, exclude those specific orders from consideration. 

• Methodology2: (Order Date) 

Utilize the confirmed_at column as the order date from the ffm_order table and the 
quantity column from the ffm_orderitem table. This approach will be applied for both 
monthly and quarterly predictions. 

Steps In Model:  

1. Only consider the categories having at least 40 months data points 
2. Not to consider the categories having continuous 4 months missing data 
3. Some contract numbers are excluded (which were shared by GeM)

![Steps In Model](https://github.com/user-attachments/assets/cef521e4-da1b-4c9f-bc78-1e125b630476)


The model performance is evaluated on these crucial metrics: 
• MAE (Mean Absolute Error) 
• RMSE (Root Mean Squared Error) 
• MAPE (Mean Absolute Percentage Error) 
• SMAPE (Symmetric Mean Absolute Percentage Error) 
• MSE (Mean Squared Error) 
• MAD (Mean Absolute Deviation) 
• R-squared (Coefficient of Determination) 
• EV (Explained Variance Score) 
• MDA (Mean Directional Accuracy) 
• WMAPE (Weighted Mean Absolute Percentage Error) 

Business Value:  

1. Qualitative – Sellers will get the tentative quantity required/demanded and can prepare for it in 
required time. This will enable more participation and generate a healthy competition in GEM. 
2. Buyers can also plan their procurement effectively by knowing in advance about seller’s availability.

   
The module works by accumulating the demand of a category for a time period (week/month), pre-processing 
the data and then forecasting the demand for the future. 

![DF12](https://github.com/user-attachments/assets/151b180e-8b9b-41fd-b8e5-e5194126729e)

Integration & API: Developed and integrated FlaskAPI. 

Input: Solution needs a category name or list of categories on which demand has forecast.

![df31](https://github.com/user-attachments/assets/1b3f8034-3635-479f-9b38-ec6c611f6290)


Output: It showcases graph of forecasted demand and report gets generated.

![df43](https://github.com/user-attachments/assets/1b406c56-43de-4123-8390-287a90b10546)


![df45](https://github.com/user-attachments/assets/751763ed-33bd-4f52-a87a-7009a7ca32e4)



