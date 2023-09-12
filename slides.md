---
# https://github.com/slidevjs/slidev/blob/v0.42.5/packages/types/src/config.ts
theme: eloc
---

# KT-AXA SE Community

## Knowledge Sharing

---

## What's new in Node.js 20

(Also features recap in 14, 16, 18)

---

## Agenda

1. Features recap in Node.js 14, 16, 18
2. Live demo

---

## Node.js 14

- `randomUUID` (Good bye uuid package)
- Top-Level await

---

## Node.js 14

```js
// ES Module
import { randomUUID } from 'crypto';

// commonjs
const { randomUUID } = require('crypto');

randomUUID(); // 'c4a760a8-dbcf-4d05-ae27-eb46b3d2bb1d'
```

---

## Node.js 14

```js
// Top-Level await
export const asyncFunc = async () => {
  return Promise.resolve('Hi!, Top-level await is working!');
};

const result = await asyncFunc(); // Hi!, Top-level await is working!
```

---

## Node.js 16

- `Array.prototype.at`

---

## Node.js 16

```js
const arr = ['a', 'b', 'c', 'd', 'e'];

arr.at(0); // 'a'
arr.at(-1); // 'e'
arr.at(100); // undefined
arr.at(); // falsy values always return 1st element
```

---

## Node.js 18

- `watch` mode (Good bye nodemon)
- `fetch` API (Good bye node-fetch package)
- `Array.prototype.findLast`
- `Array.prototype.findLastIndex`

---

## Node.js 18

```bash
# watch mode
node --watch index.js
```

---

## Node.js 18

```js
// fetch API
const response = await fetch('https://jsonplaceholder.typicode.com/users/1');
const user = await response.json();
```

---

## Node.js 18

```js
// Array.prototype.findLast
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];
numbers.findLast((n) => n % 2 === 0); // 8

// Array.prototype.findLastIndex
numbers.findLastIndex((n) => n % 2 === 0); // 7
```

---

## Node.js 20

- Support load `.env` file
- Statble native test runner

---

## Node.js 20

```bash
# .env
PORT=3000
DATABASE_URL=postgres://user:pass@localhost:5432/db
FOO=BAR

node --env-file .env index.js
```

---

## Node.js 20

```js
import { test, mock } from 'node:test';
import assert from 'node:assert';
import fs from 'node:fs';

mock.method(fs, 'readFile', async () => 'Hello World');

test('synchronous passing test', async (t) => {
  // This test passes because it does not throw an exception.
  assert.strictEqual(await fs.readFile('a.txt'), 'Hello World');
});
```

---

# Thank you!

## Q&A