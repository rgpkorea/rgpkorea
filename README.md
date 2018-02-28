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

