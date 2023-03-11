# VIM

### Change .vimrc configuration
+ `: + so %` - you need type to update configuration of vim

### Visual mode
+ `shift + v` - visual line mode
+ `shift + v` and get some line numbers, then `:sort` - will sort lines

### Commands
+ `d + d` - delete
+ `: + tabedit + file.txt` - edit file in new tab
+ `: + bd` - delete current tab

+ `y` - copy line
+ `p` - paste line
+ `.` - repeat last command 
+ `yiw` - copy the word

+ `/` - search in file

+ `vs` - vertical split 
+ `sp` - horizontal split 
+ `cntr + w + hjkl` - move between split windows
+ `cntr + hjkl` - move between split windows if you change .vimrc file
+ `cntr + w + w` - move between split windows
+ `!ls` - list all files in work directory
+ `zz` - point window to cursor

+ `bp` - previous buffer
+ `ls` - list of buffers
+ `b3` - go to the third buffer
+ `bd` - delete current buffer
+ `gt` - switch beetween buffers

+ `e .` - files in current directory
+ `^` - switch between files

+ `di(` remove, for example `array $arr` parameter in method
+ `di'` remove inside ', for example in 'some here th', will be ''
+ `ci'` change inside '
+ `vi'` select inside '
+ `vi(` select inside (
+ `va{` will select inside { with itself
+ `vat` will select inside of current cursor

### Install plugin
1) `vim .vimrc`
2) Paste `Plugin 'tpope/vim-vinegar'`
3) Run `: + PluginInstall`


### Shortcut
`, + e + v` - edit .vimrc file
`space + ,` - clean search (nohsearch)
vertical tabc` - close buffer in terminal`

### Commands after install plugin Vundle
`-` - open current directory
`d` - create directory
`D` - delete directory
`%` - create new file

`cntr + p` - find file
`cntr + t` - Open tree in directory

### Ctag to fast search
`ctag -R` - add tags file for quick search
`:tag register` - find register method in whole project
or `,f` - same `:tag register`
`:tn` - go to the next tag
`tp` - go to previous tag
`ts` - list of what find
`!ctag -R` - rewrite tags file when do changes
`cntr + ]` - go into method of class
`ctag -R --exclude=node_modules|vendor` - exclude vendor and node_modules folders

`:Ag ` - search every work in ' or "
`Gsearch` - search in files
In Gsearch you can edit words, so choose all via visual block and type: `s/word/update_word` - you replace word on update_word
After replace run command `:Greplace` and then choose a to rewrite every word
After run `:wa` - to save all changed files

### Snippets
`,es` - edit your snippets

### Surround plugin
`cs'"` - will change ' on "
`ds'` - will delete '
`dst` - will delete, for example <div> and </div> tags
`cst` - will replce your tag on another tag
you can select in wrap it to tag by `S`

### Php plugins
`,n` - add namespace automate import
`,nf` - add namespace inline
`,pcd` - fix style by php-cs-fixer
`,pf` - fix file
