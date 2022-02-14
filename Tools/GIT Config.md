```ini
[user]
    name  = Emiliano Firmino
    email = <email>

[core]
    whitespace = trailing-space,space-before-tab
    editor     = nvim -f

[alias]
    ap = add --patch
    au = add --update
    bl = blame
    br = branch
    cb = checkout -b
    ci = commit --signoff
    co = checkout
    di = diff
    dw = diff --word-diff
    mg = merge --no-ff
    re = rebase
    rf = reflog
    ru = rebase --interactive
    st = status --branch --short

    review       = push origin HEAD:refs/for/master
    review-wip   = push origin HEAD:refs/for/master%wip
    review-ready = push origin HEAD:refs/for/master%ready

    # Log & Diffs
    k        = !gitk
    l        = log --oneline --decorate --graph
    la       = log --oneline --decorate --graph --all
    diffstat = diff --stat -r
    changes  = diff --name-status -r
    timeline = log --graph --branches --pretty=oneline --decorate

    # More Info
    who    = shortlog --summary --
    whatis = show  --summary --date=short --pretty='tformat:%h (%s, %ad)'
    whois  = "!sh -c \
        'git log -i -1 --pretty=\"format:%an <%ae>\n\" \
        --author=\"$1\"' -"

    undo  = reset --hard
    fixup = commit --amend -C HEAD
    fix   = commit --amend -C HEAD

    prune-all = !git remote | xargs -n 1 git remote prune
    prune-preview = remote prune --no-dry

    ignored-files   = ls-files --exclude-standard --ignored --others
    modified-files  = ls-files --modified
    untracked-files = ls-files --exclude-standard --others

    list-cmds = config --get-regexp alias

[apply]
    whitespace = fix

[color]
    status = auto
    diff = auto
    branch = auto
    interactive = auto
    ui = true

[diff "word"]
    textconv = strings

[diff "excel"]
    textconv = strings

[diff "zip"]
    textconv = unzip -c -a
```
