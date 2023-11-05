# AccuProf

This project was undertaken to assess the profitbality of the UK football betting market using the Accumualtor betting method. Unfortunately, due to my Univrsity's regulations, I cannot publish the code here although I can explain the method and the findings briefly

## Method

Accumulator betting is the betting format on which you combine single-way bets into one large bet which pays off only if all the component bets also succeed. If one fails, the whole accumualtor fails. This was investigated due to the severe lack of research into this topic area, and so I thought it had potential to provide large profits.

There exists a plethora of exisitng stategies for single-way bets, so my idea was to combine different strategies for single-way bets into making an accumulator. For this, I selected 2 different strategies, which I labelled ST1 and ST2. For these strategies, you can visit the papers by [Lisandro Kauntiz et al.](https://arxiv.org/abs/1710.02824) and [Edward Wheatcroft](https://www.degruyter.com/document/doi/10.1515/jqas-2019-0009/html). So, I would use these strategies to select bets from a gameweek, and then further strategies (below) would compile certain bets from these selected bets into an accumulator. 

I developed 4 different strategies to form an accumulator from the bets selected by the strategies above. They were used with a range of different accumulator sizes to properly assess the profitability. The different strategies are encompassed in the grid below.

![image](https://github.com/oranbramble/AccuProf/assets/56357864/0128a84c-6639-45bb-8ab4-874ff4736043)

- **Confidence** : Uses confidence parameter to order bets by confidence
- **No Confidence** : Choose randomly without confidence parameter
- **Priority ST1** : Prioritise Strategy 1 bets
- **Priority ST2** : Prioritise Strategy 2 bets

These used a confidence parameter which I derived using a Neural Network, which was trained on previous match odds data and outputted a single float value representing confidence in the selected bet. Ie.e. if ST1 selected a bet, its data would be run through the ST1 confidence neural network and output a confidence value in the bet suggested. These confidence values were essential to then forming an accumulator from these bets. </br>

## Results

</br>

![betting without kelly](https://github.com/oranbramble/AccuProf/assets/56357864/22d20caa-0ae9-4986-b968-f44ed0dcbcce)

</br>

The above graph demonstrates how profitable this idea turned out to be (NOTE: this is all in a simulated environemnt, i.e. run on past game data. But, theres no reason it couldn't be implemented quite easily in real life!). Using just £10 stakes on each accumulator, we see betting on low size accumulators seems to provide optimal returns, althugh if you get lucky, a higher size accumulator can also be very profitable. For consistent profit however, accumulator sizes of 2 or 3 are recommended.

</br>

![betting with kelly](https://github.com/oranbramble/AccuProf/assets/56357864/75f28d2d-fb15-423a-a103-0a46cd5e8a28)

</br>

This graph shows the same but instead of £10 stakes per accumulator, I implemented a bankroll strategy known as the Kelly bankroll management strategy. For more info on this, see [here](https://www.thepunterspage.com/kelly-criterion-betting/). It uses the fact that odds set by bookies are a relatively accurate measure of probability of event occuring. Using this bankroll management strategy, less profits were realised, but the profit was much more consitent and all sizes of accumulator actually profitied. This shows that this method of accumulator betting could potentially provide profti with little to no risk of a loss.

## Conclusion

This project of mine is the one I am most proud of, mainky because it has the biggest implications in real-life. Although it is untested, the evidence is there to suggest accumulator betting, when done right, can be incredibly profitable and consistent. This goes against litrature which would suggest accumulator betting is risky and not as profitable as single-way betting, but my research suggests this may be untrue. Either way, it proves this area is criminially underesearced and definitely warrants further investigation.
