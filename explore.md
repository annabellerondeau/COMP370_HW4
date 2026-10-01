## How big is the dataset?
cmd: wc -l clean_dialog.csv

Output: 36860 lines

## What’s the structure of the data? (i.e., what are the field and what are values in them)
cmd: head -n 1 clean_dialog.csv

Output : "title","writer","dialog","pony"

## How many episodes does it cover?
cmd: awk -F, '{print $1}' clean_dialog.csv | tail -n +2 | sort | uniq | wc -l

Output: 196

## During the exploration phase, find at least one aspect of the dataset that is unexpected – meaning that it seems like it could create issues for later analysis.

The file encoding is not in UTF-8 which is the only encoding supported by the csv tool. This kept me from using the csvtool to explore the data.
