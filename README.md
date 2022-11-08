# Bike Share Rebalancing With Mathematical Optimization

## Problem
Using historical Citi-bike data in NYC and Jersey area during July 2022, we like to know:

- What is the demand for bikes per hour at each station during the first week of August?
- Knowing the demand, how can we minimize loss of sale?

We use a mixture of Machine Learning (ML) and Mathematical Optimization (MO) to solve this problem.

## Repo Guide
- The ML model to predict the number of in-flow and out-flow of bikes per hour at each station
  for the first week of August, can be found in the [predict_bike_flow](predict_bike_flow.ipynb) notebook.
- The MO model to decide how many bikes should be added to or removed from each station
  during each hour (with the goal of minimizing total loss of sale) is in the [bike_rebalancing](bike_rebalancing.ipynb) notebook. 
- The data is collected from the Citi-bike data website. They are processed in [predict_bike_flow](predict_bike_flow.ipynb) notebook.
- The [stations_flow.csv](stations_flow.csv) and [top_stations.csv](top_stations.csv) are the outputs of ML model 
  that are used as inputs for the MO model. Of course, you can run the [predict_bike_flow](predict_bike_flow.ipynb) notebook and 
  or even modify it as you please to get new results. Just ensure the format of the output is similar
  in case you like to use the MO model of [bike_rebalancing](bike_rebalancing.ipynb) notebook.

The MO model size is intentionally small to ensure even those without access to Gurobi license can run the model 
(check out [License Requirement](#license-requirement) section for more info about the license).

## Google Colab
If you like to access the notebook in Google Colab, click on 
[this link](https://colab.research.google.com/github/decision-spot/bike_share/blob/main/bike_rebalancing.ipynb).
When you open the notebook, there will be further instructions under "For Google Colab Only" section.

Note that you must sign in with a Google account to be able to run the code in Colab.

### What is Google Colab?
Google Colab is a free, online Jupyter Notebook environment that allows you to 
write and execute Python code through your browser.
If you're curious to know the steps needed for loading a repo in Google Colab from scratch, here they are:
- Go to https://colab.research.google.com/ (you must sign in with your Google account).
- Click on the GitHub tab, and in the search box, enter this repo's URL (https://github.com/decision-spot/bike_share).
- You should see the name of both notebooks. Click on the one you want (e.g. `bike_rebalancing.ipynb`). and it opens in a new tab.

## License Requirement
The problem is modeled using Gurobi Python API. So, a Gurobi license is required to run this model.
If you don't have a license, you can request a free commercial evaluation license 
or a free academic license [here](https://www.gurobi.com/downloads/).
The data used in the MO model is small enough to run the model with gurobi restricted license
(available via `pip install gurobi` as shown in the notebook).