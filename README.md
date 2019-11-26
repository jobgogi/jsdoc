# JSDoc

> 참고한 유튜버
> [Documenting Your JavaScript | JSDoc Crash Course](https://youtu.be/YK-GurROGIg)

## JSDoc 설치
```shell
$ npm i -D jsdoc
npm notice created a lockfile as package-lock.json. You should commit this file.
+ jsdoc@3.6.3
added 25 packages from 22 contributors and audited 27 packages in 4.438s
found 0 vulnerabilities
```

## jsdoc 설정 파일 생성
`Root` 폴더에 `jsdoc.json` 파일을 생성하여 아래와 같이 입력한다.
[jsdoc 설정](https://jsdoc.app/about-configuring-jsdoc.html)
```json
{
  "source": {
    "include": ["src"],
    "includePattern": ".js$",
    "excludePattern": "(node_modules/|docs)"
  },
  "plugins": ["plugins/markdown"],
  "templates": {
    "cleverLinks": true,
    "monospaceLinks": true
  },
  "opts": {
    "recurse": true,
    "destination": "./docs"
  }
}
```
