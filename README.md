# issue-5962

## Steps on reproducing the issue

1. Run npm init in root of app (this will create a package.json file)
2. Install express in root of app : `npm install --save express` (save will update package.json with express dependency)
3. Copy the files in the repo
4. Do `node server` : it should output "server on 8000"
5. Start http://localhost:8000/ : your index.html will be called

Following this will reproduce this error:

```
@firebase/analytics: TypeError: undefined is not an object (evaluating 'e.push') 
(anonymous function) — firebase-analytics-compat.min.js:885 asyncFunctionResume
ke — firebase-analytics-compat.min.js:1020
getOrInitializeService — firebase-app-compat.min.js:362
getImmediate — firebase-app-compat.min.js:261
(anonymous function) — firebase-analytics-compat.min.js:1176
getOrInitializeService — firebase-app-compat.min.js:362
getImmediate — firebase-app-compat.min.js:261
_getService
(anonymous function) — firebase.js:15
```

This can only be encountered if you'll run it in Safari browser. Running it on other browser will produce no error and will run as intended.
