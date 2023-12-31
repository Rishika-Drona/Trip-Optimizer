# Travel Time Optimization via Ant Colony and Genetic Evolution

For this project, I have tackled the travel time optimization problem for taxi vehicles. This can be framed as the *Traveling Salesman Problem*, a well-known computer science problem. The objective is to find the shortest route that visits a set of locations. For this problem, optimization techniques are required to intelligently search the solution space and find near-optimal solutions. More specifically, I first used XGBoost model to predict travel times between every pair of pick-up and drop-off locations. Then, I used evolutionary algorithms, namely ant colony and genetic, to find the best travel itinerary for the vehicles in the data.


## Dataset

The data is the [NYC Taxi and Limousine Commission Trip Record](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page) data, already downloaded on [Kaggle](https://www.kaggle.com/c/nyc-taxi-trip-duration/data). I have the monthly data in the year 2021 for yellow taxi, green taxi, and for-hire vehicles. The dataset has close to 1.5 million trip records with 11 attributes.



## Requirements
* python3
* matplotlib 
* numpy
* pandas
* xgboost
* geopy

## Installation
```
$ python3 -m pip install xgboost
$ python3 -m pip install geopy
```

## Usage
### Data Visualization
```
$ python3 basicAnalysis.py
$ python3 sophisticatedAnalysis.py
```
### Predictive Modeling
```
$ python3 XGBoost.py
```
### Evolutionary Algorithms
```
$ python3 aco_main.py -h
usage: aco_main.py [-h] [--verbose] loc_count ant_count g alpha beta rho q

positional arguments:
  loc_count   number of locations (default is 15)
  ant_count   number of ants to use (default is 10)
  g           number of generations (default is 100)
  alpha       relative importance of pheromone (default is 1.0)
  beta        relative importance of heuristic information (default is 10.0)
  rho         pheromone residual coefficient (default is 0.5)
  q           pheromone intensity (default is 10.0)

optional arguments:
  -h, --help  show this help message and exit
  --verbose   print out each generation cost and best path
```
```
$ python3 genetic_evo_main.py -h
usage: genetic_evo_main.py [-h] [--verbose] loc_count n g m c

positional arguments:
  loc_count   number of locations (default is 15)
  n           population size (default is 10)
  g           number of generations (default is 100)
  m           mutation factor (default is 0.5)
  c           crossover rate (default is 0.7)

optional arguments:
  -h, --help  show this help message and exit
  --verbose   print out each generation cost and best path
```
## Output
![](https://i.imgur.com/9Iji3RD.gif)
![](https://i.imgur.com/S490pPp.gif)
