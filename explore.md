## How big is the dataset?
cmd: wc -l clean_dialog.csv

Output: 36860 lines

## What’s the structure of the data? (i.e., what are the field and what are values in them)
To see the header: 

cmd: head -n 1 clean_dialog.csv

Output : "title","writer","dialog","pony"

To see the header and the first entry (to understand the structure):

cmd: head -n 2 clean_dialog.csv

Output:

"title","writer","dialog","pony"
"Friendship is Magic, part 1","Lauren Faust"," Once upon a time, in the magical land of Equestria, there were two regal sisters who ruled together and created harmony for all the land. To do this, the eldest used her unicorn powers to raise the sun at dawn; the younger brought out the moon to begin the night. Thus, the two sisters maintained balance for their kingdom and their subjects, all the different types of ponies. But as time went on, the younger sister became resentful. The ponies relished and played in the day her elder sister brought forth, but shunned and slept through her beautiful night. One fateful day, the younger unicorn refused to lower the moon to make way for the dawn. The elder sister tried to reason with her, but the bitterness in the young one's heart had transformed her into a wicked mare of darkness: Nightmare Moon.","Narrator"

## How many episodes does it cover?
cmd: awk -F, '{print $1}' clean_dialog.csv | tail -n +2 | sort | uniq | wc -l

Output: 196

## During the exploration phase, find at least one aspect of the dataset that is unexpected – meaning that it seems like it could create issues for later analysis.

The file encoding is not in UTF-8 which is the only encoding supported by the csv tool. This kept me from using the csvtool to explore the data.
