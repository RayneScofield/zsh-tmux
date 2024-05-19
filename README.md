# zsh-tmux
ZSH shell and tmux configuration
## Default Z shell
```
sudo apt install zsh
chsh -s $(which zsh)
```
## [ZSH plugin manager "zinit"](https://github.com/zdharma-continuum/zinit)
```
bash -c "$(curl --fail --show-error --silent --location https://raw.githubusercontent.com/zdharma-continuum/zinit/HEAD/scripts/install.sh)"
zinit self-update
```
### ZSH completions
[take github cli for example](https://cli.github.com/manual/gh_completion):  

Generate a _gh completion script and put it somewhere in your $fpath:  

```
gh completion -s zsh > ~/.local/share/zinit/completions/_gh
```
Ensure that the following is present in your ~/.zshrc:
```
autoload -U compinit
compinit -i
```
Zsh version 5.7 or later is recommended.
## [Powerlevel10K theme](https://github.com/romkatv/powerlevel10k)
Add ```zinit ice depth=1; zinit light romkatv/powerlevel10k``` to ~/.zshrc.
## Tmux common commands
```
# sessions
tmux new -s session-name
tmux attach
tmux attach -t session-name
tmux detach    #  prefix d
prefix s       #  show all sessions
prefix $       #  rename session
prefix Ctrl-s  # save sessions
prefix Ctrl-r  # restore sessions

# windows
prefix c       # create window
prefix ,       # rename window
prefix &       # kill window
prefix n       # focus to next window
prefix p       # focus to previous window
prefix w       # show all window
prefix number  # go to window number

# panes
prefix \       # split window vertically
prefix -       # split window horizontally
prefix q       # show all panes
prefix !       # turn pane to window
prefix z or m  # maximize pane
prefix x       # kill pane
prefix { or }  # swap panes
```
## Tmux plugin manager
```
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```
```
prefix I      # install plugins
prefix U      # update plugins
prefix alt u  # uninstall plugins
```
## Tmux vim mode
```
prefix [      # enter into tmux vim mode
Ctrl-c or enter # exit tmux vim mode
