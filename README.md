## Car price analysis:

This project is a part of Module 11 - Practical Application 2. The goal of this project is to predict used car price using various regression techniques.

#### High level data tasks: <br>
&nbsp;&nbsp;&nbsp; 1) Pull the dataset into a dataframe for analysis. <br>
&nbsp;&nbsp;&nbsp; 2) Look at data description to understand missing values and basic statistics of each feature. <br>
&nbsp;&nbsp;&nbsp; 3) Transform numeric features by standardizing it as needed. <br>
&nbsp;&nbsp;&nbsp; 4) Transform numeric features to numeric data. <br>
&nbsp;&nbsp;&nbsp; 5) Encode categorical features. <br>
&nbsp;&nbsp;&nbsp; 6) Reduce cardinality of features having a large number of unique values. <br>
&nbsp;&nbsp;&nbsp; 7) Perform feature selection and regression analysis on transformed data with <b> price </b> as target variable.

#### Data Understanding:
&nbsp;&nbsp;&nbsp; 1) <b>Acquire data</b> - Data has been aquired from kaggle. The original dataset contained information on 3 million used cars out of which, </br> &nbsp;&nbsp;&nbsp;&nbsp; we have pulled only 426K records. <br>
&nbsp;&nbsp;&nbsp; 2)<b>Data description</b> - There are 426,880 rows and 18 columns in this dataset. The format of raw data is a .csv file. </br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The target variable of the dataset is the column <b>"price"</b>. </br>
&nbsp;&nbsp;&nbsp; 3) <b>Data quality</b> - There are several columns missing data as shown above. Drop column entirely if <b>more than 80 %</b> of values are missing. </br>

#### Data Preparation:
&nbsp;&nbsp;&nbsp; 1)<b>Data Cleanup</b> - Column <b>"size"</b> is missing a significant percentage of values. Since the value for this column can be inferred from column &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <b> "type" </b>, we can drop the column  <b>size</b>. </br> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Also, column <b>"VIN"</b>, <b>"Id" </b> and <b>region</b> (can we infer region from feature "state") doesn't provide much value for prediction. </br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Therefore these columns can be dropped as well. Finally, drop records where value of target feature <b>"price"</b> is <b>0</b> as it doesn't provide any <br> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;value for prediction.

#### Remove Outliers:
&nbsp;&nbsp;&nbsp; 1) Based on the analysis on column <b>"price"</b> for outliers by comparing the samples against google to understand the actual real car price, it will be more appropriate to take the percentile from 5 upto 99.7 to remove outliers and invalid car prices. </br>
&nbsp;&nbsp;&nbsp; 2) Considering any used car mileage above 10K miles as minimum and below 500 K as maximum, it will be more appropriate to take the percentile from 6.68 and 99.7.

#### Handline missing values:
&nbsp;&nbsp;&nbsp; 1) Features <b>fuel, transmission, title_status, paint_color and condition </b> - Replace the missing values with <b>mode</b>. </br>
&nbsp;&nbsp;&nbsp; 2) Features <b>year, manufacturer and model </b> - These features are missing only few values. Delete records having <b>"Null"</b> values for one or more of these features. </br>
&nbsp;&nbsp;&nbsp; 3) Features <b>cylinders</b> and <b>type</b> has a value called <b>"other"</b>. We can use this value to replace the missing values for these features. </br>
&nbsp;&nbsp;&nbsp; 4) Fill Null values for feature <b>drive</b> with value <b>fwd</b> as its the most common drivetrain.

#### Transform values:
&nbsp;&nbsp;&nbsp; 1) Transform feature <b>"Year"</b> to <b>age</b>. </br>
&nbsp;&nbsp;&nbsp; 2) Use only the main <b>model</b> of the vehicle by ignoring the trims. Also, ignore the word "cylinders" in feature <b>cylinder</b>. </br>
&nbsp;&nbsp;&nbsp; 3) Since <b>automatic</b> transmission is the most popular in the US, we can change the transmission having value as <b>"other"</b> to <b>"automatic"</b> </br>
&nbsp;&nbsp;&nbsp; 4) Transform column <b>title_status</b> by moving status <b>"lien"</b> to <b>"clean"</b> and all other statuses to <b>"other"</b>.</br>
&nbsp;&nbsp;&nbsp; 5) There are used cars that are over <b>100</b> years old in the dataset. To make the year relavent, we can eliminate used cars beyond <b>30</b> yrs old from our dataset. </br>
&nbsp;&nbsp;&nbsp; 6) Transform the <b>categorical</b> variables to <b>numeric</b> to be used for further analysis. </br>

#### Modelling:
Perform Linear, Lasso and Ridge regression on the resuling dataset




