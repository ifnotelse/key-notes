 editor commands

L Move to the bottom of the screen
H Move to the top of the screen
$ Move to the last column (character) on the current line
0 Move to the first column (character) on the current line


undo == u 
redo == control +r



Copying, Deleting, and Pasting


yw Copy word. This actually copies from the current character in a word until the end of the word (including punctuation) and the white space after the word. So, if your cursor was on the h in “this is fun,” the cw command would copy “his ” into memory.

yy Copy current line.

y$ Copy from current character to end of the line.

yG Copy current line to the end of the document.



dw Delete word; this command actually deletes from the current character in the word until the end of the word (including punctuation) and the white space after the word. So, if your cursor was on the h in “this is fun” the dw command would delete “his ”, resulting in “tis fun.”

 dd Delete current line.

 d$ Delete from current character to end of the line.

 dG Delete current line to the end of the document.12

 x �Delete the character the cursor is currently on (like a delete key).13

 X  Delete the character before the character the cursor is currently on (like a backspace key).


 p Pastes the buffer contents before the cursor

 P Pastes the buffer contents after the cursor
