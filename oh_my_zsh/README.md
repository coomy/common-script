## ~/.zshrc
```
plugins=(git autojump cp zsh-autosuggestions)
```

## ~/.oh-my-zsh/lib/git.zsh
```
~~STATUS=$(command git status ${FLAGS} 2> /dev/null | tail -n1)~~
```
删除上面这行，避免每次执行操作后都要 git status，对于大工程速度会很慢

## ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh
自动补全的文本颜色默认会和当前输入的文字颜色一样，很难辨识。一般会把提示补全的文字改浅一点，可以找到如下代码，并替换：

~~ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE='fg=8'~~
```
ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE='fg=238'
bindkey '^\\' autosuggest-execute // 这个是快捷键绑定，一键补全并执行
```

## 如果上述颜色fg设置不生效，说明系统颜色系统是8，需要改成256color
- 在 .zshrc 中添加 export TERM="xterm-256color"

或者
- 添加 zsh-256color 到 plugins
- cd $ZSH_CUSTOM/plugins && git clone https://github.com/chrissicool/zsh-256color

