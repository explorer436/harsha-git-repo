vim delete up until a word

Put your cursor at the point you want to start at.

Make sure you're in command mode.

hit v to start a visual selection
then hit / and type the word you're looking for to select up to it, then press enter to make the selection
then hit d to delete the text 

---------------------------------------------------------------------------
To delete a word along with the whitespace after the word - dw (vw to select in visual mode)
To delete a word but not the the whitespace after the word - de (ve to select in visual mode)

---------------------------------------------------------------------------
To remove unnecessary spaces and tabs in empty lines in Vim-
In a search, \s finds whitespace (a space or a tab), and \+ finds one or more occurrences.
The following command deletes any trailing whitespace at the end of each line. If no trailing whitespace is found no change occurs, and the e flag means no error is displayed.
:%s/\s\+$//e
(this did not work with eclipse vim plugin)

---------------------------------------------------------------------------
Delete all text before search pattern : 
If you have a file that looks like below
1: #sometext
2: #sometext
3: #sometext
If you want to delete the text before the pattern ":" (colon). I have used the following command to replace every :%s/^.*/\://
If want to delete the texts after the pattern ":" (colon). I have used the following command to replace every :%s/\:.*$//
I would like to learn other ways to do.

Another answer : 
Do you want to not include the colon?
If so, then for deleting everything before (but not including) the colon :%s/.*\ze://
And for everything after :%s/:\zs.*//
See :help \zs and :help \ze for more info.

These atoms are amazing! After I discovered them, I started using them all the time. I remember them as z == zero-width (since they don't match anything).

If you want to delete all characters before "Hello", you can do
:%s/.*Hello/Hello/
Note that .* is greedy, i.e. it will eat all occurrences of "Hello" till it finds the last one. If you have a line:
abcHellodefHelloghi - it will become - Helloghi
If you want a non-greedy solution, try - :%s/.\{-}Hello/Hello

---------------------------------------------------------------------------
Removing duplicate rows in vi :sort u

---------------------------------------------------------------------------
How to “delete all blank(empty) lines” 
To delete blank lines in vim (empty lines), use this command - :g/^$/d

The g character says, “perform the following operation globally in this file.” (Operate on all lines in this file.)
The forward slash characters enclose the pattern I’m trying to match. In this case I want to match blank lines, so I use the regular expression ^$. Here the ^ means “beginning of line,” and $ means “end of line,” so with no characters in between them, this vim regex means “blank line.” (If I had typed ^abc$, that would mean, “find a line with only the sequence of characters ‘abc’”.)
The d at the end of the command says, “When you find this pattern, delete the line.”

In a similar way, to delete Lines Beginning With A certain text In Vim :g/^(enter text here)/d

---------------------------------------------------------------------------
delete line containing certain text in vim with prompt :%s/.*text.*\n//gc
The substitute command works by 
1. adding a wildcard
2. and adding an end-of-line.

---------------------------------------------------------------------------