# one-hit-wonder-project
my attempt to discover when the most one hit wonders came out

I started with this dataset: 

/kaggle/input/billboard-the-hot-100-songs/charts.csv

which I uploaded to BigQuery.

This dataset includes every weekly Hot 100 chart since Billboard began tracking in 1958. The information I needed to extract was how many songs each artist charted with. This dataset does not have a primary key because every week, song, and artist appears many times - most songs chart for more than 1 week. 

So I wrote a nested query to extract the first time each song charted, and then each artist that appeared on that list only once. 

Next, I exported the resulting table to Sheets. I then filtered as many collaborations as I could using filters for the keywords FEATURING, WITH, AND, X, +, and /. This eliminated most of the collaborations. Collab songs usually feature at least one artist that has several hits, but they may have only recorded one song with their collaborator. Mariah Carey and Jay Z are not one hit wonders but they only have one hit together. 

I also needed all the dates these artists charted, but adding that criteria to my query would return duplicates. So I exported a second table with the names, dates, and songs of all the artists that got above 50 on the charts to use as a range for VLOOKUP. 

Now I had a single sheet with ONLY the one-time-only charting artists, the first date they charted, and their song title. On to visualization! 
