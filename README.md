# mkalias
Quickly create and categorize shell aliases

## Installation
You need Python installed.

Simply copy `mkalias` anywhere in your PATH and make it executable with 

	chmod +x /path/to/mkalias

When you start `mkalias` for the first time, it asks you for the path to your aliases file and stores this information in `/home/yourusername/.config/mkalias/mkaliasconf`. 

## aliases file layout
It is recommended to put aliases in a seperate file from your general shell configuration. In your shell configuration file you have to include the path to the aliases file. 
For example: I have a general shell config file `~/.zshrc` and the alias file `~/.zsh_aliases`. In `~/.zshrc` I include

```bash
if [ -f ~/.zsh_aliases ]; then
    . ~/.zsh_aliases
fi
```

In the aliases file I seperate the different categories with comments. Example

```bash
# cd to favourite directories
alias cdd='cd ~/Downloads'
alias cdm='cd ~/Music'

# edit configs
alias vza='nvim ~/.zsh_aliases'
alias vvi='nvim ~/.config/nvim/init.vim'
```
and so on.

## Usage
Just type `mkalias`. It asks you for a new alias. It then asks you for the command to be executed. Finally you are asked which in which category the new alias should go in. You are shown a list of all existing categorys + the option for a new category. Type the number corresponding to the category. In case you chose to create a new category you are asked for a new category name. Type it in, hit enter and the new alias is stored in your configuration file. Don't forget to source the shell configuration file or start a new shell instance after creating a new alias.

You can list/print all your currently available aliases with `mkalias -l` 
