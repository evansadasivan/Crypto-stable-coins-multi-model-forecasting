# Project-2
Northwestern Bootcamp Project 2 - Evan Sadasivan, Avinash Patel and Christine Nashihibi

## Installation Guide - Technologies utilized

* ### Rapid API - Api Dojo - https://rapidapi.com/apidojo/api/investing-cryptocurrency-markets/

* ### Important to note that the stable coin analysis will require you to open the jupyter lab file in Google Colab. The crypto analysis will be handled with the following Anaconda environment, while the Google Colab instructions will just require a few pip installs. 

* ### Anaconda -
    * Navigate to the Anaconda website in order to download the appropriate installer.
    * https://www.anaconda.com/products/distribution#windows 

* ### Anaconda - conda environment 
            <!-- (After installing Anaconda we need to enable the terminal commands) -->

            conda init bash

            <!-- (Close your terminal and open a new one) -->

            conda update conda
            conda update anaconda

            <!-- (Now we need to create a suitable environment to run our jupyter lab and
             install libraries necessary for pyviz) -->

            conda activate base
            conda create -n pyvizenv python=3.7 anaconda -y

            conda activate pyvizenv

            conda install -c conda-forge python-dotenv -y
            conda install -c anaconda nb_conda -y
            conda install -c conda-forge nodejs=12 -y
            conda install -c pyviz holoviz -y
            conda install -c plotly plotly -y
            conda install -c conda-forge jupyterlab=2.2 -y
            conda install -c anaconda numpy==1.19 -y
            conda install -c conda-forge matplotlib==3.0.3 -y

            jupyter labextension install @jupyter-widgets/jupyterlab-manager --no-build
            jupyter labextension install jupyterlab-plotly --no-build
            jupyter labextension install plotlywidget --no-build
            jupyter labextension install @pyviz/jupyterlab_pyviz --no-build
            jupyter lab build

            <!-- (Remember to also setup a dot env file containing api keys)  -->

* ###  Other libraries - can be quick installed using the following commands in the pyviz environment:
            
            conda install -c conda-forge tensorflow -y
            pip install -U scikit-learn
            pip install imblearn
            
             <!-- (The following will need to be run in google co lab before importing anything and working with the machine learning models.) -->
            
            pip install "dask[complete]"
            pip install hvplot
            pip install auto-ts
            pip install statsmodels
            pip install tscv
            pip install python-dotenv
            


## Overall Aim

Despite the recent downward trend in crypto currencies and stable coins within the previous six months, they continue to be an integral digital currency and form of investment. We will utilize machine learning methods to predict the future outlook of cryto and stable coins for a few months ahead. The result will hopefully give us an educated guess as to how the market will shape out and would it be beneficial to invest or utilize digital currencies. 

The following currencies and coins will be the focus of the analysis:

* Bitcoin 
* Ethereum
* Luna
* Binance - BUSD stable coin
* Tether - USDT stable coin
* Dai - DAI stable coin 
* Coin (Circle) - USDC stable coin 

The models utilized for each form of analysis are listed ahead:
* Evan - SK learn on cryptos
* Christine - Keras on cryptos
* Avi - stablecoins & Auto TS


## General Process

* ## Data collection, Cleaning, Splitting, Fitting, Testing, and Predicting 
The data will be collected using API Dojo from Rapid API website. The link is provided in the the technology used section. After connection has been established we set up GET Requests to retreive the data. Pass the data into a json format for easier parsing and dataframe setup. Using Pandas we are able to parse the data to find the important financial information for the different instruments. Unfortunately the API will only provide 1 years worth of current data. In order to over come this problem we chose to call the data 3 times in with different params in order to get 3 years worth of data. Data will need to  be cleaned. We dropped 'perc_chg' and 'color' columns. We drop any duplicates in the 'date' column before setting the date as the index. Some columns like 'volume' must have the ',' and letter values like - 'K' , 'M', 'B' replaced or evaluated. The last part of the cleaning process will be changing the datatypes for the dataframe.

After having cleaned dataframes, depending on which model you utilize you must split the data into two dataframes: traning and testing. Training data will consist of your oldest data. The test data will be the most recent. A third group of data will need to be used to predict future values i.e. this data will consist of data that is newer and not found in either training or test data sets. Using Open, Close, High, Low, Volume as the features and Price is target (y). This allows us to understand which are the dependent vs independent variables  in our dataframes. Generally speaking in machine learning you will have to first import the necessary libraries to call your models. You instantiate the models by assinging it to a variable and calling the newly defined variable. After calling your model, you take the training data and fit the model using the data. This will train the model and get it ready for backtesting. We will now use the model to predict the values for the test data, this will give us an idea of the models performance. The last step is to feed the model with the newest data and see how the results compare with the data.



* ## Crypto Analysis and Plots
Our crypto analysis employed two libraries to create different models. The first library we used was scikit learn. Our goal was to set up a model that would learn to predict the daily close price of each crypto. The features we gave our models to look at were 'open','high','low', and 'volume'. To set up the models, we took our 3 years data for each of our three cryptos (BTC, ETH, LUNA) and used the following method to prepare our models. First, we split the data for each crypto into test and train splits. Using sklearn's predict feature, we predicted our target and then compared our predicted values against the actual close values for each day. Following this, we used the same steps on our test data. Finally, we looked at how our models would fare if they were tasked with predicting the future. To similute this future predicting, we gave the models an additional 30 days of data for each of our features and set it to predict the close values. 

In order to evaluate how our models performed, we graphed the predicted vs actual close values at each stage (train, test and future). These graphs can be found in the sklearn graphs folder. We also examined their performance by looking at the mean squared error at each stage. The BTC and ETH models were fairly successful in learning to predict the close values. The LUNA model is much more difficult to tell because the values are so much lower. The mean squared error for the luna model for simulated future prediction was 1.29279. Of course, we would have predicted anyway that because of the recent crash in LUNA value, that the model would likely not do as well.

* ## Stable Coin Analysis and Plots



## Notes/Appendix:

Possible additional forms of analysis: 
We then use NLP to examine how people have responded to crypto and how we predict they will respond.






