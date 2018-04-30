# Install [Hugo](https://gohugo.io/)

정적 웹 페이지 생성을 위해 **휴고**를 이용하였습니다.

포스팅을 로컬 환경에서 미리 확인해 보고, 깃헙으로 배포를 하기 위해서는 **휴고**를 설치 해 주어야 합니다.

아래의 방법을 참고해 각 운영체제 별로 설치해 주세요.

## Mac

[HomeBrew](https://brew.sh)를 이용해 설치
```
brew install hugo
```

## Windows

[Chocolatey](https://chocolatey.org/)를 이용해 설치
```
choco install hugo -confirm
```

# Clone Souce Code

최초 한번 블로그 소스 코드를 깃헙으로부터 내려 받아 합니다.

> 만약 [Git](https://git-scm.com)이 설치되어있지 않다면 [이곳에서](https://git-scm.com/downloads) 설치해 주세요.

## 블로그 소스 설치

```
git clone git@github.com:rgpkorea/rgpkorea.github.io.git
```

## 테마 설치

테마가 서브모듈로 설정되어 있습니다. 최초 소스 코드를 다운 받으셨다면 테마도 내려 받아야 합니다.

블로그 소스코드가 받아져 있는 폴더로 이동해서 서브모듈을 설치합니다.

```
git submodule init
git submodule update
```

## 구조

### Branch

* **develop:** 기본 브랜치로 설정되어 있는 브랜치. 새 글추가 및 소스코드 수정 등은 전부 이 브랜치에서 수행 합니다.

* **master:** 배포되고 나면 생성되는 static 파일들. 실제 깃헙 페이지가 바라보고 있는 브랜치이며, 일반적으로는 직접 수정 할 일이 없습니다.

### Directory

* **archetypes:** 포스팅 생성시 자동 입력되는 메타 정보를 설정하는 곳

* **content:** 포스팅 될 `.md`파일들이 위치

* **dist:** 배포시 master브랜치로 복사 될 내용이 임시로 저장되는 곳

* **layouts:** 각종 화면을 구성하고 있는 html파일들이 위치

* **static:** 이미지, 폰트, css, js 등, resource 성격의 파일들이 위치

* **themes:** 서브모듈로 테마가 설치되어 있는 곳

# Start Hugo

로컬에서 포스팅을 확인 해 보고, 새 포스팅을 디플로이 합니다.

> 해당 설명은 Mac OS 위주로 작성되었습니다.

## Run Hugo Server

휴고를 이용해 로컬에 간이 서버를 띄웁니다.

```
hugo serve -D
```
> 여기서 `-D`옵션은 Draft파일까지 보고 싶을 때 추가해 주는 옵션입니다.

정상적으로 실행되고 나면 `http://localhost:1313`주소로 브라우져에서 접근 할 수 있습니다.

기본적으로 라이브 리로드가 지원 되기 때문에, 소스 코드 수정 후 별도의 새로고침 없이 바로 반영되는 것을 확인 할 수 있습니다.

> 최신 버전의 Hugo에서는 빠른 속도를 위해 소스 코드 전체를 다시 빌드 하지 않는 모드가 기본입니다. 
>
> 해제 하고 싶으면 `--disableFastRender` 옵션을 추가해 서버를 띄워 주세요.

## Create New Post

새 글을 작성하는 방법에는 다음의 두가지 방법이 있습니다.

1. Hugo 명령어를 이용해 파일을 생성하는 방법.
  > 일반 포스팅일 경우와 인터뷰일 경우의 경로가 서로 다름에 유의.
2. md 파일을 해당 위치에 직접 복사하는 방법.
  > 첫번째 방법으로 자동 생성시에 자동으로 입력되는 meta 정보를 수동으로 입력해 주어야 함.

### Hugo Command

일반 포스팅
```
hugo new posts/my-first-post.md
```
인터뷰
```
hugo new interview/my-first-intervew.md
```

> **중요!!** 원하는 파일 명 뒤에 확장자 `.md`를 곡 붙여 주셔야 합니다!

### Direct Copy

`.md`파일을 각각의 경로에 복사합니다.

| | 경로 |
| - | :-: |
| **일반 포스팅** | content/posts/ |
| **인터뷰** | content/interview/ |

`.md`파일의 최상단에 다음의 meta 정보를 추가 합니다.

```
---
title: 제목
description: 부제목
author: 작성자
image: post-bg.jpg // 인터뷰일 경우 interview-bg.jpg
date: 2018-02-23T02:04:18+09:00
type: post
draft: true // false로 해야 실제 환경에서 볼 수 있습니다.
---
```

# Deploy

> 배포 전 노출 되어야 할 `.md`파일이 draft상태인지 먼저 확인 합니다. (각 파일의 meta 정보 영역에서 확인)

## Commit & Push

변경사항을 commit하고 저장소로 push합니다.
```
git add .
git commit -am '변경된 내역'
git push origin develop
```

## Run Deploy Script

미리 작성되어 있는 스크립트 파일을 실행합니다.
```
sh deploy.sh
```

# 끗

