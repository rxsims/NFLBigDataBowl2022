# NFLBigDataBowl2022
Full code used in the 2022 NFL Big Data Bowl


How to reproduce the results:

Part 1:
1) Run BallLand_Full.ipynb - Finds x and y coordinates for the football at the frame where it lands.
2) Run FindBounceCatch.ipynb - Determine whether a particular punt is a bounce of is fielded/caught
3) Run FindSnap.ipynb - Finds which frame in the tracking data corresponds to the snap
4) Run PreSnap_Full.ipynb - Organizes all player positional data, football starting and landing coordinates, hang time, and bounce vs catch label for each punt.
5) Run ReturnLength.ipynb - Finds distance from punt landing x-coordinate to the x-coordinate of the ball at first contact.
6) Run BounceDirection.ipynb - Find the length of bounces and creates features for training MDN model.

Each of these notebooks will create a file: fb_land.csv, BounceCatch.csv, snapframe.csv, BC_AllPlayers.csv, FullTeamReturn.csv, BounceFeatures.csv.

While the first 4 of these notebooks appear in the originally submitted file, the final 3 will produce the relevant training data for each of the models in question.


Part 2:
