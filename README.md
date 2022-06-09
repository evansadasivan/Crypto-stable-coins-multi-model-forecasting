# Project-2
Northwestern Bootcamp Project 2 - Evan Sadasivan, Avinash Patel and Christine Nashihibi

## Installation Guide

* ### Anaconda - conda environments 
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

            pip install auto-ts
            pip install statsmodels
            pip install tscv


## Overall Aim

## General Process

* ## Data collection and cleaning 

* ## Crypto Analysis and Plots

* ## Stable Coin Analysis and Plots



Notes:
Revisit the crypto and stable coin data that we analyzed in the first project. We will add some additional midcap and small cap cryptos to our analysis. We will use SKLearn and Keras or TensorFlow to make a predictive model. Using data through the recent Terra/Luna Crash to make predictions about the future of crypto.

Hypothesis: Despite the recent downward trend in crypto/stable coins within the previous six months, they continue to be a great digital currency and investment. We will use our predictive model to determine the next several months and beyond.

Possible addition: We then use NLP to examine how people have responded to crypto and how we predict they will respond.

Using Open, Close, High, Low, Volume
Price is target (y)



What models to use?
Evan - SK learn on cryptos
Christine - Keras on cryptos
Avi - stablecoins & Auto TS
