# Environment for Development with macOS

## Installation

* iTerm2@latest [here](https://www.iterm2.com/downloads.html)
* iTerm Color Themes [here](https://github.com/bahlo/iterm-colors)
* Hack font [here](http://sourcefoundry.org/hack/)
* Homebrew
```bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
* vim@8.x (required homebrew.)
```bash
$ brew install vim --with-override-system-vim
```
## oh-my-zsh
[github](https://github.com/robbyrussell/oh-my-zsh)
```bash
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
### theme
[spaceship-zsh-theme](https://github.com/denysdovhan/spaceship-zsh-theme)

## ATOM

### download
[here](https://atom.io)

### pkgs@apm

* eslint@latest

* Git@brew
```bash
$ brew install git
```
* NodeJS (with NPM)
```bash
$ brew update
$ brew install nodejs
```

## n@npm
```bash
$ npm i n -g
$ n latest
```
권한 오류 발생 시
```bash
$ sudo chown -R $USER:admin /usr/local/n
```
