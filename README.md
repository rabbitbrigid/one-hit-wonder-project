# one-hit-wonder-project
my attempt to discover when the most one hit wonders came out

I started with this dataset: 

/kaggle/input/billboard-the-hot-100-songs/charts.csv

which I uploaded to BigQuery.

This dataset includes every weekly Hot 100 chart since Billboard began tracking in 1958. The information I needed to extract was how many songs each artist charted with. This dataset does not have a primary key because every week, song, and artist appears many times - most songs chart for more than 1 week. 

So I wrote a nested query to extract the first time each song charted, and then each artist that appeared on that list only once. 

Next, I exported the resulting table to Sheets. 
