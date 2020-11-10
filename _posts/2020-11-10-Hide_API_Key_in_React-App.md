---
title: "[React]Hide API Key in React-App"
date: 2020-11-10 14:43:35

categories:
  - React
---

**Warning**: Exposing API key is extremely dangerous.

If API key is stolen by malicious users, you will get charged for large amounts of API calls.  
Already uploaded API key to your GitHub repo? Follow these steps below immediately.

## 1. Create .env file

To store our valuable API key, create `.env` file in the root directory of your project.

+-- public  
+-- src  
+--`.env` ← `Here`  
+--.gitignore  
+--package-lock.json

## 2. Store your API key

Type your API key in `.env` file like below:

```
REACT_APP_API_KEY=A1B23YOURAPIKEY
```

Don't forget to prepend `REACT_APP_` to the name of API key, and don't write semicolon, double quotes, etc.

## 3. Add .env file .gitignore

`.gitignore` file helps you not to be pushed in your repo by ignoring the files listed.

#misc ← `Here`  
.DS_Store  
`.env`  
.env.local  
.env.development.local

## 4. Call API with a secure key

Now, you can securely call API.

```javascript
const API_KEY = process.env.REACT_APP_API_KEY;
console.log(API_KEY);
```