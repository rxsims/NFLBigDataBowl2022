# NFLBigDataBowl2022
Full code used in the 2022 NFL Big Data Bowl


How to reproduce the results:

Part 1: This code is already present in the submitted notebook, working directly on the data.
1) Run BallLand_Full.ipynb - Finds x and y coordinates for the football at the frame where it lands.
2) Run FindBounceCatch.ipynb - Determine whether a particular punt is a bounce of is fielded/caught
3) Run FindSnap.ipynb - Finds which frame in the tracking data corresponds to the snap
4) Run PreSnap_Full.ipynb - Organizes all player positional data, football starting and landing coordinates, hang time, and bounce vs catch label for each punt.
At this point, four files are created: fb_land.csv, BounceCatch.csv, snapframe.csv, and BC_AllPlayers.csv
