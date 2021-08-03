---
title: "Jilli Docker 적용"
date: 2021-008-03 17:37:28 +0900
categories: docker jilli
---

# Jilli Docker 적용하기
## 환경
- window 10
- docker Desktop  

## Jilli-Manager > Frontend 적용
- ref : [Vue Docker 만들기](https://woolbro.tistory.com/99) 
- frontend 폴더에 frontend.dev.Dockerfile, .dockerignore 파일 생성
  - frontend.dev.Dockerfile
  ```
  FROM node:lts-alpine
  # LABEL MAINTAINER sunghan.bae@bjsystems.kr
  WORKDIR /app
  ADD package.json ./
  ADD . ./
  CMD npm install && npm start
  EXPOSE 9208
  ```
  - .dockerignore
  ```
  node_modules
  npm-debug.log
  ```
- docker build
  > docker build -f frontend.dev.Dockerfile -t lark-manager-dev .
  ![image](https://user-images.githubusercontent.com/7900446/127990139-7b138e01-4c12-4d41-a1f8-04d1e1b3fa9f.png)

- docker desktop에서 volume mount를 위한 resource 등록
![image](https://user-images.githubusercontent.com/7900446/127990200-97fb233b-894d-4797-80f3-cb01321e27ed.png)

- docker run
  > docker run -p 9208:9208 -i --rm -v c:/data/git/lark/lark-manager/frontend:/app lark-manager-dev
