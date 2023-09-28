#Vim
## Local & Global Marks

- Local marks are with lowercase 
- Global marks are with uppercase

## Increase & Decrease Sequence of Numbers

If you have a set of numbers like 0,0,0,0 you can increase them as a sequence to achieve 1,2,3,4 using the shortcut `g <Ctrl>a` or `g <Ctrl>x`

## Find where a Keymap has been set

```vim-shell
:map <C-o>   # This shows infos for normal mode
:imap <C-o>  # This shows ifos for insert mode
:verbose map <C-o>  # This shows more infos
```
