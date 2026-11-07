# 강석 ♥ 지은 모바일 청첩장 (정적 HTML 버전)

`mobile/` 폴더 전체를 GitHub Pages, Vercel, Netlify 등 아무 정적 호스팅에 올리면 됩니다.
`index.html` 하나와 `assets/` 폴더만 있으면 동작합니다.

## 바꿔야 할 자리표시자

| 위치 | 내용 | 찾는 방법 |
|---|---|---|
| 마음 전하실 곳 | 은행명·계좌번호 6건 | `index.html`에서 `[은행명] [계좌번호]` 검색. 화면에 보이는 글자와 `data-copy` 속성 두 곳을 같이 바꿉니다 |
| 카카오톡 공유 | JavaScript 키 | `index.html` 하단 스크립트의 `KAKAO_JS_KEY = ''`. 비워두면 버튼이 숨겨지고 링크 복사만 보입니다 |
| 공유 썸네일 | `og:image` | 호스팅 주소가 정해지면 `<meta property="og:image">` 값을 절대 주소(https://…/assets/img/cover.jpg)로 바꿉니다 |

## 배경음악

`assets/audio/bgm.m4a`(AAC, 우선)와 `assets/audio/bgm.mp3`(대체)가 배경음악입니다. 오른쪽 아래 스피커 버튼으로 끄고 켭니다.
파일을 못 찾으면 버튼은 자동으로 숨겨집니다. 음원을 바꾸려면 같은 이름으로 덮어쓰면 됩니다.
변환 예: `ffmpeg -i 원본.mp4 -vn -c:a copy bgm.m4a`

- 브라우저 정책상 소리는 하객이 화면을 한 번 터치하거나 스크롤한 뒤에 시작됩니다. 그때 35% 음량으로 서서히 페이드인됩니다.
- 버튼으로 끄면 다시 켤 때까지 자동 재생하지 않습니다.
- 음원은 저작권이 해결된 파일을 쓰세요. 유튜브 추출은 약관 위반입니다. 음량은 `index.html`의 `TARGET = 0.35` 값으로 조절합니다.

## 사진 교체

- `assets/img/cover.jpg` 커버 (가로 사진, 4:5로 잘려 보임)
- `assets/img/g1.jpg` ~ `g5.jpg` 갤러리 슬라이드 (g1은 세로 사진)
- `assets/img/g6.jpg` 갤러리 아래 와이드 스트립
- `assets/img/map.png` 약도

파일 이름을 그대로 두고 덮어쓰면 HTML 수정 없이 바뀝니다. 가로 1,400px 정도면 충분합니다.

## 로컬 미리보기

프로젝트 루트에서:

```
powershell -ExecutionPolicy Bypass -File serve.ps1
```

그 다음 브라우저에서 http://localhost:8765 을 엽니다.
