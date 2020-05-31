<h1 align="center">Koreanbots - JS SDK</h1>
<p>
  <a href="https://www.npmjs.com/package/koreanbots" target="_blank">
    <img alt="Version" src="https://img.shields.io/npm/v/koreanbots.svg">
  </a>
  <a href="https://github.com/koreanbots/js-sdk#readme" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
  <a href="https://github.com/koreanbots/js-sdk/graphs/commit-activity" target="_blank">
    <img alt="Maintenance" src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" />
  </a>
  <a href="https://github.com/koreanbots/js-sdk/blob/master/LICENSE" target="_blank">
    <img alt="License: MIT" src="https://img.shields.io/github/license/koreanbots/js-sdk" />
  </a>
  <a href="https://npmcharts.com/compare/koreanbots?minimal=true" target="_blank">
    <img alt="Downloads" src="https://img.shields.io/npm/dm/koreanbots.svg">
  </a>
  <a href="https://github.com/koreanbots/js-sdk/workflows/.github/workflows/eslint.yml" target="_blank">
    <img alt="eslint.yml" src="https://github.com/koreanbots/js-sdk/workflows/.github/workflows/eslint.yml/badge.svg">
  </a>
</p>

> JS SDK for <a href="https://koreanbots.dev">Koreanbots</a>

### 🏠 [홈페이지](https://koreanbots.dev)

## 설치

```sh
npm install koreanbots
```

## 테스트하기

- discord.js v12
```js
const { MyBot } = require("koreanbots")
const Bot = new MyBot("Koreanbots 토큰")

let update = count => Bot.update(count) 
    .then(res => console.log("서버 수를 정상적으로 업데이트하였습니다!\n반환된 정보:" + JSON.stringify(res)))
    .catch(console.error)

client.on("ready", () => {
    console.log(`${client.user.tag}로 로그인하였습니다.`)

    update(client.guilds.cache.size) // 준비 상태를 시작할 때, 최초로 업데이트합니다.
    setInterval(() => update(client.guilds.cache.size), 600000) // 10분마다 서버 수를 업데이트합니다.
})

client.login("토큰")
```

- discord.js v11
```js
const { MyBot } = require("koreanbots")
const Bot = new MyBot("Koreanbots 토큰")

let update = count => Bot.update(count) 
    .then(res => console.log("서버 수를 정상적으로 업데이트하였습니다!\n반환된 정보:" + JSON.stringify(res)))
    .catch(console.error)

client.on("ready", () => {
    console.log(`${client.user.tag}로 로그인하였습니다.`)

    update(client.guilds.size) // 준비 상태를 시작할 때, 최초로 업데이트합니다.
    setInterval(() => update(client.guilds.size), 600000) // 10분마다 서버 수를 업데이트합니다.
})

client.login("토큰")
```

- 아이디로 봇 정보 가져오기 (/bots/get/:id)
```js
const koreanbots = require('koreanbots');
const Bots = new koreanbots.Bots()

Bots.get("653534001742741552")
    .then(r=> console.log(r)) // 반환되는 데이터는 옆 링크를 참고해주세요: https://koreanbots.dev/js-sdk/interfaces/_types_.getbyid.html
    .catch(e=> console.error(e))
```

## Author

👤 **zero734kr**

* 개인 Github: [@zero734kr](https://github.com/zero734kr)
* Organization Github: [@koreanbots](https://github.com/koreanbots)

## 🤝 도움주기

이슈와 PR은 모두 환영입니다!<br>
무언가 문제가 생겼다면 [이슈 페이지](https://github.com/koreanbots/js-sdk/issues) 또는 [koreanbots 통합 이슈 페이지](https://github.com/koreanbots/koreanbots)에 저를 언급하여 알려주세요! ``(예시: @zero734kr, js sdk 버그입니다.)``<br>
코드 수정 요청은 [PR 페이지](https://github.com/koreanbots/js-sdk/pulls)에 올려주세요.

## 서포트

만약 이 모듈이 도움이 되었다면 ⭐️를 눌러주세요!

## 📝 라이센스

Copyright © 2020 [zero734kr](https://github.com/koreanbots).<br />
This project is [MIT](https://github.com/koreanbots/js-sdk/blob/master/LICENSE) licensed.

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
