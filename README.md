# Football_data_study

The aim of this case study is to evaluate and analyse a model of expected assist obtained by a logistic regression model taking into exam Seriea A season 2021/2022 in order to understand in which corner kick situation there is an offensive advantage.
The corner kick situations are:
  - Group A: right corner kick, right foot kicker (out-swinger effect kick corner)
  - Group B: right corner kick, left foot kicker (in-swinger effect kick corner)
  - Group C: left corner kick, left foot kicker (out-swinger effect kick corner)
  - Group D: left corner kick, right foot kicker (in-swinger effect kick corner)

The datasets used are:
  - positional data from corner kicks by Sics.sport
  - foot player data by Transfermarkt
  - player identification numbers data by Sics.sport, Soccerment and Skillcorner

The study case is divided in:
  - PHASE 1: data selection
  - PHASE 2: data classification
  - PHASE 3: model implementation

The model is based on hypotheis that the expected assist is a shot-centric metric, means that assist kick depends exclusively on the fact that the striker actually receives the pass. So the expected assist model is comparable to an expected goal model.

The results of the case study are so listed:
  - logistic regression model for expected assists trained on the available data is quantitatively quite reliable
  - need to improve the model by training it on larger datasets from previous seasons and/or from other championships
  - in-swinger corner kicks bring a greater offensive adantage in terms of assists compared to out-swinger corner kicks
