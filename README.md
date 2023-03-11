[Website](https://assiaoua.github.io/tennis-data-story/) | [Github of the website ](https://github.com/assiaoua/tennis-data-story)| [Process book](https://github.com/com-480-data-visualization/datavis-project-2022-plot-twist/blob/main/Process%20book%20DV.pdf) | [Screencast](https://youtu.be/h821G34XrvY)

# Project of Data Visualization (COM-480)

| Student's name | SCIPER |
| -------------- | ------ |
| Alexandre Variengien| 337357 |
| Félicie Giraud-Sauveur| 284220 |
| Assia Ouanaya| 288251 |

[Milestone 1](#milestone-1-23rd-April-5pm) • [Milestone 2](#milestone-2-7th-May-5pm) • [Milestone 3](#milestone-3-4th-June-5pm)

## Milestone 1 (23rd April, 5pm)

**10% of the final grade**

This is a preliminary milestone to let you set up goals for your final project and assess the feasibility of your ideas.
Please, fill the following sections about your project.
*(max. 2000 characters per section)*

### Dataset

We chose to work with the ATP Tennis with Betting Odds found on [Kaggle](https://www.kaggle.com/datasets/edoardoba/atp-tennis-data/metadata). 

The dataset consists of 36 120 matches summaries. 
Each line contains:
- Information about the tournament (name, location, etc...)
- Information about the match (surface, date, rounds, comment, etc...)
- Information about the players (winner, loser, nationalities, world ranking, ATP points, etc...)
- Physical information about the players (playing hand, weights, height, etc...)
- Betting odds information (odds of match loser and winner from different online platforms)

For clarity, we did not present all of the 54 columns. The full descriptions can be found in the "milestone1.ipynb".

### Problematic

Since its creation in the nineteenth century, tennis has kept increasing in popularity to become one of the most played sports, and one of the most mediatized. You cannot ignore the names of the best figures such as Rafael Nadal or Novak Djokovic that compete in the unmissable Grand Slam tournaments: from Roland Garros to Wellington.
Nonetheless, the usual picture of tennis shared by the media tends to focus on a tiny subset of both the events and the players.
With this visualization, we want to give a holistic image of the community of professional tennis players, its global structure.  

First, we want to visualize the pattern of matchmaking through tournaments and through the seasons. All the tournaments can be seen as a graph whose nodes are the players and the edges are the tennis matches. We want to visualize the structure of this graph.  

In addition to the competitions, we would focus on individual players: besides the well-known superstars, what is the usual career of a professional tennis player, what are his characteristics? We want to share the stories of the ones whose names will never appear in any international headlines, while they make up the biggest chunk of the community.  
Those questions, such as the role of right or left handedness, are the subject of common discussions. Through the use of data visualization, we aim at shedding new light on these topics.  

This visualization is intended for the general public, with no particular interest in tennis. Our goal is to show the fascinating patterns that emerge in the data visualization from this field and to share the statistical stories that never appear in newspapers.

### Exploratory Data Analysis

See jupyter notebook "milestone1.ipynb".

### Related work/Our ideas

These type of data about tennis can be presented in a very classical way in the form of tables detailing the statistics of the players according to different criteria. This is the case for instance on these two reference sites: http://www.tennisabstract.com/cgi-bin/leaders.cgi?f=B0s00o1 or https://www.atptour.com/en/stats.  
There are also much more original ways to present and play with this type of data as can be seen on these two sites of data visualization: https://tennisvisuals.com/ or https://www.nationalgeographic.com/culture/article/150906-data-points-tennis-tracking.
We can also find analyses that already exist on similar data like here: https://www.kaggle.com/code/nescobar/data-visualizations-of-atp-tennis-competitions/notebook.

Our idea is original in the sense that it aims to show much more the links between all players and countries. Our ambitions for the moment are as follows:

- ***Tab 1*: Network between players:**
    - Make a network that connects players who have played a match. Interactivity: you can move the nodes with the mouse to make the network move.
    - A node corresponds to a player (with the picture of the player in the node). The bigger the node, the more matches the player has made. 
    - Slider to choose the year.
    - Buttons to apply filters according to different variables: Location, Tournament, Serie, Court, Surface, Players ranking range.
    - Possibility to mouseover a node (player): information about the player is displayed with for instance the number of matches played in ATP by series per year, the number of wins and the number of losses according to the year/the tournament/the type of court/the type of surface, his nationality, his weight, his year of start as a pro and his playing hand, a list with his main opponents. 
    - It is also possible to mouseover on the edge between two players: information is displayed with the characteristics of the matches. For instance: locations, tournaments, dates, series, courts, surfaces, rounds, winners, ranks and points of the players at the beginning of the tournament, number of games won by each player for each set, number of sets won by each player, comments, odds.
    - Inspirations: http://www.claudiobellei.com/2017/02/04/viznetworks/ ; http://bl.ocks.org/eesur/be2abfb3155a38be4de4 ; https://bl.ocks.org/steveharoz/8c3e2524079a8c440df60c1ab72b5d03 ; https://d3-graph-gallery.com/graph/interactivity_button.html ; https://sylhare.github.io/2020/06/10/Advanced-node-network-graph-d3.html

- ***Tab 2*: World map visualisation:**

    - The goal of this animated visualization is to picture the geographical movement of a tennis player going from tournement to tournement. 
    - Each player is represented by a colored circle on a world map, the movement of the circle follows the cities the player visited during the tournements present in the database.
    - The map will be an [azimuthal equidistant polar projection](https://en.wikipedia.org/wiki/Azimuthal_equidistant_projection) to be able to show movement around the globe with minimal discoutinuosities induced by wraping at the corners.
    -The color of the circles will correspond to the ranking of the player (e.g. the more yellow, the higher rank). This could be useful to visualize the levels of the player present at a given tournament.
    - Inpiration of the visualization (A flow where a colored icon correspond to one person, we added the geographical component): https://www.nytimes.com/interactive/2018/03/19/upshot/race-class-white-and-black-men.html 


- ***Tab 3*: Bart Charts moving over time:**
    - Two bart charts on the same line with the bars moving as the years go by.
    - A first bart chart to show the evolution of the countries ranking in terms of number of wins or points or players etc...
    - A second bart chart to show the evolution of the players in terms of number of wins or points or number of matches etc...
    - Button to apply filters according to different variables: Series, Court, Surface.
    - Inspiration: https://observablehq.com/@d3/bar-chart-race  

- ***Tab 4*: Slot Machine between 2 players (optional, to be implemented if we have time):**
	- The goal would be to implement a slot machine that chooses randomly 2 players and displays statistics about their last matches between these 2 players. 
	- The slot machine would display basic information about the 2 players such as Name, image, nationality and rank. The statitistics shown between the two players are the number of matches played (at least >= 1), the number of wins of the 1st player, at which country and tournament they most played in.
	- You can click on a button "SHUFFLE" that will pick 2 new players. 
	- Some visualization inspiration https://josex2r.github.io/jQuery-SlotMachine/ & https://odhyan.com/slot/.

- ***(Side ideas for the site)***:
    - Make the loading symbol in the form of a spinning tennis ball.
    - Make a mascot in the form of a tennis racket to explain the site's features at the beginning.
    - Make symbols for the selection of variables, a small cup for the winner, flags for the nationalities, etc...

*NB : The dataset is extracted from the Kaggle database [ATP tennis data](https://www.kaggle.com/datasets/edoardoba/atp-tennis-data) and only a "Djokovic vs Nadal quick analysis" is presented as analysis of this data.*


## Milestone 2 (7th May, 5pm)

**10% of the final grade**

Our final product will take the form of a website. On the principal page, animated videos of the visualizations will be shown, and the user could select one by clicking on them. No particular order will be privileged.
We plan to include a minimal amount of text on each page, just enough to let the user explore the data by him or herself.

We describe the four independent pieces of our product below. The three first ones are core to our project, while the fourth is optional. Furthermore, in each of the descriptions, we shared the features of the visualization necessary and possible extensions.


### Visualisation Descriptions

#### Tab 1: Network between players

The first visualization will be a network that connects players who have played a match. A node corresponds to a player (with the picture of the player in the node). The bigger the node, the more matches the player has made. Inspiration: http://www.claudiobellei.com/2017/02/04/viznetworks/ and http://bl.ocks.org/eesur/be2abfb3155a38be4de4.

<img src="/img/network_select.png" alt="network_select" width="1100"/>

It will be possible to move the nodes with the mouse to make the network move. Once moved, the node is frozen in its new location until the user clicks it again. This makes it easier to study a node even when there are many nodes on the page.

<img src="/img/network_moving.png" alt="network_moving" width="200"/>

A slider will also enable to choose the year or the range of Winners rank. Inspiration: http://www.claudiobellei.com/2017/02/04/viznetworks/.

<img src="/img/network_curseur.png" alt="network_curseur" width="300"/>

When we pass the mouse over a node (player), information about the player will be displayed for instance: the number of matches played in ATP by series per year, the number of wins, and the number of losses according to the year/the tournament/the type of court/the type of surface, his nationality, his weight, his year of start as a pro and his playing hand, a list with his main opponents. Inspiration: https://sylhare.github.io/2020/06/10/Advanced-node-network-graph-d3.html.

<img src="/img/network_joueur.png" alt="network_joueur" width="400"/>

When we pass the mouse over the edge between two players, information will be displayed with the characteristics of the matches. For instance: locations, tournaments, dates, series, courts, surfaces, rounds, winners, ranks, and points of the players at the beginning of the tournament, number of games won by each player for each set, number of sets won by each player, comments, odds. Inspiration: https://sylhare.github.io/2020/06/10/Advanced-node-network-graph-d3.html.

<img src="/img/network_edge.png" alt="network_edge" width="600"/>

The courses on "web development", "Javascript", "D3.js" and "interactive" were useful to build this visualization. The future "graph" course could also be useful.

_For the moment this visualization is being debugged, so it is not provided in the skeleton of the site but will be present in the final product. In addition, the case of images is particularly complex so it is not part of the minimum product and remains an option for the future.  
For information, the first versions of the html/css/js files are provided in the "tab1_network" folder._

#### Tab 2: World map visualisation
The second visualization will be a map of the world. The map will contain colored moving circles and fixed points.

Each circle corresponds to a player from the dataset, and the movement of the circle on the map corresponds to the path through the cities where the player participated in matches. 
The fixed point corresponds to the cities where matches are played, and information about the name of the tournaments it hosts.
New players appear with a fade-in at the location of their first tournament and similarly disappear with a fade-out after the last match.

The circles are colored according to a color scale, linked to their rank (the color change during time, after matches when the rank is updated).

The user can interact with a slider that specifies the date. By default, the slider is moving at a constant speed, but the user can fix the slider at any time to investigate precise dynamics.

The broad goal of the visualization is to visualize the geographical movements of the whole community of professional tennis players through the seasons.

More precisely, we want to reveal patterns at different times and geographical scales, for instance, inside a given year, what is the usual schedule of tournaments for players? Can we observe that the participants of the tournament share a similar ranking, or are the levels of players uniformly distributed?
On a time scale of several years, this visualization can enable us to visualize the emergence of new tournaments or the evolution of their popularity.

We provided a first minimal working example of the visualization. There are further details to implement, test different alternatives and select one. These include:
* Adding information about the tournaments.
* Dealing with slow points that seem fixed. We plan to make these circles transparent and increase their opacity once they are near their final position.
* The placement of the zoomed-in map of Europe. Dealing with zoom in general.
* Optionally, add more interaction such as an option to select players based on different criteria such as their nationalities for instance. This could also be displaying information about a player by hovering over a  circle.
* Optionally, we could try to add a trace for some of the points to make the movement easier to visualize as a whole, essentially turning the visualization into an animated flow map.

An image illutrating the visualization:
<img src="/img/map_maquette.png" alt="maquette" width="1200"/>
The projection we used was the Winkel tripel. We didn't choose the polar azimuthal equidistant projection, even if it would have reduced the teleportation at the border. We thought that users would not have been familiar with it, and would have been too confused to precisely understand the many movements happening at the same time. 

We used `d3` as the main visualization tool, and the `d3-geo` package to deal with geographical interpolation and projection. To ease the development, we used an `òbservablehq` notebook. Moreover, the lectures on maps, color perception, interaction, "designing viz" and "do and don't in viz" were all useful to design this visualization.

#### Tab 3: Bar chart race

* Two bar charts one representing the country ranking per year (accumulated number of match wins) and another for the players ranking with respect to their accumulated ATP points per year.

* Minimal Viable Product :
    * Simple bar chart race with the year advancing in the bottom right corner
    * Different colors for the different entities (countries/players)

* Further developments:
    * Add a timeline for the years so we can select the year of interest.
    * Add a filter to select different variables: Series, Court, Surface. 
    * For the countries, another metric that can be tested is the number of matches won divided by the number of matches played.
    * (Optional) Test to see if a fixed scaling instead of moving one is more aesthetically pleasing.

The courses concerning "Design for Data Viz", "Color Perception" "Javascript", "D3.js" and "Interaction" were used to help build this visualization. To ease the development, we used an observablehq notebook.

#### Tab 4: Slot Machine (optional, to be implemented if we have time)

The goal would be to implement a slot machine that chooses randomly 2 players and displays statistics about their last matches between these 2 players. There is no MVP for this tab as it is an optional and further development of our website. The courses concerning "Design for Data Viz", "Color Perception" "Javascript", "D3.js" and "Interaction" were used to help build this visualization. 

<img src="/img/slot.png" alt="slot" width="1100"/>

### Functional project prototype review

[Website](https://assiaoua.github.io/tennis-data-story/) | [Github](https://github.com/assiaoua/tennis-data-story) linked to the website

## Milestone 3 (4th June, 5pm)

**80% of the final grade**

[Website](https://assiaoua.github.io/tennis-data-story/) | [Github of the website ](https://github.com/assiaoua/tennis-data-story)| [Process book](https://github.com/com-480-data-visualization/datavis-project-2022-plot-twist/blob/main/Process%20book%20DV.pdf) | [Screencast](https://youtu.be/h821G34XrvY)

