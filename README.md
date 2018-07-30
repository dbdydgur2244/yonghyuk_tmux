# tmux

## tmux-plugins

### Installation

```bash
$ git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

아래 내용을 `.tmux.conf`에 추가  

```bash
# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'

# Other examples:
# set -g @plugin 'github_username/plugin_name'
# set -g @plugin 'git@github.com/user/plugin'
# set -g @plugin 'git@bitbucket.com/user/plugin'

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm'
```

## tmuxinator

### Installation

```bash
$ gem install tmuxinator
```

### Completion

#### bash

```bash
$ source ~/.bin/tmuxinator.bash
```

#### zsh

```bash
$ source ~/.bin/tmuxinator.bash
```

##tmux prefix highlight

### Installation

아래 내용을`~/.tmux.conf`에 추가

```bash
set -g @plugin 'tmux-plugins/tmux-prefix-highlight'
```

  ### Configurations

```bash
set -g @prefix_highlight_fg 'white' # default is 'colour231'
set -g @prefix_highlight_bg 'blue'  # default is 'colour04'
```

```bash
set -g @prefix_highlight_prefix_prompt 'Wait'
set -g @prefix_highlight_copy_prompt 'Copy'
```

```bash
set -g @prefix_highlight_show_copy_mode 'on'
set -g @prefix_highlight_copy_mode_attr 'fg=black,bg=yellow,bold' # default is 'fg=default,bg=yellow'
```

```bash
set -g @prefix_highlight_output_prefix '< '
set -g @prefix_highlight_output_suffix ' >'
```



## tmux-powerline

### Installation

```bash
$ git clone https://github.com/erikw/tmux-powerline.git
```

아래 내용을`~/.tmux.conf`에 추가

```bash
set-option -g status on
set-option -g status-interval 2
set-option -g status-justify "centre"
set-option -g status-left-length 60
set-option -g status-right-length 90
set-option -g status-left "#(~/path/to/tmux-powerline/powerline.sh left)"
set-option -g status-right "#(~/path/to/tmux-powerline/powerline.sh right)"

# powerlineified window list 
set-window-option -g window-status-current-format "#[fg=colour235, bg=colour27]⮀#[fg=colour255, bg=colour27] #I ⮁ #W #[fg=colour27, bg=colour235]⮀"

bind C-[ run '~/path/to/tmux-powerline/mute_powerline.sh left'      # Mute left statusbar.
bind C-] run '~/path/to/tmux-powerline/mute_powerline.sh right'     # Mute right statusbar.
```

### 추가 설정

`themes/default.sh`에서 필요 없는 파라미터들 주석 처리할 수 있음.



## tmux-continuum

특징:

1. tmux environment 15분 간격으로 자동 저장
2. coputer/server가 켜질 때 자동으로 tmux 시작
3. 자동으로 tmux 시작될 때 restore

### Installation

`.tmux.conf`에 다음과 같은 내용 추가

```bash
set -g @plugin 'tmux-plugins/tmux-resurrect'
set -g @plugin 'tmux-plugins/tmux-continuum'
```

자동 시작을 활성화하려면 `.tmux.conf`에 다음과 같은 내용 추가하면 된다.

```bash
set -g @continuum-boot 'on'
```

