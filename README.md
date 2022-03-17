# AML RoadShow Hackathon: AML For Coders

[Azure Account Signup and AML Workspace Deployment](RegisterForAzureAccount.md)

### Day 1: Creating, Register & Deploy a Model Leveraging an ACI endpoint.

Insider your Data folder – you will see a very familiar dataset, which has been split up into 2 files (along with a few columns have been removed).

- [Train1.csv](./Data/Train1.csv)
- [Train2.csv](./Data/Train2.csv)

Dataset to leverage with your rest endpoint:
- [Hold.csv](./Data/Hold.csv)

The titanic dataset. You will work without AutoML to create a classication model based on an 80-20 split. You may decide you want to run an AutoML job to help you determine what model will provide you with the best results. We are going for **accuracy**.  You are being challenged to:

Explore the 2 datasets, join them together based on passenger_id and engeering features for training your model inside an AML experiment.
Create a model to predict if a person will survive on the titanic.
Create a rest-endpoint that can be called to predict survival that will be compared to a hold out dataset.

Activity Requirements:

    1. Required attributes to log during a training run to complete the exercise:
        a. Log in an experiment run your AUC for your test data
        b. Log in an experiment run Row size of the test dataset
        c. Log in an experiment run your ROC curve
        d. Log a Confusion Matrix
    2. Register your model
    3. Deploy to an ACI endpoint your registered model
    4. Inference the hold out dataset using your rest api with the holdout dataset.
    5. Calculate your accuracy

**Things to consider:**

This is a dirty dataset. As such you might want to figure out what data is missing and how you are going to handle that challenge.

Nice article: https://towardsdatascience.com/step-by-step-tutorial-of-sci-kit-learn-pipeline-62402d5629b6

Creating the model - once deployed, you will need to be able to replicate the environment used to create the model, if you use a conda yml file to define your environment from the start, deployment will probably be easier. Check out notebook: [001_Environments.ipynb](001_Environments.ipynb)

Dataset(s) Features:
    passendger_id: id of passenger
    survived: Survival 0 = No, 1 = Yes
    pclass: Passenger Class (1 = 1st, 2 = 2nd, 3 = 3rd)
    name: Name
    sex: Sex
    age: Age
    sibsp: Number of Siblings/Spouses on board
    parch: number of parents/children on board
    ticket: ticket number
    fare: passenger fare
    cabin: Cabin
    embarked: Port of Embarkation (C = Cherbourg, Q = Queenstown, S = Southhampton)
    home.dest: Destination

### Day 2: Create an inferencing pipeline 

- Register the datasets:
[Day2_Inference1.csv](./Data/Day2_Inference1.csv)
and
[Day2_Inference2.csv](./Data/Day2_inference2.csv)


- Consume the datasets, and run batch prediction saving a dataset and registering to the AML workspace.


