`ZZ` `ZQ`: quit and save, quit without saving
`vib`, `viB`: select inside () or {}
`gv`: last visual select mode 
- to add to back of varying lines,`Ctrl+v$A` 
` to toggle upper and lowercasing
`g`w`: toggle casing for a word 
`g~it`: toggle for all in tag 
`gg=G`: reindent the whole file
`Ctrl+z`, `fg`: bring nvim to bg and fg
`:mksession sesssionname.vim`, `source sesssionname.vim` : to save a session 
`J` `gJ`: join multiple line with or without space between
`Ctrl + x` `Ctrl + a`: to decrement and increment 
`vip`: select inside paragraph
`Ctrl + j`: new line from insert mode
`Ctrl + w`: delete word from insert mode
`Ctrl + o`: run one command from insert mode
`:vim /wordIWantToChange **:` : plain Searchfor word in  * for dir, ** recursive
`copen` : where the changes have been made to 
`cdo s/wordIWantToChange/newWord/gc ` 


## Jumping
% : for Jumping between (), [], {}
gx, gf: for opening files and links '/home/feez/files/Pictures/screenshot-2025-08-05_09-34-21.png'
`ma` `'a` | `mA` `'A`: create and goto mark 
`:marks`
`''` : previous jump location 
`'.` : last edit jump location 
`'^` : last insert mode jump location 
`'[` ,`']` : jump to beginning and end of last multi line edit
`Ctrl + o` `Ctrl + i`: go forward and backwards in the jump list 

## Search 
`g*`: partial finding of word 
`:jumps` : jumps list 

## Copy
`:register`: opens the registers 

