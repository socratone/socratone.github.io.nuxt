---
title: Docker 시작하기
description: 도커를 쓰는 기본적인 방법에 대해 다뤘습니다.
img: docker
alt: docker icon
author: socratone
category: docker
---

# Docker 시작하기

도커는 다양한 방식으로 활용된다.  
개발 환경을 구축할 때 쓰기도 하는데  
이런 경우라면 도커를 알아야 여러가지 대처를 할 수 있다.  
도커를 쓰는 기본적인 방법에 대해서 다루겠다.

### 1. 홈페이지 등에서 도커 데스크탑을 설치한다.

### 2. docker images 명령어를 입력해서 현재 설치된 이미지를 확인한다.

### 3. 우분투 이미지를 설치한다.

```shell
docker pull ubuntu:14.04
```

### 4. 이미지를 이용해서 컨테이너를 만들고 실행한다.

```shell
docker run -i -t --name 생성할컨테이너이름 ubuntu:14.04 /bin/bash
```

-i 옵션 : 사용자가 입출력을 할 수 있는 상태로 하겠다.  
-t 옵션 : 가상 터미널 환경을 에뮬레이션 하겠다.  
/bin/bash : 실행 파일로 bin bash shell을 쓰겠다.

그러면 컨테이너의 터미널에 들어가게 되고 깃 등 다양한 것들을 설치할 수 있다.

### 6. exit 명령어를 입력한다.

bash가 종료된다.  
메인 실행파일이 종료되면 컨테이너도 종료된다.

### 7. 다음 명령어로 컨테이너 목록을 확인할 수 있다.

```shell
docker ps -a
```

### 8. 다음 명령어로 아이디에 해당하는 컨테이너를 실행하면서 터미널에 들어가지 않을 수 있다.

```shell
docker start 컨테이너이름
```

### 9. 터미널로 들어가는 명령어는 다음과 같다.

```shell
docker attatch 컨테이너이름
```
 
### 10. 컨테이너를 종료하지 않고 밖으로 나오려면

ctrl + p, ctrl + q 

### 11. 컨테이너를 멈추려면

```shell
docker stop 컨테이너이름
```
 
### 12. 컨테이너를 지우려면

```shell
docker rm 컨테이너이름
```
 
### 13. 이미지를 지우려면

```shell
docker rmi 이미지이름
```

참고 : [youtu.be/Bhzz9E3xuXY](https://youtu.be/Bhzz9E3xuXY)