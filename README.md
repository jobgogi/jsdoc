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

## 빌드 스크립트 추가
`package.json` 파일를 열어 `scripts` 항목에 아래의 내용을 추가한다.
```json
...
"scripts" : {
  "doc": "jsdoc -c jsdoc.json"
}
...
```
그리고 `src` 폴더를 `ROOT`에 생성하고 그 안에 `index.js`를 생성 후 아래의 명령어를 실행한다.
```shell
$ npm run doc
```
그럼 다음과 같은 폴더 구조로 완성이 될 것이다.
```
.
├── README.md
├── docs
├── jsdoc.json
├── node_modules
├── package-lock.json
├── package.json
└── src
    └── index.js
```
