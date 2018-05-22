# TrifactaHelloWorld
A first shot on trifacta data wrangling, documentation in the readme

## Cleaning sample data
1. The downloaded csv file is imported to Trifacta.
2. Trifacta automatically leads us to the transformer, where we can turn our messy data into clean data. 
![alt text](https://github.com/jabusch24/TrifactaHelloWorld/blob/master/images/1_start.PNG)

3. First of all, we investigate on the data types of our columns by clicking the column name bar and choosing the data type we would like to set. That way we learn that some rows in email are missing, similar to a couple of other columns. As the email is the most important data, we delete all rows that DO NOT contain any emails.
![alt text](https://github.com/jabusch24/TrifactaHelloWorld/blob/master/images/2_delete_rows.PNG)
We also know that we have duplicate email addresses. This step is not as simply done in Trifacta and requires a couple of steps, including creating a new column, sorting the email column and then comparing against the newly created column. The recipe n the follwing picture gives more detail.
![alt text](https://github.com/jabusch24/TrifactaHelloWorld/blob/master/images/3_remove_duplicates.PNG)

4. Then, the data quality bar will give us an indication of how many rows do not comply with our set data type. Consequently we find a couple of "uncompliant" data points. As we wish to keep the row data, we turn the missing or odd values in "age" and "gender" to NULL.
![alt text](https://github.com/jabusch24/TrifactaHelloWorld/blob/master/images/4_turn_missing_data_null.PNG)

5. The histogram enables us to see outliers or "strange" data. That way, we can identify that the "age" column starts at "-78" which of course doesnt make sense so we turn it into NULL. Voila, that was it and here is the final data set:
![alt text](https://github.com/jabusch24/TrifactaHelloWorld/blob/master/images/6_final_data_table.PNG)
with the final recipe: 
![alt text](https://github.com/jabusch24/TrifactaHelloWorld/blob/master/images/5_final_recipe.PNG)

6. Finally we simply export the final outcome csv to place it into our github.  
![alt text](https://github.com/jabusch24/TrifactaHelloWorld/blob/master/images/7_generate_results.PNG)

## Cleaning power outage data
In order to clean the data set "15-years-of-power-outages", I recommend the following cleaning steps:

1. First, I recommend changing the "Date_of_Restoration" and "Time_of_Restoration" to NULL wherever is is not in the appropriate format. 
2. Secondly, we trim the "Geographic_areas" and turn it into lowercase. 
3. "Number_of_customers_affected" appears to be quite dirty, thanks to many "Unknowns","0" and "N/A". Thus we get rid of those and turn them to NULL. Clearing them by statistical means would have too large of an impact. The result is a clear histogram with relevant information. 
4. Additionally, we need to get rid of any commas and additional strings, until we can finally change the datatype to an integer to create a relevant histogram. 
5. Finally, we split the tags into two seperate tag columns to analyze them appropriately. The screenshot shows a copy of the summary and the final recipe with data.
![alt text](https://github.com/jabusch24/TrifactaHelloWorld/blob/master/images/8_summary.PNG)
![alt text](https://github.com/jabusch24/TrifactaHelloWorld/blob/master/images/9_recipe.PNG)


