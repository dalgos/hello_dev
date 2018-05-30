# Environment for Development with macOS

## Installation

* iTerm2@latest [here](https://www.iterm2.com/downloads.html)
* iTerm Color Themes [here](https://github.com/bahlo/iterm-colors)
* iTerm2 brogrammer theme [here](https://github.com/dalgos/hello_dev/blob/master/brogrammer.itermcolors)
* Hack font [here](http://sourcefoundry.org/hack/)
* Homebrew
```bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## nodejs
```bash
// 6.x
$ curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs
// 8.x
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```

## vim@8.x (required homebrew.)
```bash
$ brew install vim --with-override-system-vim
```

## yarn
```bash
// macos
$ brew install yarn
// debian, ubuntu
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
// or
sudo apt-get update && sudo apt-get install yarn
```

## oh-my-zsh
⛓[github](https://github.com/robbyrussell/oh-my-zsh)
```bash
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
### theme
⛓[spaceship-zsh-theme](https://github.com/denysdovhan/spaceship-prompt)

```bash
npm install -g spaceship-prompt
```

zsh의 custom theme 폴더로 spaceship.zsh-theme 파일을 symlink 합니다

```sh
$ ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

`.zshrc` 파일을 수정합니다.

```sh
ZSH_THEME="spaceship"
```

## Macvim
vim 8.0 설치하고, macvim으로 대체하기 ⛓[참고링크](https://nolboo.kim/blog/2016/09/16/vim-8-upgrade/)
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

vim plugin manager
vim-plug[here](https://github.com/junegunn/vim-plug)

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

## IDE

### ATOM
[download page](https://atom.io)

#### pkgs
* git-plus : git 명령어를 커맨드 팔레트에서 지원
* linter-eslint : eslint 리포팅 플러그인 (linter, linter-ui-default, intensions, busy-signal 필수 - 자동설치)
* activate-power-mode : 팡!팡!(느려짐 주의)
* atom-ternjs : javascript code intelligence
* file-icons : Assign file extension icons
* file-types : Specify additional file types for lang
* language-babel : Add syntax for Babel
* language-javascript-jsx : Add syntax for jsx

### VSCode
[download page](https://code.visualstudio.com/download)

#### pkgs
* [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
* [Bracket Pair Colorize](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer)
* [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)
* [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
* [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
* [TSLint](https://marketplace.visualstudio.com/items?itemName=eg2.tslint)
* [React-Native/React/Redux snippets for es6/es7](https://marketplace.visualstudio.com/items?itemName=EQuimper.react-native-react-redux)
* [vscode-icons](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons)
* [Javascript(es6) code snippets](https://marketplace.visualstudio.com/items?itemName=xabikos.JavaScriptSnippets)
* [Jest](https://marketplace.visualstudio.com/items?itemName=Orta.vscode-jest)
* [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

## Git
```bash
$ brew install git
```
### pretty git log
```bash
$ git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```
Edit ~/.gitconfig
```bash
[alias]
lg = !"git lg1"
    lg1 = !"git lg1-specific --all"
    lg2 = !"git lg2-specific --all"
    lg3 = !"git lg3-specific --all"

    lg1-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(auto)%d%C(reset)'
    lg2-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(auto)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)'
    lg3-specific = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset) %C(bold cyan)(committed: %cD)%C(reset) %C(auto)%d%C(reset)%n''          %C(white)%s%C(reset)%n''          %C(dim white)- %an <%ae> %C(reset) %C(dim white)(committer: %cn <%ce>)%C(reset)'
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
$ sudo chown -R $(whoami) /usr/local/n
```

## Browsers

### Chrome
[download page](https://www.google.co.kr/chrome/browser/desktop/index.html)

#### Extensions (usable with Canary too)
* [React Developer tools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi)
* [Redux devTools](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd) : [Github](https://github.com/zalmoxisus/redux-devtools-extension)
* [Vue.js devTools](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)


### Chrome Canary
[download page](https://www.google.co.kr/chrome/browser/canary.html)

### Firefox
[download page](https://www.mozilla.org/ko/firefox/new/)

### Opera
[download page](http://www.opera.com/ko)

### Vivaldi
[download page](https://vivaldi.com)
