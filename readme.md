# BLACKPINK 팬 홈페이지

## 프로젝트 소개

BLACKPINK 팬 페이지 만들기
(GIT & GITHUB 이용한 협업 프로젝트)

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

# 📁 git-project

```bash
git-project/
├── index.html
├── html/
│   ├── memberStories/
│   │   ├── jennie.html
│   │   ├── jennieDetail.html
│   │   ├── jisoo.html
│   │   ├── jisooDetail.html
│   │   ├── lisa.html
│   │   ├── lisaDetail.html
│   │   ├── rose.html
│   │   └── roseDetail.html
│   ├── discography.html
│   ├── gallery.html
│   ├── memberStory.html
│   ├── notice.html
│   ├── profile.html
│   └── video.html
├── css/
│   ├── common.css
│   ├── commonReverse.css
│   ├── discography.css
│   ├── gallery.css
│   ├── main.css
│   ├── memberStory.css
│   ├── notice.css
│   ├── profile.css
│   ├── snsContact.css
│   └── video.css
├── images/
│   ├── common/
│   ├── discography/
│   ├── gallery/
│   └── memberStory/
└── readme.md
```

## Description

- `index.html` : 메인 페이지
- `html/` : 서브 페이지 모음
- `css/` : 스타일시트 파일
- `images/` : 페이지별 이미지 리소스
- `readme.md` : 프로젝트 설명 문서

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

```bash
git-project/
├── index.html
├── profile.html
├── gallery.html
├── discography.html
├── video.html
├── memberStory.html
└── ...
```

=> 가독성 떨어짐, 구조 정리 어려움 => 유지보수 어려움

해결:
index.html을 제외한 모든 html 파일들을 전부 html이라는 별도의 폴더에 넣음

```bash
git-project/
├── index.html
├── html/
│   ├── discography.html
│   ├── gallery.html
│   ├── profile.html
│   ├── video.html
│   └── memberStory.html
├── css/
├── images/
└── ...
```

=> 폴더 구조 가독성 좋아짐 => 유지보수 수월
(단, HTML 파일 위치 변경으로 인해: <a href> 경로 수정 필요, CSS 경로 수정 필요, 이미지 경로 수정 필요할 수 있음)

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

### 나연님 -> 버그 해결(2026.2.24 강민님과 디스코드에서 대화 나눔)

## 라이선스

본 프로젝트는 학습용으로 제작되었습니다.
이미지는 무료 라이선스 자료를 사용했습니다.

## 배운 점

김나연:
branch를 나누고 github 웹 페이지 내에서 PR로 서로 코드가 어떻게 진행되고 있는지 여러가지로 확인해볼 수 있어 좋았습니다. 특히 conflict 가 난 경우 PR로 상황을 보고 해결할 수 있어 위험 부담도 적어지고 이런이런 충돌이 일어났다 하는 상황 공유가 편리하였습니다.

전강민:
혼자만 잘한다고 해서 다 되는게 아니라, 협력이기 때문에 각자의 코드를 서로 리뷰해주며 도움을 주고 받는 것도 정말 중요하다고 생각되었습니다. 또한, 컨벤션을 미리 정해두고 하니까 초반에는 맞추는게 살짝 힘들었지만 뒤로 갈 수록 수월하게 협업이 되는게 느껴져서 컨벤션의 중요성을 느낄 수 있었습니다.

김종찬:
지난 번 팀소개 페이지 협업과 달리 각자의 브랜치를 활용하여 협업을 진행함으로써, 다수의 팀원이 동시에 작업하면서도 코드의 안정성을 유지하는 협업 프로세스를 경험했습니다. 작업 중 발생한 다양한 문제들을 해결하며 협업 하였고, 작업 과정에서 공통 CSS와 서로의 페이지 레이아웃 등을 확인하고 의견을 나누며, 협업에서의 일관성 확보도 얼마나 중요한지 실감했습니다.

원세빈:
처음에 요구사항을 정리하고 프로젝트의 진행 방향을 정하는 데 시간이 꽤 걸렸습니다. 이 과정을 통해 기획 단계의 중요성과 소통이 얼마나 핵심적인지 깊이 체감했습니다. 막상 구현을 시작하려니 배운 내용이 잘 기억나지 않아 당황하기도 했지만, 차근차근 해결해 나가며 완성되어 가는 모습에 큰 뿌듯함을 느꼈습니다.
특히 Git을 사용하며 충돌(Conflict)이 발생했을 때 코드가 망가질까 봐 걱정했던 기억이 남는데, 반복하다 보니 점차 익숙해졌습니다. 팀원들과 실시간으로 작업물을 공유하며 웹페이지가 완성되어 가는 과정을 확인하니, 협업의 효율성과 공통 코드 관리의 장점을 확실히 알 수 있었던 소중한 경험이었습니다.

임주연:

1. 초반에 어떤 아티스트로 정할지 부터 어떤 스타일로 페이지를 만들기 까지 이 모든 사항들을 팀원들과 하나하나씩 정하는 과정이 생각보다 오래 걸렸습니다. 팀원들 각자 서로 다른 아이디어와 방향성을 가지고 있었지만 하나의 방향성으로 합쳐지면서 프로젝트의 시작인 기획 단계의 중요성을 깨달았고, 특히 팀원들과의 원활한 소통이 무엇보다 가장 중요하다고 느꼈습니다.
2. 서로 각자의 브랜치에서 작업을 하면서 conflict가 가장 두려웠습니다. 그래서 push, pr, pull 할 때 마다 긴장되고 불안했었습니다. 특히 내 작업이 잘못되는 것은 상관없지만 다른 팀원들의 작업에 영향을 줄까봐, 민폐가 될까 그것이 가장 두려웠습니다. 실제로 pr을 했지만 충돌이 생겨서 엄청 당황해서 우왕좌왕하였고 push 할 때도 제 local에서 conflict가 발생해서 강의자료 찾아보고 강의 유튜브도 다시 보면서 해결해보려고 노력했었습니다. 그리고 pr 할 때마다 내가 잘 하고 있는지 확인하게 되고 혹시 잘못하고 있을까봐 강의자료를 같이 보면서 pr을 했었습니다. 이 과정을 경험하면서 내용을 이해하고 있는 것과 실제 구현하는 실습은 확실히 다르다는 것을 뼈저리게 느꼈고 강사님의 강의 자료와 강의영상을 반복하고 실습하고 반복하고 실습하고를 정말 지겨울 정도로 해야지 겨우 익숙해지겠다는 생각이 들었습니다.
3. git을 통해 팀원들과의 협업을 하면서 저에게 가장 아쉬웠던 점은 제 꺼 하기도 바빠서 팀원들과의 소통을 실시간으로 원활하게 하지 못하였습니다. 제 작업을 하다가 돌아가고 하다가 돌아가고 하다 보니 정신이 없어서 소통보다는 다들 이렇게 하고 있구나, 이렇게 소통하고 있네를 느끼기만 했고 직접 적극적으로 참여는 많이 하지 못하였고 이 점이 참 아쉽지만 또 배우는 시간이었습니다.
4. 첫 프로젝트를 하면서 정말 복습과 실습을 많이 해야겠다는 동기부여도 되었습니다. 또한, 내가 수정했던 것들이 웹에 바로 구현이 되면 또 뿌듯하고 pr 할 때는 두렵고 긴장하고를 반복하면서 속도는 느리지만 하나씩 배워가는 과정이 힘들지만 재밌었습니다. 정말 팀원들께서 많이 도와주셔서 첫 프로젝트를 잘 끝냈던 것 같고 그래서 정말 감사했습니다.

=> 결론적으로 복습 복습 복습... 그냥 하자...ㅎㅎ

한창규:

1. 지난 초미니프로젝트를 하면서부터 부족했다고 생각했던 소통이 있었습니다 하지만 이번에는 구조 설계나 팀원들과의 의견을 통해서 하나의 의견으로 모이는데 생각보다 시간을 쓰면서 맞춰가던 부분이 흥미로웠습니다.

2. 각자의 브랜치에서 작업을 하는데 컨플릭이나 실수로 pr을 하지 않을때도 있고 그랬습니다 그런 부분들을 보면서 보기와는 다르게 협업하는 과정들이 쉽지 않았고 특히 컨플릭이 생겼을 때 정확히 어떤 부분이 문제이고 해결하는 방법을 생각하고 의논하는 부분이 있어서 많이 배운 것 같습니다.

3. 실제로 원하는 구조를 잡아도 막상 스타일을 입히기전에 구조를 보면 이게 뭐지 싶은 것도 많았지만 하나하나 스타일을 입히면서 팀원들과 만든 페이지가 결국 하나의 dev에 모여서 완성이 되가고 있던게 참 신기했습니다.

4. 첫 날을 제외하고 다 빠지게 되어서 너무 아쉽습니다. 팀장으로서도 죄송한 부분이 많고 그럼에도 불구하고 다들 이해해주시고 프로젝트를 끝까지 완성시킨 것 같아서 고마운 마음뿐입니다.

이번을 계기로 확실히 배웠던 것에 대해서 더 이해하고 스스로 설계할 수 있으며 코드를 해석하는 능력도 조금은 갖춘 것 같습니다.
