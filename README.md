### Betting on 21.5
##### **MID-TERM project | A simple strategy to beat the bookies using ML.**
---
**_Thanks to @albertoviciana for being the best teammate ever._**
<br />
<br />

**Big Disclaimer**: We are not betting experts and we do not reccomend trying this at home with real money if you don't know what you are doing or if you dont feel comfortable with losing  that money.

![](https://github.com/CommanderPoe/tennis-prediction/blob/master/img_up%20(courtesy%20of%20unsplash)/hermes-rivera-newhL3aprGk-unsplash.jpg)

<br />
<br />

### The dataset
The tennis dataset's `shape` we used is (28335,42), and it's the result of merging ten years of data. You can find it here: [tennis-data.co.uk](http://tennis-data.co.uk/alldata.php).
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

![raw_data_example](https://github.com/CommanderPoe/tennis-prediction/blob/master/img_up%20(courtesy%20of%20unsplash)/raw_table.png)
<br />
<br />

### Introduction
For the midterm project at Ironhack, we decided to find a way to get rich quickly (jokes on us :smile:). We focused on a simple analysis of the betting market and tried to build a strategy to beat the bookies using Machine Learning. We picked every [major tournament](https://en.wikipedia.org/wiki/2020_ATP_Challenger_Tour) ie; ATPs, GrandSlams, Masters and MasterCups played from 2010-2021 and skipped 'small' tournaments like [Challengers](https://en.wikipedia.org/wiki/2020_ATP_Challenger_Tour) or [ITFs](https://en.wikipedia.org/wiki/International_Tennis_Federation). Compared to other sports like football, where that number of matches is easily achievable by the first and second division of any single European country, we had to squeeze the volume to reduce the variance.

We only took into account ATP [ranked](https://www.atptour.com/en/rankings/singles) players.
<br />
<br />

### Goal
- Get a positive Return on Investment **(ROI)**.
- Big volume of matches.
- Find our niche (**OVER/UNDER 21.5**).
<br />
<br />

### Rules of tennis
Check [here](https://www.rulesofsport.com/sports/tennis.html) the rules of tennis.
<br />
<br />

### How does tennis betting work in a nutshell?
Let's say you bet 10€ on Nadal with an odd of 1.5: 
1. If he wins, you go back home with your 10€, plus 5€ of benefits.
2. If he loses you go back home with 0€
3. If he wins, as you bet 10€ and won 15€, your ROI (return on investment) is 50% on that specific bet.
4. If he looses, your ROI in -100%

If you want to dig deeper on how tennis betting work: Click [here](https://www.rookieroad.com/tennis/how-does-tennis-betting-work/).

For our specific market target (**OVER/UNDER 21.5**). Click [here](https://www.rookieroad.com/tennis/what-215-mean-tennis-betting/).
<br />
<br />

### Understanding the impact of ROI,YEILD & BEP.
***ROI or Return on Investment** is a measure of the efficiency of an investment – or how much money you can expect to make relative to the amount of money you risk.*

> PROFIT = (Wager Return - Amount Wagered)

> **ROI**= PROFIT / AMOUNT_WAGERED

The ROI in the above example would be equal to **5€** or **50%** if our pick wins.
<br />
<br />

***Yield** is a percentage calculation of the betting efficiency, depending on the selected bets and odds for the match or bet slip.*

> #= Number of bets 

> **YEILD** = (Profit - #) / #

Yield and ROI have a very similar formula. The difference is that ROI gives you your profit/loss ratio related to your initial investment, while yield gives you your average win on the turnover, for each of your individual bets.
<br />
<br />

*The **BEP or Break Even Point** is that magical number where if we win this percentage of the time we’ll at the very least not lose money, and ideally go beyond that to make a nice return on their investment.*

> **BEP** = 1 / odds 

Using 1.80 odds (more or less the avg offered by the bookies for the over/under 21.5 in tennis), we'd need to win 55.55% of the time. If we rounded up, we could say that anything above 56% is net profit in the long run.
<br />
<br />

### How to use the model?
Since there's no GUI or fancy web page to try our findings, if you wanted to use our model to predict tennis results, you would have to interact with the script thru Jupyter Notebook or using the Code Editor of your choice.

These were the two highest results we got from running several different Machine Learning models on over 20k matches.
<br />
<br />

> Logistic Regression
![LR](https://github.com/CommanderPoe/tennis-prediction/blob/master/img_up%20(courtesy%20of%20unsplash)/Screen%20Shot%202021-04-22%20at%2018.27.55.png)

> Gradient Boost
![LR](https://github.com/CommanderPoe/tennis-prediction/blob/master/img_up%20(courtesy%20of%20unsplash)/Screen%20Shot%202021-04-22%20at%2018.27.10.png)

Keep in mind; there's still a lot of room for improvement. Nonetheless, these numbers look like they are decently high for our purpose, staying above the **BEP**  = _55%._ 

No matter how bad we do in the first couple of matches because as long as we can keep this win rate of at least 60% we are making sure to book a nice yield of 5% on every bet regardless the outcome of single bats.

When it comes to this kind of situations you want one of these two things, or both if possible... 

1. Bet as much as posible and squeeze the volume to reduce the variance in the short term.
2. Bet big amounts of money on single bets since we are booking a nice +5% yeild on every bet.

**_Remember that bankroll management is an essential rule for anyone eager to play with markets in general. So, as a rule of thumbs, I would never recommend betting more than 3% of your total bankroll in a single bet_**.
<br />
<br />

To predict future matches using our model, you would need the following information about the tournaments and the players:

![final_table](https://github.com/CommanderPoe/tennis-prediction/blob/master/img_up%20(courtesy%20of%20unsplash)/reduced_table.png)

`series`

`court` 

`surface` 

`wrank` -> Rank of player 1

`lrank` -> Rank of player 2

`wpts` -> Ranking points of player 1

`lpts` -> Ranking points of player 2

`total_avg` -> Average games played by the 2 players in the past regardless the outcome. 

Keep in mind that to keep this table updated, you have to keep adding the total games played on that specific match you will predict + computing the `totg_avg`. Being bit familiar with the EDA and the code its highly recommended at this stage.

All this data can be easily collected before any match and inputted into the table easily.
<br />
<br />

### Conclusions and Key learnings...
**A word of warning**: Bookies are very tricky and have the brightest minds working for them; otherwise, they would not have stayed in business for this long. Why am I saying this?

Assume you check the odds for our target market (**OVER/UNDER 21.5**). One could think that it would always be available even if the bookies adjusted the odds regarding the levels of each player, but it's not always the case. They don't always offer OVER/UNDER 21.5 market because they move up and down the number of games depending on the players' statistics in question.

Example, these are real odd from matches happening this same week in Barcelona.

![1](https://github.com/CommanderPoe/tennis-prediction/blob/master/img_up%20(courtesy%20of%20unsplash)/odds_1.png)

![2](https://github.com/CommanderPoe/tennis-prediction/blob/master/img_up%20(courtesy%20of%20unsplash)/odds_2.png)

![3](https://github.com/CommanderPoe/tennis-prediction/blob/master/img_up%20(courtesy%20of%20unsplash)/odds_3.png)

![4](https://github.com/CommanderPoe/tennis-prediction/blob/master/img_up%20(courtesy%20of%20unsplash)/odds_4.png)



As you can see here, the number of games sometimes goes to 22.5, some others as low as 17.5 when there's a big gap in the players' skills. This could be easily solvable in our model by just changing the function of the target variable from 21.5 to the desired number. Then training the model again would be compulsory. 

We can say that the avg odd is always around 1.8 (Im telling this from empiric experience, not from a mathematical point of view) and the breakeven point at 55% so we still have some margin to play with that.
<br />
<br />

### Bonus
My partner and I ran some numbers, using odds from real matches this week (ten of them). We picked six randomly and gave it as won and four losses, so we keep our 60% precision or win rate our model predicted. The results were astonishing. After 100 matches, we had an excellent 10.10% YIELD, and the ROI was +100%.

![excel_record](https://github.com/CommanderPoe/tennis-prediction/blob/master/img_up%20(courtesy%20of%20unsplash)/record.png)


Understanding the impact of the statistics of your sports bets means including a projection on the long run, including a specific and strict bankroll, a standard bet size, and disciplined betting behavior. When you combine those tactics with an ability to shop for the best lines in the business, you've got a formula for consistently winning while placing wagers on the outcome of sporting events.