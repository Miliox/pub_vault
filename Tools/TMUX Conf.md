```bash
#!/bin/bash
# ~/.tmux.conf

# 8bit color
set -g default-terminal "screen-256color"

# Large scrollback buffer
set -g history-limit    65536

# UTF-8
set  -q -g status      on
set  -q -g status-utf8 on
setw -q -g utf8        on

# Rebind Prefix to Ctrl+A
unbind        C-b
set -g prefix C-a
bind          C-a send-prefix

# Faster key repetition
set -sg escape-time 0

# Easy reload
bind r source-file ~/.tmux.conf \; display "reloaded!"

# Paste
unbind p
bind   p paste-buffer

# Splits
bind _  split-window -vb # Top
bind \\ split-window -h  # Left
bind |  split-window -hb # Right
bind -  split-window -v  # Bottom
unbind '"'
unbind '%'

# Split Nav
bind -n C-t select-pane -U # Top
bind -n C-h select-pane -L # Left
bind -n C-s select-pane -R # Right
bind -n C-n select-pane -D # Bottom

# Mouse Behavior
set -g mouse on

# Mouse Scroll
bind -n  WheelUpPane   if-shell -F -t = "#{mouse_any_flag}" "send-keys -M" "if -Ft= '#{pane_in_mode}' 'send-keys -M' 'select-pane -t=; copy-mode -e; send-keys -M'"
bind -n WheelDownPane select-pane -t= \; send-keys -M
bind -n C-WheelUpPane   select-pane -t= \; copy-mode -e \; send-keys -M
bind -T copy-mode-vi    C-WheelUpPane   send-keys -X halfpage-up
bind -T copy-mode-vi    C-WheelDownPane send-keys -X halfpage-down
bind -T copy-mode-emacs C-WheelUpPane   send-keys -X halfpage-up
bind -T copy-mode-emacs C-WheelDownPane send-keys -X halfpage-down

# To copy, left click and drag to highlight text in yellow,
# once you release left click yellow text will disappear and will automatically be available in clibboard
# # Use vim keybindings in copy mode
setw -g mode-keys vi

# Update default binding of `Enter` to also use copy-pipe
unbind -T copy-mode-vi Enter

# Linux
bind -T copy-mode-vi Enter send-keys -X copy-pipe-and-cancel "xclip -selection c"
bind -T copy-mode-vi MouseDragEnd1Pane send-keys -X copy-pipe-and-cancel "xclip -in -selection clipboard"

# Mac OSX
# bind -T copy-mode-vi Enter             send-keys -X copy-pipe-and-cancel "pbcopy"
# bind -T copy-mode-vi MouseDragEnd1Pane send-keys -X copy-pipe-and-cancel "pbcopy"
```