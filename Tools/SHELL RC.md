```bash
function change_directory_interactive()
{
	cd "$(fd --type directory | fzf --height=50%)"
}

# https://ostechnix.com/a-bash-function-to-extract-file-archives-of-various-types/
function extract () {
    if [ -f $1 ] ; then
        case $1 in
             *.tar.bz2)   tar xvjf   $1;;
             *.tar.gz)    tar xvzf   $1;;
             *.bz2)       bunzip2    $1;;
             *.rar)       rar x      $1;;
             *.gz)        gunzip     $1;;
             *.tar)       tar xvf    $1;;
             *.tbz2)      tar xvjf   $1;;
             *.tgz)       tar xvzf   $1;;
             *.zip)       unzip      $1;;
             *.Z)         uncompress $1;;
             *.7z)        7z x       $1;;
             *)           echo "'$1' cannot be extracted via extract()" ;;
        esac
    else
        echo "'$1' is not a valid file"
    fi
}

# env
export HISTSIZE=
export HISTFILESIZE=
export PAGER='most -s +u'
export PROMPT_DIRTRIM='3'

# https://bashrcgenerator.com/
# 02:23:52 0 (main) /usr/local/src $
export PS1="\[\033[38;5;6m\]\t\[$(tput sgr0)\] \[$(tput sgr0)\]\[\033[38;5;7m\]\$?\[$(tput sgr0)\] \[$(tput sgr0)\]\[\033[38;5;1m\]\$(git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/')\[$(tput sgr0)\] \[$(tput sgr0)\]\[\033[38;5;2m\]\w\[$(tput sgr0)\] \[$(tput sgr0)\]\[$(tput bold)\]\[\033[38;5;3m\]\\$\[$(tput sgr0)\] \[$(tput sgr0)\]"

# conveniences
alias ..='cd ..'
alias _='sudo'
alias apt='sudo apt'
alias fd='fdfind'
alias now='date +"%T"'
alias open='xdg-open'
alias path='echo -e ${PATH//:/\\n}'
alias pbcopy='xclip -sel clip'
alias pbpaste='xclip -sel clip -o'

# better built ins
alias cat='pygmentize -g -O full,linenos=1,style=monokai'
alias cdi='change_directory_interactive'
alias cp='rsync  --progress --verbose --human-readable'
alias cpr='rsync --progress --verbose --human-readable --stats --recursive'
alias mv='rsync  --progress --verbose --human-readable --remove-source-files'
alias du='du -lh'
alias df='df -lh'
alias mkdir='mkdir -pv'
alias ps='procs --tree'
alias top='htop --tree --sort-key=PERCENT_CPU'

alias hd='most -b'
alias hexdump='hd'

alias ls='ls --almost-all --classify --color=auto --group-directories-first --ignore-backups --human-readable'
alias ll='ls -l'

# greppers
alias rgbz='rg --type=bazel'
alias rgcc='rg --type=cpp'
alias rgjj='rg --type=jinja'
alias rgjs='rg --type=json'
alias rgjv='rg --type=java'
alias rgpy='rg --type=py'
alias rgrs='rg --type=rust'
alias rgsh='rg --type=sh'

alias grep='rg'
alias cgrep='rgcc'
alias jgrep='rgjv'
alias jsgrep='rgjs'
alias jjgrep='rgjj'

# single letter commands
alias .='pwd'
alias ,='clear'
alias a='cat'
alias b='popd'
alias c='rgcc'
alias d='pushd'
alias e='nvim'
alias f='fd'
alias g='git'
alias h='rg'
alias i='ll'
alias j=''
alias k="ncal -w -y $(date +'%Y')"
alias l='git l'
alias m='man'
alias n=''
alias o='open'
alias p='git add -p'
alias q='howdoi'
alias r='!'
alias s='git st'
alias t='todo.sh'
alias u='git add -u'
alias v='code'
alias w='htop'
alias x='extract'
alias z=''

# bookmark shortcut
alias 1='open https://'
alias 2='open https://'
alias 3='open https://'
alias 4='open https://'
alias 5='open https://'
```