# NVIM

### Install nvim
Official installation instructions: [nvim](https://github.com/neovim/neovim/wiki/Installing-Neovim#linux)

* Install nvim.
```shell
curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim.appimage
chmod u+x nvim.appimage
./nvim.appimage
```

### add alias
```shell
sudo nano ~/.bashrc
alias nvim=/home/ubuntu/nvim.appimage
```

## Management

### Copy and Paste
1) Press `Esc`
2) Press `yy`
3) Press `p`

### Move Right Up Down Left
1) `h` Right
2) `j` Up
3) `k` Down
4) `l` Left

### Turn on VISUAL Mode
1) press `v2` for visual mode
2) press `shift + v2` for visual line mode
3) press `cntr + alt + v2` for visual block mode

You can press `o` to opposite current selection

### Add text before words
1) Go to visual block mode
2) Press `shift + i`
3) Type the word
4) Press `Esc`

### Add text after words
1) Go to visual block mode
2) Press `$`, `shift + a`
3) Type the word
4) Press `Esc`

### Turn on command mode
Type `:`

`w file.txt` - Save file
`q` - Quit
`qw` - Quit and write the file
`q!` - If you change file you can quit and ignore changes
`e file.txt` - Open the file or create a new file with such name
`enew` - Create empty environment

Buffer.
1) Open files by typing `e`
2) Execute command `ls` - you see all files

`b 1` - open file with `1`
`b file2.txt` - open file
`cntr + 6` - switch between buffers files
`sp` - split files horizontal
`vs` - split files vertical
`cntr + w + hjkl` - run between windows
`tabnew` - open new terminal
`tabp` - open previous terminal
`wqa` - write and quit all
`wa` - write all
`qa` - quit all

### Motions, Commands, Text Objects
`set number` - numeric lines2
`shift + g` - jump to the last line
`g + g` - jump to the first line
`numeric number of code + g` - jump to the numeric code
`w` - move forward to the beginning of word
`b` - move back to the beginning of word
`shift + w` - move forward to the beginning of word only by spaces
`e` or `shift + b` - move back to the beginning of word only by spaces
press `0` - to come back to the beginning of editor
`^` - to come back to the beginning of editor except spaces
`$` - to come back to the end of editor
`u` - undo
`cntr + r` - redo
`f + letter` - go to the word starts from `letter`
`t + letter` - go to before where the word starts from `letter`
`;` - go to the next letter
`,` - go to the previous letter
`/ + word` - search `word`
`n` - go to next word
`shift + n` - go to previous word
`noh` - clear
`*` - search the word
`%` - toggle between pairs
`i` - insert mode
`a` - insert mode after
`shift + o` - insert mode above line
`o` - insert mode below line
`shift + i` - insert to the beginning of line 
`shift + a` - insert to the end of line 
`x` - delete symbol 
`d + w` - delete word 
`.` - repeat 
`d + shift + w` - delete with coma or specifies symbols
`d + ^` - delete all until the beginning
`d + $` or `shift + d` - delete all until the ending
`d + t + ,` - delete all until the coma
`d + d` - delete full line
`4 + d + d` - delete for lines
`c + w` - delete word and go to insert mode
`c + t + ,` - change until the come
`c + c` - change entire line
`shift + c` - change until at the end of line
`yw` - copy word with space
`yy` - copy the whole line
`p` - paste
`shift + p` - paste above the current line
`5 + p` - paste 5 times

### Text Object
`i + w` - select whole word with space in visual mode
`a + w` - select whole word without space in visual mode
`d + a + w` - delete around word
`d + i + w` - delete inside word
`i + parentheses` - select all until this parentheses in visual mode
`a + parentheses` - select all until these parentheses around in visual mode
`Tutor` - It is tutorial to help you all functionality in neovim, type in command mode

### Practical examples
Select all the text of file
1) `g + g`
2) `shift + v`
3) `shift + g`


### Tmux
`cntr + b` - all tmux commands start with (Remember if you create .tmux.conf, you can rewrite to `cntr + spae2`)
+ `c` - Create new window
+ `0` or `1` - Switch between windows
+ `n` or `p` - Switch to the next or previous window
+ `n` or `p` - Switch to the next or previous window
+ `shift + 5` - Split windows
+ `arrow right` or `arrow left` - switch between splits windows
+ `x` - close Split terminal
+ `:` - to get access of all commands
+ `new-session -s laracast` - create new session with name laracast
+ `s` - switch between sessions
+ `d` - detach session

`cntr + d` - delete tmux window
`tmux kill-server` - kill tmux server
