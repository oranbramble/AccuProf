# AccuProf

This project was undertaken to assess the profitbality of the UK football betting market using the Accumualtor betting method. Unfortunately, due to my Univrsity's regulations, I cannot publish the code here although I can explain the method and the findings briefly

## Method

Accumulator betting is the betting format on which you combine single-way bets into one large bet which pays off only if all the component bets also succeed. If one fails, the whole accumualtor fails. This was investigated due to the severe lack of research into this topic area, and so I thought it had potential to provide large profits.

There exists a plethora of exisitng stategies for single-way bets, so my idea was to combine different strategies for single-way bets into making an accumulator. For this, I selected 2 different strategies, which I labelled ST1 and ST2. For these strategies, you can visit the papers by [Lisandro Kauntiz et al.](https://arxiv.org/abs/1710.02824) and [Edward Wheatcroft](https://www.degruyter.com/document/doi/10.1515/jqas-2019-0009/html). So, I would use these strategies to select bets from a gameweek, and then further strategies (below) would compile certain bets from these selected bets into an accumulator. 

I developed 4 different strategies to form an accumulator from the bets selected by the strategies above. They were used with a range of different accumulator sizes to properly assess the profitability. The different strategies are encompassed in the grid below.

![image](https://github.com/oranbramble/AccuProf/assets/56357864/0128a84c-6639-45bb-8ab4-874ff4736043)

• **Confidence** - Uses confidence parameter to order bets by confidence
• **No Confidence** - Choose randomly without confidence parameter
• **Priority ST1** - Prioritise Strategy 1 bets
• **Priority ST2** - Prioritise Strategy 2 bets

These used a confidence parameter which I derived using a Neural Network, which was trained on previous match odds data and outputted a single float value representing confidence in the selected bet. Ie.e. if ST1 selected a bet, its data would be run through the ST1 confidence neural network and output a confidence value in the bet suggested. These confidence values were essential to then forming an accumulator from these bets. </br>

## Results


![betting without kelly](https://github.com/oranbramble/AccuProf/assets/56357864/22d20caa-0ae9-4986-b968-f44ed0dcbcce)


