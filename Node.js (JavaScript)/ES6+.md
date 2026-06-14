變數宣告
## 1. 變數宣告：`let` 與 `const`

早期只有 `var`（有變數提升與作用域問題）。現在請遵循：

- **`const`**: 優先使用。宣告後不可重新賦值（但物件內部的屬性可以改）。
- **`let`**: 只在變數需要「重新賦值」時使用（如：迴圈、計數器）。

## 2. 箭頭函式 (Arrow Functions)

讓函式寫法更精簡，且不綁定自己的 `this`。

```js
// 傳統寫法
function add(a, b) { return a + b; }

// ES6 箭頭函式
const add = (a, b) => a + b;
```

## 3. 樣板字串 (Template Literals)

處理字串與變數組合時，不再需要痛苦的 `+`。使用反引號 **`** 並配合 `${}`。

```js
const name = "Gemini";
console.log(`Hello, my name is ${name}!`);
```


## 4. 解構賦值 (Destructuring Assignment)

這是後端處理 API 回傳資料或 `req.body` 時最常用的功能。

```
const user = { id: 1, name: "Alice", email: "a@test.com" };

// 直接從物件取出屬性
const { name, email } = user;
console.log(name); // Alice
```

## 5. 物件屬性簡寫 (Property Shorthand)

當變數名稱與物件屬性名稱相同時，可以縮寫。

```
const username = "Tom";
// 舊：{ username: username }
// 新：
const userObj = { username }; 
```

## 6. 展開與其餘運算子 (Spread & Rest)

使用 `...` 來複製陣列/物件，或接收不固定數量的參數。


```
// 複製並新增屬性
const oldObj = { a: 1 };
const newObj = { ...oldObj, b: 2 }; // { a: 1, b: 2 }

// 合併陣列
const arr = [...list1, ...list2];
```

## 7. Promise 與非同步處理

ES6 引入了 `Promise`，解決了「回呼地獄 (Callback Hell)」。 _註：雖然 `async/await` 是 ES8 提出的，但它是建立在 ES6 Promise 之上的核心應用。_

## 8. 模組化 (Modules)

現在可以使用 `import` 與 `export` 來拆分代碼檔案。

```
// math.js
export const add = (a, b) => a + b;

// main.js
import { add } from './math.js';
```