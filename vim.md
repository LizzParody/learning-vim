# Learning VIM
# Lesson 1

## Moving the cursor
```
     ^
     k              
<h        l>
     j
     v
```

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

## TEXT EDITING
### Deletion
1. x delete the character under the cursor.
2. Type dw to delete a word until the start of the next word (excluding its first character).
3. Type de to delete a current word (including the last character)
4. Type d$ to delete to the end of the line (including the last character).
5. d2w delete two words.
6. d4w delete four words.
7. dd to delete a whole line.
8. 2dd to delete two lines.

### Insertion
Press i to insert text.

### Appending (añadir)
Press A and it will go to the last character, and you can type any necessary additions.

### Editing a file
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

### Using a count for a motion
Typing a number before a motion repeats it that many times.

1. 2w move the cursor two words forward.
2. 3e move the cursor to the end of the third word forward.
3. 0 to move to the start of the line.
4. $ To move to the end of the line.

### Undo command
1. Press u to undo the last commands, U to fix a whole line.
2. To undo the undo's type  CTRL-R

# Lesson 3
### The put command
Type p to put previously deleted text after the cursor. (PASTE a deleted word or line)

### The replace command
Type r(x) to replace the character at the cursor with x. (Replace a character).

### The change operator
The change operator is used with the same motions as delete. <br>
1. To change until the end of a word, type ce. <br>
2. To change until the end of a line type c$.

# Lesson 4
### Cursor location and file status
1. CTRL-G to show your location in the file and the file stats (a message will appear at the bottom of the page with the filename and the position in the file).
2. Type G to move to the bottom of the file.
3. Type gg to move you to the start of the file.
4. Type [number of line] and G. this will return you to the line you want.

### The search command
1. Type / followed by a phrase to search for a phrase.
2. To search for the same phrase again press n.
3. To search for the same phrase in the opposite direction press N.

CTRL + O - to go back to where you came from.
CTRL + I - to go forward.

### Matching parentheses search
Type % to find a matching ), ] or }. </br>
This is very useful in debugging a program with unmatched parentheses!

### The substitute command
1. Type :s/old/new to substitute 'new' for the first old in a line type.
2. :s/old/new/g  To substitute new for all 'old's on a line type
3. :#,#s/old/new/g To substitute phrases between two line #'s type
4. :%s/old/new/g To substitute all occurrences in the file type
5. :%s/old/new/gc To ask for confirmation each time add 'c'.

# Lesson 5
### How to execute an external command
 Type :! followed by an external command to execute that command. (like :!ls to listing your directory) <br>
NOTE:  All  :  commands must be finished by hitting <ENTER>.

### More on writing files
1. To save changes made to the text, type :w FILENAME.
2. To delete the file type :!rm FILENAME.

### Selecting text to write
1. To save part of the file, type v motion :w FILENAME
2. v motion will highlight the text.
3. When you press : at the bottom will appear :'<,'>
4. Type w TEST (test is a filename that doesn't exist yet)
5. Vim will write the selected lines to the file TEST.

NOTE:  Pressing  v  starts Visual selection.  You can move the cursor around to make the selection bigger or smaller.  Then you can use an operator to do something with the text.  For example,  d  deletes the text.

### Retrieving and merging files
* You can retrieve TEST file using the commnad :r TEST (test is the filename) -> the file you retrieve is placed below the cursor line.

NOTE:  You can also read the output of an external command.  For example,
       :r !ls  reads the output of the ls command and puts it below the
       cursor.

# Lesson 6
### The open command
1. Type o (lowerCase) to open a line below the cursor and place you in Insert mode.
2. Type O (upperCase) to open a line above the cursor and place you in Insert mode.

### The append command
1. Type a to insert text after the cursor.
2. Move with e or w to where you want to append text, and then type a.

NOTE:  a, i and A all go to the same Insert mode, the only difference is where the characters are inserted.

### Another way to replace
* Type a capital  R  to replace more than one character.
NOTE:  Replace mode is like Insert mode, but every typed character deletes an existing character (until ESC is pressed).

### Copy and Paste operator
1. Use the y to copy and p to paste.
2. Move the cursor to the end of the next line:  j$
3. Type  p  to put (paste) the text. <br>
NOTE: you can also use  y  as an operator;  yw  copy one word.

### Set option
1. Set an option so a search or substitute ignores case.
2. press /AWord ->press n to look for it several times.
3. Set the ic (ignore case)   :set ic... search for /AWord.
4. :set hls is -> highlight all the searched words.
5. To disable ignoring case enter  :set noic
6. To remove the highlighting of matches enter:
:nohlsearch <br>
NOTE:  If you want to ignore case for just one search command, use  \c
             in the phrase:  /ignore\c  <ENTER>

* Typing ":set xxx" sets the option "xxx".  Some options are:
        'ic' 'ignorecase'       ignore upper/lower case when searching
        'is' 'incsearch'        show partial matches for a search phrase
        'hls' 'hlsearch'        highlight all matching phrases
     You can either use the long or the short option name.

# Lesson 7
### Getting Help
on-line help system
* Enter \<F1>
* :help <ENTER>
* :help cmd to find help on cmd

1. Type CTRL-W CTRL-W to jump from one window to another
2. Type :q <ENTER> to close help window


* Jump to a subject:  Position the cursor on a tag (e.g. |bars|) and hit CTRL-].

*  Jump back:  Type CTRL-T or CTRL-O (repeat to go further back).

### Create a startup script
Enable VIM features
* To use more features you have to create a "vimrc" file.
:e ~/.vimrc
Create a vimrc startup script to keep your preferred settings.

### Completion
Command line completion with CTRL-D and <TAB>
1. Make sure Vim is not in compatible mode:  :set nocp

When typing a  :  command, press CTRL-D to see possible completions. Press <TAB> to use one completion.

NOTE:  Completion works for many commands.  Just try pressing CTRL-D and <TAB>.  It is especially useful for  :help .

#EXAM OF COMMANDS
What does the following commands does?
Lesson 1
h
j
k
l
:q!
:wq
x
dw
de
d$
d2w
d4w
dd
2dd
i   
A

Lesson 2
w
e
$
2w
3e
0
$
u
U
CTRL-R

Lesson 3
p
r(x)
ce
c$

Lesson 4
ctrl-G
G
gg
[number of line] + G
/[word]
n
N
ctrl + O
ctrl + I
%
:s/old/new
:s/old/new/g
:#,#s/old/new/g
:%s/old/new/g
:%s/old/new/gc

Lesson 5
![external command]
!ls[ENTER]
:w FILENAME
:!rm FILENAME
v
v [highlight text]:w FILENAME
vd
:r FILENAME
:r !ls

Lesson 6
o
O
a
R
y
j$
yw
:set ic [word]
:set hls is
:set noic
:nohlsearch
/ignore\c
:set is
:set hls

Lesson 7
f1
:help
:help cmd
CTRL-W CTRL-W
:q
Position the cursor on a tag (e.g. |bars|) and hit CTRL-]
CTRL-T
CTRL-O
CTRL-D
