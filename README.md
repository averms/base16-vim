# Base16 Vim Minimal

a-vrma's fork of the Base16 Vim template. This fork has a number of
improvements:

- Faster because it uses the actual builtin Vim commands rather than defined
  functions.
- Cleaner because it doesn't unnecessarily override highlight groups. The
  upstream template even sets colors for some highlight groups that don't
  exist.
- Includes a fix for a Neovim bug with CursorLine
  (https://github.com/neovim/neovim/issues/9019).
- Instead of having the generated themes in the `colors/` directory as upstream
  does, they are distributed using GitHub releases.

This fork does not support `base16-shell`. This is because I don't use it and I
don't know how to add support for it. If you would like to add it, patches are
welcome. For a user, this means you will have to change your terminal emulator
settings too if you want to use a Vim without `termguicolors`. Fortunately, the
entire point of the base16 project is to make this easy.

## Installation

Download the tar.xz file from the latest release and unpack it. Choose the
colorschemes you want and put them in `~/.vim/colors` or
`~/.config/nvim/colors`, depending on whether you are using Vim or Neovim.

## Customization

If you want to do some local customization, you can add something like this to
your `~/.vimrc`.

```vim
" The autocmd definition has to be before the colorscheme command.
augroup base16_additions
    autocmd ColorScheme base16-*
        \ hi clear MatchParen
        \ | hi clear SpellCap
        \ | hi Comment guifg=#B2B2B2 ctermfg=249 gui=italic cterm=italic
augroup END

colorscheme base16-classic-dark
```
