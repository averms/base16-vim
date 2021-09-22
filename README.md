# Base16 Vim Minimal

My fork of the Base16 Vim template. This fork has a number of
improvements:

- Faster because it uses the actual Vim commands rather than defined
  functions.
- Cleaner because it doesn't unnecessarily override highlight groups. It also
  doesn't set colors for highlight groups that don't exist. The upstream
  template does that with, for example, `Bold` and `Italic`.
- Includes a fix for a Neovim bug with CursorLine
  (https://github.com/neovim/neovim/issues/9019).
- Instead of having the generated themes in the `colors/` directory as upstream
  does, they are distributed using GitHub releases.

This fork does not support `base16-shell`. This is because I don't use it and I
don't think it is possible to add support for it in the way I wrote the
template. It also isn't necessary now that Vim has support for `termguicolors`.

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

## Future development

See TODO.md. If you have any improvements to suggest, feel free to open an
issue.
