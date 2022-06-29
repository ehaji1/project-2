Key Files:  Project 2 DSE Presentation, 

What is the question?

Using the LSTM machine learning model, we will determine how closely the Consumer Price Index can be predicted during two of the most turbulent periods in recent history (2008-2010 and 2020-2022), and if we can predict individual CPI components (i.e. energy, food, shelter).   

We will also use sentiment analysis to validate/contradict our predictions.

How do we approach the question? 


	In order to answer the question, we would need to determine and access the data that is associated with CPI. In order to access the data, we went to the Bureau of Labor Statistics to extract various CPI data, which will be used to configure into a database. We used the data of beef, chicken, energy, utility and more to establish a consistent dataframe when running the code through various deep learning tools. Originally, we used an API that was supplied by the Bureau, but it was not sufficient in what we were trying to obtain. The data was pulled using excel for each data group from the time of when the government started to record the data all the way up to the current time of May 2022. In the code, we established a dataframe for all groups of data, which will be used for picking specific data for individual comparisons. We concat the data into one dataframe in which the index was based on the year. Once the data was contacted, we ran a def function that would fill all NaN data. The reason for the function is based on the difference of recording of each CPI, which would result in some CPI groups missing years of data since they were not being in the record at that current time. Once the data has been filled, we will begin to establish our X and y test samples, we used 16 since that would cover every CPI that is located in the dataframe. We used a window size of 30 to tell us the results for 30 days in the future. We split the X and y train and test for it function properly. In the modeling sequence of the program, i used a input unit of 800, which was determined to get the reduce the lose when running the model. We originally used three layers, but we decided that a fourth layer would be needed. The total parameter amount that was used in the code was 17,936,801. It seemed to be accessive, but based on the abundance of data from 40 years it became a necessity to achieve the most accurate results. We fit the model and ran with epochs of 800 with a batch size of 100. Depending on the computer specs, you would be ranging an estimated time of 30 mins to 2 hours of model fit. Once the model has been fit, we evaluated the results and ran an prediced and acutal varable that will be used to for graphing the actual data and the predicted data that was a result of the model. Once finished we graphed to display how close the deep learning had achieved in comparison to the acutal. At the sametime we ran the sentiment analysis of the current articles related to a few of the top CPI groups that had more value to the current time. The data was extracted using a news api and then...

What deep learning tools did we use?

  Long Short Term Memory is notable as a choice for time-series predictions, which could be implemented for CPI. The prediction model we used was based on the python programming languages and multiple libraries such as tensorflow, keras, scikit, pandas and numpy for deep learning algorithms. The LSTM model had a set up of multiple layers based on the different CPI that we pulled from the Bureau of Labor Statistics. The CPI datasets were used as the input variables, which then would be allocated to a hidden layer consisting of various neurons to be moved to the output dense layer, which will have 1 variable. In theory, we could just develop a basic Recurrent Neural Network(RNN), however the necessary input data and gate function that is associated with LSTM made it a better choice of practice for this particular calculation of CPI prediction. 

Any issues?
	Originally, we used an API that was associated with the Bureau of Labor Statistics. However, the extraction would only be a small portion since it would run only 20 years of data, which would require multiple pullings per CPI group. Also, the format of the extraction would not be supportive in developing, and some groups of data were unable to be pulled using the API. Knowing that we were unable to pull data on certain objects, we had to manually pull each dataset and manipulate the excel file to ensure that the data could be usable for any functions. Outside of the data extraction, we had issues with the development of the CPI prediction code, and the sentiment analysis of the CPI groups. The CPI prediction model had a reshape issue, but I was able to fix it by creating a def function to replace nan values that were empty with the previous value, which ensured that the code can now be reshaped and set up without missing data for particular dates. With the sentiment analysis, we were having issues with the news api where it wasn't able to run properly, so we had to recode the api to get it functional for extracting the CPI. The final issue was running the code, which had a waiting period of 66 mins, based on the four layers within the model. It was necessary to get the closest we could get with the predicted model. If not, then the predicted model would never have matched any of the data in the actual dataset. 

What were the results?


What did we learn?


How to improve if given more time? 

	In order to improve the overall format and results of the LSTM and sentiment analyssi of the data, we would need to have more CPI data extracted from the other CPI groups. Some of the more important CPI data that was left out our current data was coffee, which would have a huge impact on the predicted model. Also, it would been best to reformat the models based off of regions. In that version we would split the country into 5 regions and used the data from the Labor and Statistics to set up models for each individual area. The data for region based already exists in the goverment database, and could been used to get a better idea of how each area was impacted more compared to others. For example, In areas such as California Gas, Energy and more would have a higher inflation rate then states in other regions like Wyoming. The breakdown of regions would have been more accurate and narrowed the data for each predicted model, and would display more accurate results of each region in comparsion to the overall CPI. 
