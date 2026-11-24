# 여행 노트

친구들과 함께하는 여행의 가이드, 지도 파일, 기록과 사진을 모아 두는 저장소입니다.
GitHub Pages로 공개하면 `https://<아이디>.github.io/<저장소이름>/` 주소로 누구나 볼 수 있습니다.

## 폴더 구조

```
index.html                  메인 페이지 (여행 목록)
_template/                  새 여행을 만들 때 복사하는 기본 폴더
trips/
  2026-seonjaryeong/        여행 하나 = 폴더 하나
    index.html              여행 페이지 (자료 · 코스 · 기록 · 사진)
    files/                  가이드 문서, GPX, KML 등 자료
    photos/                 사진
```

모든 HTML 파일은 글꼴과 스타일이 파일 안에 들어 있어 인터넷이 없는 PC에서 내려받아 열어도 똑같이 보입니다.

## 처음 한 번: GitHub Pages 켜기

1. 이 폴더의 내용을 저장소에 그대로 올립니다. `.nojekyll` 파일도 함께 올려야 합니다.
2. 저장소의 **Settings → Pages**로 갑니다.
3. **Source**를 `Deploy from a branch`로, 브랜치를 `main`, 폴더를 `/ (root)`로 고르고 저장합니다.
4. 1~2분 뒤 페이지 위쪽에 사이트 주소가 나타납니다.

## 새 여행 추가하기

1. `_template` 폴더를 복사해 `trips/` 안에 붙이고, 이름을 영문·숫자로 바꿉니다.
   예: `trips/2027-turkey`
2. 자료는 `files/`에, 사진은 `photos/`에 올립니다.
   사진은 긴 변 2000px 안팎으로 줄여 올리면 페이지가 빨리 열립니다.
3. 새 폴더의 `index.html`을 열어 고칩니다.
   - 맨 위 `var TRIP = { ... }`: 자료 목록(`files`)과 사진 목록(`photos`)
   - `<header>` 안: 여행 이름, 소개, 여행지, 날짜
   - `여행 기록` 아래 `<article class="log">`: 기록을 날짜별로 추가
4. 메인 `index.html`의 `var TRIPS = [ ... ]`에 여행 한 덩어리를 추가합니다.

```js
{
  slug: "trips/2027-turkey/index.html",
  title: "형제 부부 튀르키예 여행",
  place: "튀르키예",
  when: "2027년 6월",
  status: "plan",          // plan 준비 중 · now 여행 중 · done 다녀옴
  summary: "한두 문장 소개",
  tags: ["해외", "가족"],
  files: 2, photos: 0,
  ridge: ""                // 비워 두면 됩니다
},
```

## 사진 추가하기

`photos/`에 사진을 올린 뒤, 그 여행 페이지의 `photos` 목록에 한 줄씩 적습니다.

```js
photos: [
  { src: "photos/01-summit.jpg", caption: "선자령 정상석 앞에서", date: "2026-12-13" },
  { src: "photos/02-windmill.jpg", caption: "풍력발전기 설원" }
]
```

메인 페이지 `TRIPS`의 `photos` 숫자도 함께 고치면 목록의 사진 수가 맞게 나옵니다.

## 참고

- 지도 자료 © OpenStreetMap contributors, 고도 자료 SRTM
- 파일은 GitHub 웹 화면에서 **Add file → Upload files**로 끌어다 놓아 올릴 수 있습니다. 사진이 많을 때는 GitHub Desktop이 편합니다.
