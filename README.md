windprediction
==============

Apply Bayes net machine learning algorithms to make short-term wind predictions. Research done with Dr. Ole Mengshoel at Carnegie Mellon Silicon Valley.

#### STRUCTURE
data - directory containing datasets grabbed from wundergound

models - directory containing Bayesian network models generating using Weka

results - directory containing output from running Weka's BayesNet classifier on the datasets and models

scripts - directory containing Python scripts that grab data from wunderground, preprocess the data, and run Weka's BayesNet on the models and data

wind_prediction_presentation.pdf - slides explaining the project and presenting the results

#### USAGE
##### INSTALL WEKA


##### GENERATE DATA
1. Locate desired weather station on Weather Underground.
  1.1 Go to http://www.wundergound.com
  1.2 Use the search bar in the upper-right hand corner to search by city.
  1.3 Click on 'Change Station'.
  1.4 Browse among the stations for the area and note the station code (e.g. KCASANTA162).
2. Use the wu_csv script to grab the data.
  2.1 Open the wu_csv script using your favorite editor.
    2.1.1 vi scripts/wu_csv.py
  2.2 Change line 4 to the desired station.
    2.2.1 station = 'KCASANTA162'
  2.3 Run the script, redirecting the output in a CSV file.
    2.3.1 python scripts/wu_csv.py > data/KCASANTA162.raw.csv

##### PREPROCESS DATA
1. Use the preprocess script to prune and rearrange columns.
  1.1 Open the preprocess script using your favorite editor.
    1.1.1 vi scripts/preprocess.py
  1.2 Change line 3 to the desired station.
    1.2.1 station = 'data/KCASANTA162.raw.csv'
  1.3 Run the script, redirecting the output to a CSV file.
    1.3.1 python scripts/preprocess.py > data/KCASANTA162.csv
2. Use the nominalize script to discretize the data. Weka's BayesNet classifier requires data to be in this form.
  2.1 Run the script, which will nominalize all files whose filenames are in the form [STATIONNAME].csv in the data directory. No need to modify this script.
    2.1.1 python scripts/nominalize.py

##### CREATE BAYESNET MODEL


##### RUN BAYESNET CLASSIFIER
1. Use the run_bayes script to run Weka's BayesNet classifier for a particular model for all datasets.
  1.1 Open the run_bayes script using your favorite editor.
    1.1.1 vi scripts/run_bayes.py
  1.2 Change line 8 to the desired 
