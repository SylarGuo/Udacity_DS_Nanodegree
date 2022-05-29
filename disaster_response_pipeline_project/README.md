# Disaster Response Pipeline Project

### Project Summary
This Disaster Response Pipeline project evaluates disaster data from Figure Eight in order to create a model for a disaster message classification API. I built a machine learning pipeline to classify messages submitted during disasters so that they may be sent to the proper disaster aid organization. A web app is included in the project, which is allowed to enter any new message and receive classifications in different categories.

### File Descriptions
app    

| - template    
| |- master.html # main page of web app    
| |- go.html # classification result page of web app    
|- run.py # Flask file that runs app    


data    

|- disaster_categories.csv # data to process    
|- disaster_messages.csv # data to process    
|- process_data.py # data cleaning pipeline    
|- InsertDatabaseName.db # database to save clean data to     


models   

|- train_classifier.py # machine learning pipeline     
|- classifier.pkl # saved model     


README.md    

### Components
There are three components I completed for this project. 

#### 1. ETL Pipeline
A Python script, `process_data.py`, writes a data cleaning pipeline that:

 - Loads the messages and categories datasets
 - Merges the two datasets
 - Cleans the data
 - Stores it in a SQLite database
 
 
#### 2. ML Pipeline
A Python script, `train_classifier.py`, writes a machine learning pipeline that:

 - Loads data from the SQLite database
 - Splits the dataset into training and test sets
 - Builds a text processing and machine learning pipeline
 - Trains and tunes a model using GridSearchCV
 - Outputs results on the test set
 - Exports the final model as a pickle file
 

#### 3. Flask Web App
A web app is included in the project, which is allowed to enter any new message and receive classifications in different categories.

### Instructions:
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/
