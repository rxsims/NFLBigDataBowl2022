# NFLBigDataBowl2022
Full code used in the 2022 NFL Big Data Bowl


How to reproduce the results:

### Part 1: Training Data

1) Run BallLand_Full.ipynb - Finds x and y coordinates for the football at the frame where it lands.
2) Run FindBounceCatch.ipynb - Determine whether a particular punt is a bounce of is fielded/caught
3) Run FindSnap.ipynb - Finds which frame in the tracking data corresponds to the snap
4) Run PreSnap_Full.ipynb - Organizes all player positional data, football starting and landing coordinates, hang time, and bounce vs catch label for each punt.
5) Run ReturnLength.ipynb - Finds distance from punt landing x-coordinate to the x-coordinate of the ball at first contact.
6) Run BounceDirection.ipynb - Find the length of bounces and creates features for training MDN model.

Each of these notebooks will create a file: fb_land.csv, BounceCatch.csv, snapframe.csv, BC_AllPlayers.csv, FullTeamReturn.csv, BounceFeatures.csv.  The output of these notebooks has also been provided.  While the first 4 of these notebooks appear in the originally submitted file, the final 3 will produce the relevant training data for each of the models in question.

7) Run ExtraPunt_PreSnapData.ipynb - Provides player data in the same form as PreSnap_Full for the plays that were excluded from training.  Exclusion was done for various reason explained throughout the previous files.  This data will be completely untrained, but will still be useful for evaluating punters in the end. Outputs ExtraPuntLocations.csv file.


### Part 2: Training Model

Run all four files (TwoOutcome, ThreeOutcomeModel, ReturnLength, MDN_Bivariate).  These notebooks will save the different models to make predictions on potential landing locations in the next section.  They also save the small arrays containing the mean and standard deviation for each of the training features so the new data can be quickly implemented.

The h5 files associated with the TensorFlow model save files used in contrusting the original plots have also been uploaded, as well as the normalization statistic files.


### Part 3: Making Predictions

Run EvaluatePunter_Full.ipynb - For a given punter, evaluate the optimal landing location and field value for each of their punts in a given season.  This notebook is run for each punter meeting some minimum requirement for punts in a season (which was taken as 1 punter per game i.e. 16 games).  Ideally, the numeric integration would be done in parallel, but it was not implemented.

Run ActualPunts.ipynb - Evaluated the expected field value for the actual punt landing location.  Note, Integration Warnings may appear if the out-of-bound or direct-to-endzone plays are not removed before integrating.  These punts are easy to evaluate by the rules of the game, and do not need modeling to find their expected values.

The full set of all these ideal locations, as well as more predicted statistics, are given in an attached file.

Run ComparisontoOptimal.ipynb - Tabulates the results of the previous two notebooks into a single table, ranking each punter's performance relative to the optimal predicted values.

