markdown#
BLACKPINK 팬 홈페이지

## 프로젝트 소개

BLACKPINK 팬 페이지 만들기(GIT & GITHUB 이용해서 협업 프로젝트)

## 팀원

전강민 : 메인 및 전체 arrange
김종찬 : PROFILE
원세빈 : DISCOGRAPHY
안준영 : GALLERY
한창규 : VIDEO 전체 arrange
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

## 주요 기능

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

### commit/push/pr

문제:
pr이 올라오지 않음

원인:
commit만 올렸거나 push만 한 상태일 것

해결:
add, commit, push, pr 과정 다시 점검 => 과정을 빼먹지는 않았다 체크

### feature/index pull conflict

문제:
PR은 DEV에 잘 돼있는데 왜 feature/index에서 pull이 안 됨

원인:
merge를 하지 않아서

해결:
git checkout dev
git pull origin dev
git checkout feature/index
git merge dev

### merge conflict

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

적용되지 않음

<footer></footer>

해결:
footer 적용하여 수정함.

### Merge Conflict

문제: git pull 과정에서 notice.html 파일에 충돌 발생.

원인: 같은 부분을 서로 다른 브랜치에서 수정했기 때문.

해결: 충돌 표시(<<<<<<, ======, >>>>>>)를 직접 수정하고
의도한 코드만 남긴 뒤 재커밋하여 해결.

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

### 전체 다 PR 올리지 말고 COMMIT 만 해주세요!!

### 나연님 -> 버그 해결

### html 폴더 내 memberStorys 폴더 생성 -> 풀 받으면 폴더 있을 것 -> dev 쪽에는 지금 없음 -> 폴더 생성하기.

### notice -> 버그 해결

## 라이선스

본 프로젝트는 학습용으로 제작되었습니다.
이미지는 무료 라이선스 자료를 사용했습니다.

## 배운 점

각자 배운 점 이야기 해주시면 좋을 것 같습니다.
