# VisualStudio Code Debugging ReactJS

1. 최신 vscode를 [다운로드](https://code.visualstudio.com/download) 합니다.
1. vscode의 extension 중 [Debugger for chrome] (https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) 를 설치합니다.

1. vscode의 debugger 탭을 활성화하고 launch.json을 아래와 같이 작성합니다.

```json

{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Chrome",
            "type": "chrome",
            "request": "launch",
            "url": "http://localhost:3000",
            "webRoot": "${workspaceRoot}/src"
        }
    ]
}

```
debugger 탭을 활용하여 react app을 디버깅할 수 있습니다. :-)
