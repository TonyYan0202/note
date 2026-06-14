| **指令**                      | **縮寫**     | **說明**                                   |
| --------------------------- | ---------- | ---------------------------------------- |
| **`npm install <name>`**    | `npm i`    | 安裝套件並加入 `dependencies`（正式環境需要）。          |
| **`npm install <name> -D`** | `npm i -D` | 安裝為 `devDependencies`（僅開發時需要，如：Nodemon）。 |
| **`npm install <name> -g`** | `npm i -g` | 全域安裝（通常用於工具類軟體）。                         |
| **`npm install`**           | `npm i`    | 根據 `package.json` 自動安裝專案內所有需要的套件。        |
| **`npm update`**            | -          | 更新所有已安裝套件至符合版本範圍的最新版。                    |
| **`npm uninstall <name>`**  | `npm un`   | 移除套件。                                    |
### 常見套件
#### 後端相關

| 名稱      | 功能                   | TS支援度          |     |
| ------- | -------------------- | -------------- | --- |
| express | 後端框架,Middleware為核心設計 | @types/express |     |
|         | express的中介集          | V4^ 原生         |     |
