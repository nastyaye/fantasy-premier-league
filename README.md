# Fantasy Premier League Stats, Visualizations &amp; Analysis

Simple python web app with FPL stats, visualizations and anlysis.
Live at [fantasy.elek.hr](http://fantasy.elek.hr/).

## Running locally
### With Docker
  - Set the value of `IP` environment variable in `variables.env` to `127.0.0.1`
  - Run `docker-compose up`
  - Application will be available at [localhost](http://localhost/)
  
### Natively
  - Run `pip install -r requirements.txt` to install requirements
  - Set the `IP` environment variable to `127.0.0.1` (eq. in PowerShell run `$env:FPL_IP="127.0.0.1"`)
  - Set the `FPL_SEASON` environment variable to `2018-19` (eq. in PowerShell run `$env:FPL_SEASON="2018-19"`)
  - Open up a terminal window and run `python .\web\app.py`. Wait until application starts. 
  - In another termianl window, run `bokeh serve .\bokeh\vpc.py --allow-websocket-origin=localhost:5000`
  - Application will be available at [localhost:5000](http://localhost:5000/)

## Features
Currently, there are three avaliable features
	- Players Comparison
	- Points Per Cost Analysis
	- 2D Analysis

### Players Comparison
Players Comparison is exactly what it sounds it is. Take two players and compare them on number of factors: price, gained points, performance index, in-game stats, or popularity among FPL managers. There are also some handy line plots visualizing the trends in player's price, points, playing time and ICT index.

![comparison](https://raw.githubusercontent.com/antoniaelek/fantasy-premier-league/master/static/images/comparison.png)

### Points Per Cost Analysis
Points Per Cost scatter plot visualizes relationship between each player's price and their average points gain. Blue circles on the plot are goalkeepers, orange ones are defenders, midfielders are in green and forwards are red circles. Larger circle means you get better value for your money. It is also possible to filter plot by a certain position, for better visibility.

![points-per-cost](https://raw.githubusercontent.com/antoniaelek/fantasy-premier-league/master/static/images/vpc.png)

### 2D Analysis
2D analysis plot visualizes relationship between any pair of each player's aggregated metrics. For example, the plot given in the screenshot below shows the relationship between average players' ICT index and their average points gain. It is possible to see right away that this relationship is a linear one for midfielders and forwards (green and red circles), but not so much for defenders and goalkeepers (orange and blue dots).

![points-per-cost](https://raw.githubusercontent.com/antoniaelek/fantasy-premier-league/master/static/images/aggregates.png)
