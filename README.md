### Betting on 21.5
##### **MID-TERM project | A simple strategy to beat the bookies using ML.**
---
**_Thanks to @ albertoviciana for being the best teammate ever._**
<br />
<br />

![](https://github.com/CommanderPoe/tennis-prediction/blob/master/img_up%20(courtesy%20of%20unsplash)/hermes-rivera-newhL3aprGk-unsplash.jpg)

<br />
<br />

### The dataset
The tennis dataset `shape` is (28335,42). It can be found here: [tennis-data.co.uk](http://tennis-data.co.uk/alldata.php).
<br />
<br />

### Columns Description:

- |__ATP__| -> Tournament ID. _'int64'_
- |__Location__| -> Location of the tournament. _'object'_
- |__Tournament__| -> Name of the Tournament _'object'_
- |__Date__| -> Date of the tournament. _'datetime'_
- |__Series__| -> Type of tournament. _'object'_
- |__Court__| -> Surface of the match. _'object'_
- |__Round__| -> Round of the competition. _'object'_
- |__Best of__| -> Max amount of sets that can be played in a match. _'float64'_
- |__Winner__| & |__Loser__| -> Winner/Loser of the match. _'object'_
- |__LRank__| & |__Loser__| -> ATP Rank of the winner/loser. _'float64'_
- |__WPts__| & |__LPts__| -> ATP points in Rank of the winner/loser. _'float64'_
- |__W1__| - |__W5__|, |__L1__| - |__L5__| -> Games won or lost by each player on that match. _'float64'_
- |__Comment__| -> Comments on the state of the match. _'object'_  
- |__Wsets__| & |__Lsets__| -> Sets won by the winner/loser. _'float64'_
- |__B365W__| & |__B365W__| -> Bookies odds (Bet 365). _'float64'_
- |__EXW__| & |__EXL__| -> Bookies odds (Express). '_float64'_ _'object'_
- |__SJW__| & |__SJL__| -> Bookies odds (SJ). _'float64'_
- |__PSW__| & |__PSL__| -> Bookies odds (Pinnacle). _'float64'_
- |__LBW__| & |__LBL__| -> Bookies odds (Liberty). _'float64'_
- |__MaxW__| & |__MaxL__| -> Max odds offered taken oddsport. _'float64'_
- |__MinW__| & |__MinL__| -> Mix odds offered taken oddsport. ??
- |__AvgW__| & |__AvgL__| -> Avg odds offered. _'float64'_
<br />
<br />

### Introduction
For the midterm project at Ironhack we decided to find a way to get rich quickly (jokes on us :smile:). We focused on a simple analysis of the betting market and tried to build a strategy to beat the bookies using Machine Learning. Historical data was crucial for our analysis, this is the reason why we picked every [major tournament](https://en.wikipedia.org/wiki/2020_ATP_Challenger_Tour) ie; ATPs, GrandSlams, Masters and MasterCups played from 2010-2021 and skipped small tournaments like [Challengers](https://en.wikipedia.org/wiki/2020_ATP_Challenger_Tour) or [ITFs](https://en.wikipedia.org/wiki/International_Tennis_Federation) tournaments.

We only took into account [ranked](https://www.atptour.com/en/rankings/singles) players that participated in the most important tournaments of the year, hence we did not see many matches in a single year (2000 - 2500). Compared to other sports like football where that number is reached by the first and second division of any single European country we needed to squeeze the volumen in order to reduce the variance.
<br />
<br />

### Goal
Get a positive Return on Investment **(ROI)** betting on the amount of games played (OVER/UNDER 21.5)  after a decent number of matches. Not the conventional winner/loser
