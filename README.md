# Lagos-Flood-Prediction
This project aims to develop a model for predicting flood events in Lagos, Nigeria. By analyzing historical data on rainfall, water levels, and other relevant factors, the model will attempt to identify patterns and trends that can forecast future flood risks.

## Lagos Flood Prediction- (HNG Task 2)
---

### Introduction
Flooding is a significant issue in Lagos, Nigeria, causing damage to infrastructure, displacement of residents, and economic losses. Predicting floods accurately can help in preparing and mitigating these adverse effects. This project aims to predict flood occurrences in Lagos using historical weather data and machine learning techniques.

![image](https://github.com/kingsleyosunkwo/Lagos-Flood-Prediction--HNG-Task-2-/assets/171164581/cdc0d0b6-5a59-4b12-ba24-05ae755239a6)

### Tools Used
The following tools were employed for this analysis:
1.	Spreadsheet: For data gathering, cleaning, and Labelling.
2.	Python: The primary programming language used for data analysis and model building.
3.	Pandas: For data manipulation and cleaning within the python environment.
4.	NumPy: For numerical operations.
5.	Matplotlib and Seaborn: For data visualisation.
6.	Scikit-learn: For machine learning model implementation.
7.	Joblib: For saving and loading the machine learning model.
8.	Jupyter Notebook: The environment for interactive data analysis and model building.


### Methodology
1.	Data Collection: Historical weather data for Lagos was collected, including features such as temperature, humidity, precipitation, wind speed, and solar radiation. This was obtained from a dataset from Kaggle.
The dataset has the following columns:
1.	datetime: The date of the record. 
2.	tempmax: Maximum temperature recorded on that day (°C). 
3.	tempmin: Minimum temperature recorded on that day (°C). 
4.	temp: Average temperature of the day (°C).
5.	 feelslikemax: Maximum 'feels like' temperature recorded on that day (°C). 
6.	feelslikemin: Minimum 'feels like' temperature recorded on that day (°C). 
7.	feelslike: Average 'feels like' temperature of the day (°C). 
8.	dew: Dew point (°C), the temperature at which air becomes saturated with moisture.
9.	 humidity: Humidity percentage.
10.	 precip: Amount of precipitation (mm). 
11.	precipprob: Probability of precipitation (%). 
12.	precipcover: Percentage of the day that had precipitation (%). 
13.	preciptype: Type of precipitation (e.g., rain, snow).
14.	 snow: Amount of snowfall (mm). snowdepth: 
15.	Snow depth (mm).
16.	 windgust: Maximum wind gust speed (km/h). 
17.	windspeed: Average wind speed (km/h).
18.	 winddir: Wind direction (degrees). 
19.	sealevelpressure: Sea-level atmospheric pressure (hPa). 
20.	cloudcover: Average cloud cover (%). 
21.	visibility: Average visibility (km). 
22.	solarradiation: Average solar radiation (W/m²). 
23.	solarenergy: Solar energy received (MJ/m²).
24.	 uvindex: UV index.
25.	 severerisk: Risk of severe weather events (may be empty or null).
26.	 sunrise: Sunrise time. sunset: Sunset time. 
27.	moonphase: Moon phase (0 = new moon, 1 = full moon). 
28.	conditions: General weather conditions (e.g., Partially cloudy, Rain).
29.	 description: Detailed weather description.
30.	 icon: Weather icon identifier. stations: 
31.	Weather stations that provided data.

### Process

1.	Data Preprocessing: The following data processing processes were followed:
o	Dropped some columns that might not be useful for the Prediction.
o	Handled missing values by creating a lag feature for precipitation (precip_lag1), which represents the precipitation value from the previous day.
o	Dropped rows with missing values resulting from the lagging operation.

2.	Feature Selection: The following features were selected for training the model:
o	datetime
o	tempmax, tempmin, temp
o	feelslikemax, feelslikemin, feelslike
o	dew, humidity
o	precip, precipprob, precipcover, preciptype
o	windgust, windspeed, winddir
o	sealevelpressure, cloudcover
o	visibility, solarradiation, solarenergy
o	uvindex, sunrise, sunset, moonphase

3.	Model Training:
o	A Random Forest Regressor was used to predict the flood levels.The model was trained using the selected features and target variable (flood levels which were determined from the precip values) and a threshold value of 50 was set. 
o	For any value greater than 50, it indicates possibility of flood, this possibility increases with an increase in the precip value.


4.	Model Evaluation: The model's performance was evaluated using appropriate metrics:
o	Root Mean Square Error
o	R Squared)  
The model was saved for future predictions.
5.	Prediction: The saved model was loaded, and new predictions were made using a forecast dataset. The forecast dataset was preprocessed in the same manner as the historical data so as to make correct predictions.

### Visualizations

![image](https://github.com/kingsleyosunkwo/Lagos-Flood-Prediction--HNG-Task-2-/assets/171164581/d224b071-1ef6-4209-888f-b2a03f00da57)


![image](https://github.com/kingsleyosunkwo/Lagos-Flood-Prediction--HNG-Task-2-/assets/171164581/a966a864-9e38-40fc-8782-c28dfce0d6cf)


![image](https://github.com/kingsleyosunkwo/Lagos-Flood-Prediction--HNG-Task-2-/assets/171164581/f8d576ff-e6ef-4841-8603-a1283e1ec9aa)


![image](https://github.com/kingsleyosunkwo/Lagos-Flood-Prediction--HNG-Task-2-/assets/171164581/44a7e965-7298-4f00-a1d5-a3a63fea46de)


![image](https://github.com/kingsleyosunkwo/Lagos-Flood-Prediction--HNG-Task-2-/assets/171164581/8c8fb143-950c-4fc6-b52e-f30e9a72f48e)



### Prediction Result
The model was used to predict flood levels based on new weather data. The predictions are as follows:
[174.74, 125.54, 174.74, 174.74, 174.74, 174.74, 62.77, 64.233, 20.957, 7.909, 15.066, 57.11, 10.784]

### Interpretation of Result
The values in the prediction result is an array whose elements correspond to each row of our forecast dataset. Mapping out these values we have:

![image](https://github.com/kingsleyosunkwo/Lagos-Flood-Prediction--HNG-Task-2-/assets/171164581/12a223f3-0e7f-479c-b7d6-a213043104d7)

From the table above we can see that the model predicted a high possibility of flood from 6 July to 11 July, while a lower possibility on 12 and 13 July. The model predicted ‘false’ from 14 to 18 July except for 17 July which had a Low possibility of flooding. 
Limitations
The following are reasons why the model might incorrectly predict results:
1.	Data Quality: The accuracy of predictions is heavily dependent on the quality and completeness of the input data. Missing values and inaccurate data can affect model performance.
2.	Model Generalisation: The model may not generalise well to unseen data, especially if the weather patterns change significantly over time.
3.	Feature Engineering: The project relies on basic feature engineering techniques. More advanced techniques could potentially improve the model's performance.
4.	Weather Variability: Weather conditions are inherently unpredictable, and sudden changes can lead to significant prediction errors.

### Conclusion
The project has successfully developed a predictive model for flood levels in Lagos, utilizing historical weather data. While the model currently offers valuable insights, there are several avenues for improvement. Enhancing data quality, integrating advanced feature engineering techniques, and continuously updating the model with new data will significantly boost its accuracy and reliability. Precise flood prediction is crucial for improving preparedness and mitigation strategies, ultimately minimizing the adverse effects of floods on the community. This ongoing effort will contribute to more resilient infrastructure and better protection for the residents of Lagos.







