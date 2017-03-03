# Learning VIM
# Lesson 1

## Moving the cursor
     ^
     k              
<h        l>
     j
     v

Hint:
* The h key is at the left and moves *left*.
* The l is at the right and moves *right*.
* The j looks like a down arrow.

NOTE: If you are ever unsure about something you typed, press <ESC> to place you in Normal mode.  Then retype the command you wanted.


## Exiting VIM
1. Press the <ESC> key (to make sure you are in Normal mode).
2. Type:      :q! <ENTER>.
     This exits the editor, DISCARDING any changes you have made.
3. To exit and save changes:
:wq <ENTER>

## Text editing
### DELETION
1. x delete the character under the cursor.
---
2. Type dw to delete a word until the start of the next word (excluding its first character).
3. Type de to delete a current word (including the last character)
4. Type d$ to delete to the end of the line (including the last character).
5. d2w delete two words.
6. d4w delete four words.
7. dd to delete a whole line.
8. 2dd to delete two lines.

### INSERTION
1. Press i to insert text.

### APPENDING (añadir)
1. Press A and it will go to the last character, and you can type any necessary additions.

### EDITING A FILE
1. To go to Vim Editor, type vim tutor (vim is the command to start the editor and tutor is the name of the file).
2. Insert and delete text as you learned.
3. Save the file with
:wq <ENTER>

# Lesson 2

NOTE: many commands are made from an operator and a motion.
d is the Operator
w is the motion.
### Motions
Pressing the motions without the d, will the cursor as specified.
w, e, $.

## Using a count for a motion
Typing a number before a motion repeats it that many times.
1. 2w move the cursor two words forward.
2. 3e move the cursor to the end of the third word forward.
3. 0 to move to the start of the line.
4. $ To move to the end of the line.

## Undo command
1. Press u to undo the last commands, U to fix a whole line.
2. To undo the undo's type  CTRL-R

# Lesson 3
## The put command
1. Type p to put previously deleted text after the cursor. (PASTE a deleted word or line)

## The replace command
1. Type r(x) to replace the character at the cursor with x. (Replace a character).

## The change operator
The change operator is used with the same motions as delete.
1. To change until the end of a word, type ce.
2. To change until the end of a line type c$.j

# Lesson 4
## Cursor location and file status
1. CTRL-G to show your location in the file and the file stats (a message will appear at the bottom of the page with the filename and the position in the file).
2. Type G to move to the bottom of the file.
3. Type gg to move you to the start of the file.
4. Type [number of line] and G. this will return you to the line you want.

## The search command
1. Type / followed by a phrase to search for a phrase.
2. To search for the same phrase again press n.
3. To search for the same phrase in the opposite direction press N.

CTRL + O - to go back to where you came from.
CTRL + I - to go forward.

## Matching parentheses search
1. Type % to find a matching ), ] or }.
This is very useful in debugging a program with unmatched parentheses!

## The substitute command
1. Type :s/old/new to substitute 'new' for the first old in a line type.
2. :s/old/new/g  To substitute new for all 'old's on a line type
3. :#,#s/old/new/g To substitute phrases between two line #'s type
4. :%s/old/new/g To substitute all occurrences in the file type
5. :%s/old/new/gc To ask for confirmation each time add 'c'.

# Lesson 5
## How to execute an external command
1. Type :! followed by an external command to execute that command. (like :!ls to listing your directory)
NOTE:  All  :  commands must be finished by hitting <ENTER>.

## More on writing files
1. To save changes made to the text, type :w FILENAME.
2. To delete the file type :!del FILENAME.
