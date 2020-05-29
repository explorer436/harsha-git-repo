https://vim.fandom.com/wiki/Using_marks

| Command  | Description  |
|---|---|
|ma |	set mark a at current cursor location|
|'a |	jump to line of mark a (first non-blank character in line)|
|`a |	jump to position (line and column) of mark a|
|d'a |	delete from current line to line of mark a|
|d`a |	delete from current cursor position to position of mark a|
|c'a |	change text from current line to line of mark a|
|y`a |	yank text to unnamed buffer from cursor to position of mark a|
|:marks |	list all the current marks|
|:marks aB |	list marks a, B|