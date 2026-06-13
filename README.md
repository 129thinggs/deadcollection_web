# Dead Collection — Web Archive

[eetc.] Dead Collection 아카이브 웹사이트

---

## 폴더 구조

```
dead-collection/
├── index.html               ← 메인 랜딩
├── css/
│   └── style.css            ← 공유 스타일
├── js/
│   └── nav.js               ← 공유 JS (뷰어, 라이트박스)
├── coffee/
│   ├── index.html           ← Dead Coffee 서브 인덱스
│   ├── zine.html            ← Zine Viewer (84p)
│   └── archive.html         ← 표본 아카이브
├── cake/
│   ├── index.html           ← Dead Cake 서브 인덱스
│   ├── zine.html            ← Zine Viewer (20p)
│   └── archive.html         ← 표본 아카이브
└── images/
    ├── coffee/
    │   ├── zine/            ← 진 스캔 이미지 (01.jpg ~ 84.jpg)
    │   └── archive/         ← 표본 사진 (DC01.jpg, UDC01.jpg ...)
    └── cake/
        ├── zine/            ← 진 스캔 이미지 (01.jpg ~ 20.jpg)
        └── archive/         ← 표본 사진 (UDC-C01.jpg ...)
```

---

## 이미지 추가하기

### 1. Zine 스캔 이미지

Dead Coffee:
- `images/coffee/zine/01.jpg` ~ `84.jpg`
- 파일명: 두 자리 숫자 (01, 02 ... 84)

Dead Cake:
- `images/cake/zine/01.jpg` ~ `20.jpg`
- 파일명: 두 자리 숫자 (01, 02 ... 20)

### 2. Archive 표본 이미지

**Dead Coffee** — `coffee/archive.html` 파일 열고 SPECIMENS 배열 수정:

```javascript
const SPECIMENS = [
  { code: 'DC01', type: 'dc',  file: 'DC01.jpg',  caption: 'DC01' },
  { code: 'DC02', type: 'dc',  file: 'DC02.jpg',  caption: 'DC02' },
  { code: 'UDC01', type: 'udc', file: 'UDC01.jpg', caption: 'UDC01' },
  { code: 'YDC01', type: 'ydc', file: 'YDC01.jpg', caption: 'YDC01' },
];
```

type: `"dc"` | `"udc"` | `"ydc"`

**Dead Cake** — `cake/archive.html` 파일 열고 SPECIMENS 배열 수정:

```javascript
const SPECIMENS = [
  { code: 'UDC-C01', type: 'udc', file: 'UDC-C01.jpg', caption: 'UDC-C01' },
];
```

---

## 로컬 실행

브라우저에서 직접 index.html을 열거나, 간단한 로컬 서버 사용:

```bash
# Python 3
cd dead-collection
python3 -m http.server 8000
# → http://localhost:8000
```

---

## 키보드 단축키 (Zine Viewer)

| 키 | 동작 |
|---|---|
| → / ↓ | 다음 페이지 |
| ← / ↑ | 이전 페이지 |
| ESC | 라이트박스 닫기 |

이미지 클릭 시 라이트박스로 확대 열람 가능.
