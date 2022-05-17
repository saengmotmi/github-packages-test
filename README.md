## README

### 1. 프로젝트 생성

#### package.json 작성

- name: `@조직명/패키지` 이름 으로 짓고, 소문자로만 사용
- version: `npm update patch` 하면 semver 버전이 업데이트 됨
- repository.url: 레파지토리 주소
- publishConfig.registry: `https://npm.pkg.github.com/`로 설정하면 npm이 아닌 github package로 배포

```json
{
  "name": "@saengmotmi/github-packages-test",
  "version": "0.0.2",
  "description": "github package test",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": ["github", "test"],
  "author": "saengmotmi",
  "license": "MIT",
  "repository": {
    "type": "git",
    "url": "https://github.com/saengmotmi/github-packages-test.git"
  },
  "publishConfig": {
    "registry": "https://npm.pkg.github.com/" // npm이 아닌 github package로 배포
  }
}
```

### 2. `~/.npmrc` 설정

- 없으면 파일을 생성하고, 다음 설정을 추가한다.

```bash
//npm.pkg.github.com/:_authToken={{ GITHUB_AUTH_TOKEN }} # github에서 generate한 token (repo, write/read:packages 권한이 필요)
@saengmotmi:registry=https://npm.pkg.github.com/ # 조직명을 추가
```

### 3. npm publish

```bash
$ npm publish
```
