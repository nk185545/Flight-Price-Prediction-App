# Flight-Fare-Predction-App

This application tell us about the Fare of flight .

The App Link :   https://flight-price-predition-app-nk.herokuapp.com/

Application Video link :   https://drive.google.com/file/d/1ZUmiqKlnXbiQRqVKEpiKNNe_2zE3BjN1/view?usp=sharing

Some Glimpses of Application : 

![fpp1](https://user-images.githubusercontent.com/80478598/115141674-4846ce00-a05b-11eb-8771-491eea56ae47.png)
![fpp2](https://user-images.githubusercontent.com/80478598/115141678-4c72eb80-a05b-11eb-8879-889ba96cf1ae.png)
![fpp3](https://user-images.githubusercontent.com/80478598/115141680-4e3caf00-a05b-11eb-9905-035324d4e990.png)



Journey : 

*1) Data Collection* :  Data collected from the Kaggle . 
    *about data* : Data Columns are : Airline ,Date_of_journey, Source, Destination, Route , Dep_Time, Arrival_Time, Duration, Total_Stop, Additional_info,Price . 
    
    As a data scientist, we will predict the total predicted Fare for flight when user give some input .(input : Departure_Date, Arrival_Date, Source, Destination, number_of_stops and airline_type .)
    
    
*2) Data Preprocessing :* 
        The major thing in this project is "Data Preprocessing "  ,because there are all columns(except- Price) of categorical-type and some are string but actually they are "Date" type columns .
        
        a)Date_of_Journey is a object data type, Therefore, we have to convert this datatype into timestamp so as to use this column properly for prediction. we use datetime and fetch day and month and made two seperate columns named as "Journey_day" and "Journey_month" and deleted "Date of journey" column.
        
        b) Similar to Date_of_Journey we  extracted values(hour and minutes) from "Dep_Time" using DateTime and made two seperate column names as "Dep_hour" and        "Dep_min" and deleted "Dep_Time" colimn.
        
        c) Similar to Date_of_Journey we  extracted values(hour and minutes) from "Arrival_Time" using DateTime and made two seperate column names as "Arrival_hour" and "Arrival_min" and deleted "Arrival_Time" colimn.
        
        d) In "Duration" column there are values like: 2hr 50min , 40 min .... So from there values extract hours and minutes seperately and made two columns "Duration_hour" and "Duration_min"  and deleted "Duration" column.
        
        e) Then we have Source and Destination two columns . The values(places) have no impact on price ,so used *ONE-HOT-ENCODING* .
        
        f) There is one column named as "Airline" . for this used *ONE-HOT-ENCODING* .
        
        g) then deleted the "Route" and "Additional_info" columns.(Additional_info" has mostly 80% no-info data) .
        
        h) There is  one columns named as  "total_stop". values are : non-stop,1 stop, 2 stop, 3 stops, 4 stops. According to data, which has more number of stops that has more fare(price) . SO used *ORDINAL-ENCODING* . 
        
        g) then combine all these data and remove non-required columns .
        
        h) now there  is no null values and all data is in integer datatype.
        
        i) Now we can build machine learning models .
        
        

    
*3) Model building* : 

    a) split the dataset into X(independent features) and y(dependent features) .
    
    b) perform train_test_split .
    
    c) try linear regression, RandomForestRegressor with hyperparameter tuning. 
    
    d) obsered that RandomForestRegressor with some parameters(got from hyperparameter tuning) has highest score and lowest error . so save this model using pickle.

*4) Model deployment* : 

    a) using flask framework , we deployed this model on HEROKU platform .
    
App link : https://flight-price-predition-app-nk.herokuapp.com/
