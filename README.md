words
=====

Words With Friends And Scrabble

The Words With Friends app typically exists here: ~/Music/iTunes/iTunes\ Music/Mobile\ Applications

Copy the Words.ipa file to a temporary directory. Very likely it will have a version number after Words.
The .ipa file is a zip file archive. So you can do this:
> unzip Words.ipa

This will create a few files and a directory called Payload which has the app.
> cd Payload/WordsWithFriendsPaid.app

Here you will find a text file called 'enable1.txt'. This is the dictionary that is used by the app.
Copy this file to a safe place and you can delete all the rest.

With this dictionary/text file, it is easy to generate stats and word lists of interest.

### Number of total acceptable words
> wc -l enable1.txt

> 173098

### Number of 2 letter words
> perl -lne 'print if length $_ == 2' enable1.txt | wc -l

> 105

### Number of 3 letter words
> perl -lne 'print if length $_ == 3' enable1.txt | wc -l

> 992

### Collect the 2 letter words in a file called 2.txt to learn later
> perl -lne 'print if length $_ == 2' enable1.txt > 2.txt

### List all the words that have a 'q' to a file called q.txt
> perl -lne 'print if /q/' enable1.txt > q.txt

### List all the words with 'z' and less than 5 characters long into z.txt
> perl -lne 'print if length $_ < 5 and $_ =~ /z/' enable1.txt > z.txt

### List all the words that start with letter 'j' into j.txt
> perl -lne 'print if /^j/' enable1.txt > j.txt


