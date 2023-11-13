cat hint1
Try poking around what's in a file by using the 'head' command:

  head -n 20 people
"""
NAME    GENDER  AGE     ADDRESS
Alicia Fuentes  F       48      Walton Street, line 433
Jo-Ting Losev   F       46      Hemenway Street, line 390
Elena Edmonds   F       58      Elmwood Avenue, line 123
Naydene Cabral  F       46      Winthrop Street, line 454
Dato Rosengren  M       22      Mystic Street, line 477
Fernanda Serrano        F       37      Redlands Road, line 392
Emiliano Wenk   M       90      Paulding Street, line 490
Larry Lapin     M       71      Atwill Road, line 298
Jakub Gondos    M       61      Mitchell Street, line 187
Derek Kazanin   M       55      Tennis Road, line 440
Jens Tuimalealiifano    M       83      Rockwood Street, line 205
Nikola Kadhi    M       75      Glenville Avenue, line 226
"""

This will show you the first 20 lines of the 'people' file.
admin@i-060a52b66c8a793eb:~/clmystery$ cat hint2
Try using grep to search for the clues in the crimescene file:

        grep "CLUE" crimescene
        
"""
CLUE: Footage from an ATM security camera is blurry but shows that the perpetrator is a tall male, at least 6'.
CLUE: Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for Rotary_Club, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason.
CLUE: Questioned the barista at the local coffee shop. He said a woman left right before they heard the shots. The name on her latte was Annabel, she had blond spiky hair and a New Zealand accent.
"""

admin@i-060a52b66c8a793eb:~/clmystery$ cat hint3
In order to track down our potential witness, we need to figure out where she lives.

Try using 'head' on some of the files like 'people' and 'vehicles' and see where we might find that.
admin@i-060a52b66c8a793eb:~/clmystery$ cat hint4
To find all the Annabels' addresses, use the 'people' file:

        grep "Annabel" people

Notice that not all of the results are worth investigating.  Remember what we know about Annabel.
admin@i-060a52b66c8a793eb:~/clmystery$ cat hint5
"Interview" the two possible witnesses by reading the correct line from the streets they live on:

        head -n 173 streets/Mattapan_Street | tail -n 1

This will give you just line 173 of Mattapan street, because it will take first 173 lines, and then take
the last line from those.
admin@i-060a52b66c8a793eb:~/clmystery$ cat hint5
"Interview" the two possible witnesses by reading the correct line from the streets they live on:

        head -n 173 streets/Mattapan_Street | tail -n 1

This will give you just line 173 of Mattapan street, because it will take first 173 lines, and then take
the last line from those.
admin@i-060a52b66c8a793eb:~/clmystery$ cat hint6
To find a matching license plate, or a matching car, you can use grep on the 'vehicles' file:

        grep "Honda" vehicles

        grep "Blue" vehicles

        grep "L337" vehicles

This doesn't give us anything useful - why not? Try using 'head' on the file to investigate its structure.
admin@i-060a52b66c8a793eb:~/clmystery$ cat hint7
In order to actually get information about vehicles that might match our description,
we need to get multiple lines AROUND each match.  We can use the -A, -B, or -C option with grep:

        grep -A 5 "L337" mystery/vehicles

This will match the license plates that contain "L337" and, for each match, show us the five lines AFTER it.
admin@i-060a52b66c8a793eb:~/clmystery$ cat hint8
To see who was a member of several different groups, you can combine their membership lists into one and search against that.

        cat Fitness_Galaxy AAA United_MileagePlus | grep "John Smith"

If you only want to see the number of matches, you can use grep's -c option (the c must be lowercase):

        cat Fitness_Galaxy AAA United_MileagePlus | grep -c "John Smith"

Or you can pipe the result to 'wc -l':

        cat Fitness_Galaxy AAA United_MileagePlus | grep "John Smith" | wc -l