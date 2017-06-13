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

## Macvim
vim 8.0 설치하고, macvim으로 대체하기 [참고링크](https://nolboo.kim/blog/2016/09/16/vim-8-upgrade/)
```bash
$ brew install macvim --override-system-vim
```
macvim 터미널에서 열기
```bash
$ macvim -v
```
alias 설정하기
```bash
$ alias vi="macvim -v"
$ alias vim="macvim -v"
```

## IDE

### ATOM
[download page](https://atom.io)

#### pkgs
* git-plus : git 명령어를 커맨드 팔레트에서 지원
* linter-eslint : eslint 리포팅 플러그인 (linter, linter-ui-default, intensions, busy-signal 필수 - 자동설치)
* activate-power-mode : 팡!팡!

### VSCode
[download page](https://code.visualstudio.com/download)

## Git
```bash
$ brew install git
```
## NodeJS (with NPM)
```bash
$ brew update
$ brew install nodejs
```

### n@npm
```bash
$ npm i n -g
$ n latest
```
권한 오류 발생 시
```bash
$ sudo chown -R $USER:admin /usr/local/n
```

## Browsers

### Chrome
[download page](https://code.visualstudio.com/download)

