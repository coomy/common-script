## ~/.zshrc
plugins=(git autojump cp zsh-autosuggestions)

## ~/.oh-my-zsh/lib/git.zsh
~~ STATUS=$(command git status ${FLAGS} 2> /dev/null | tail -n1) ~~
删除上面这行，避免每次执行操作后都要 git status，对于大工程速度会很慢

## ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh
~~ ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE='fg=8' ~~
ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE='fg=238'

bindkey '^\\' autosuggest-execute

