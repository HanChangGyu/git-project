Markdown

# BLACKPINK 팬 홈페이지

## 프로젝트 소개

BLACKPINK 팬 페이지 만들기
(GIT & GITHUB 이용해서 협업 프로젝트)

## 팀원

전강민 : 메인 및 전체 arrange
김종찬 : PROFILE
원세빈 : DISCOGRAPHY
안준영 : GALLERY
한창규 : VIDEO 및 전체 arrange
김나연 : MEMBER STORY
임주연 : NOTICE

## 페이지 구성

- 메인
- PROFILE
- DISCOGRAPHY
- GALLERY
- VIDEO
- MEMBER STORY
- NOTICE

## 사용 기술

- HTML
- CSS
- Git / GitHub

## 폴더 구조

/git-project
├── index.html
├── html/
│ ├── memberStories/
│ │ ├── jennie.html
│ │ ├── jennieDetail.html
│ │ ├── jisoo.html
│ │ ├── jisooDetail.html
│ │ ├── lisa.html
│ │ ├── lisaDetail.html
│ │ ├── rose.html
│ │ └── roseDetail.html
│ ├── discography.html
│ ├── gallery.html
│ ├── memberStory.html
│ ├── notice.html
│ ├── profile.html
│ └── video.html
├── css/
│ ├── common.css
│ ├── commonReverse.css
│ ├── discography.css
│ ├── gallery.css
│ ├── main.css
│ ├── memberStory.css
│ ├── notice.css
│ ├── profile.css
│ ├── snsContact.css
│ └── video.css
├── images/
│ ├── common
│ ├── discography
│ ├── gallery
│ └── memberStory
└── readme.md

## 주요 기능

- HTML/CSS을 통해 웹사이트 구현
- Git 브랜치 통해 협업
- 메인 페이지에서 각 메뉴(PROFILE, DISCOGRAPHY, GALLERY, VIDEO, MEMBER STORY, NOTICE)로 이동 가능
- 아티스트 프로필 정보 제공
- 앨범 및 디스코그래피 소개
- 이미지 갤러리 페이지 구현
- 영상 콘텐츠 페이지 구현
- 멤버 스토리 인스타그램 형식으로 구성
- 공지사항 페이지 구현
- 공통 레이아웃 Header / Footer 구조 적용

## 컨벤션

### 파일 저장 이름 작성법

파일 이름 통일성 필요 -> 정리와 가독성 위해

일반 파일은 camelcase 사용

userLogin (camelcase)
memberStory (camelcase)

이미지 파일은 snakecase 사용

blackpink_banner.png (snakecase)
이렇게 진행하기로 함

### css class 명 통일

class 명은 kebabcase 사용

header-inner처럼 (kebabcase)

### style.css 파일

문제
: css 방법 통일 되지 않음

원인
: html에서 style로 작성하신 분들과 css 파일로 따로 만든 분들 나눠져 있었음

해결:
css 폴더에 모든 css 파일 넣음. html에서 style 하신 분들 css 파일로 분리함.

## 트러블 슈팅

### commit/push/PR 과정에서의 오류

문제:
pr이 올라오지 않음

원인:
commit만 하고 push를 하지 않았거나, push는 했지만 PR 생성을 하지 않음.

해결:
add -> commit -> push -> pr 순서 다시 점검 => 각 단계가 제대로 진행되었는지 확인하기

### feature/index pull conflict

문제:
PR은 DEV에 잘 되어있는데 왜 feature/index에서 pull이 안 됨

원인:
merge를 하지 않아서

해결:
git checkout dev
git pull origin dev
git checkout feature/index
git merge dev

### Merge Conflict

문제: git pull 과정에서 memberStory.html 파일에 충돌 발생.

원인:
이전 footer 변경사항이 적용되지 않아서

이전 변경 사항

<footer class="main-footer">
      <div class="footer-logo">BLACKPINK IN YOUR AREA</div>
      <p class="copyright">
        Copyright(c) 2026 YG ENTERTAINMENT. All rights reserved.
      </p>
    </footer>

적용되지 않은 상태

<footer></footer>

해결:
footer 적용하여 수정함.

### Merge Conflict

문제: git pull 과정에서 notice.html 파일에 충돌 발생

원인: 같은 부분을 서로 다른 브랜치에서 수정했기 때문

해결: 충돌 표시(<<<<<<, ======, >>>>>>)를 직접 수정하고
의도한 코드만 남긴 뒤 재커밋하여 해결

### 폴더 구조 정리

문제:
기존엔 html 파일들이 전부 최상위폴더에 있었는데, 최상위 폴더에 너무 많은 html 파일들이 있음

git-project
├── index.html
├── profile.html
├── gallery.html
├── discography.html
├── video.html
├── memberStory.html
...

=> 가독성 떨어짐, 구조 정리 어려움 => 유지보수 어려움

해결:
index.html을 제외한 모든 html 파일들을 전부 html이라는 별도의 폴더에 넣음

/git-project
├── index.html
├── html/
│ ├── discography.html
│ ├── gallery.html
│ ├── profile.html
│ ├── video.html
│ └── memberStory.html
...
├── css/
├── images/
...

=> 폴더 구조 가독성 좋아짐 => 유지보수 수월
(단, HTML 파일 위치 변경으로 인해: <a href> 경로 수정 필요, CSS 경로 수정 필요, 이미지 경로 수정 필요할 수도??)

### PULL 과정에서의 오류

문제:
html 폴더 내 memberStorys 폴더 생성하였고 PULL하면 memberStorys폴더 있어야 했지만 dev에 없었음

해결:
폴더 생성해서 파일 추가하기

### Conflict 최소화

문제:
여러 명이 동시에 작업 중에 PR이 많아지면 정리하기 어려워지고 Merge Conflict 발생 확률 높아짐

해결:

- 전체 다 PR 올리지 말고 COMMIT만 하기(merge 하지 말고 브랜치에만 정리하기) => 정리된 후 PR 진행하기
- 서로 대화하면서 수시로 pull 하기

### 나연님 -> 버그 해결(2026.2.24 강민님과 디스코드에서 대화 나눔)?????

## 라이선스

본 프로젝트는 학습용으로 제작되었습니다.
이미지는 무료 라이선스 자료를 사용했습니다.

## 배운 점

각자 배운 점 이야기 해주시면 좋을 것 같습니다.
