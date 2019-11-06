# clean transcripts

use only characters in alphabet.txt. Remove other characters (@/à/è, etc) and accents (`~« etc).
remove empty lines or lines with only on character
replace numbers


# create csv 

head with wav_filename, wav_filesize, transcript
each column separated by , 
remove lines with negative wav_filesize

# shuffle file

sort --random-sort old.csv > newfile.csv

# create dev and test

```
#substitute %,« `´ â @
tail -n 4000 train.csv|head -n 2000 > dev.csv
tail -n 2000 train.csv > test.csv
#put headers in files
cp train.csv train.csv_1
head -n  train.csv_1 > train.csv
```

DON'T FORGET TO PUT THE HEADERS IN test and dev

# preprocess wav

check they have 16khz and not more (else too big for gpu memory (12 GB))



