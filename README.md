# React 環境變數設置

## .env 檔案

可以分成 .env.local、.env.dev、.env.uat、.env.production 等等的檔案
變數命名規則：前面都要加 REACT_APP，例如：

```
REACT_APP_NOT_SECRET_CODE=thisislocal
```

## 如何使用環境變數

```
process.env.REACT_APP_NOT_SECRET_CODE
```

## 在 package.json 設定不同的環境

需先執行 npm install env-cmd，一個用來管理環境變數的工具

```bash
"dev": "react-scripts start", --> 這個會吃.env.local
"uat": "env-cmd -f .env.uat react-scripts start",
"prod": "env-cmd -f .env.production react-scripts start",
"build:dev": "env-cmd -f .env.dev react-scripts build",
"build:uat": "env-cmd -f .env.uat react-scripts build",
"build": "env-cmd -f .env.production react-scripts build",
"preview": "npx serve -s build",
```
