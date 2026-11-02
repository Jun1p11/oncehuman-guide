# 원스휴먼 공략

사이트: https://jun1p11.github.io/oncehuman-guide/

MkDocs Material로 만든 사이트입니다. `main`에 push하면 GitHub Actions가 자동으로 배포합니다 (1~2분).

## 진행 상황

### 완료

- [x] 사이트 디자인, 홈, 메뉴 구조
- [x] 무한한 꿈: 개요, 재화, 피라미드 구조, 진행 방식
- [x] 무한한 꿈 세부: 얕은 잠, 깊은 잠, 영면자, 실버게이트, 영역 현상, 회상 양 상점, 클리어 보상 표
- [x] 역행하는 별: 응축기, 중결런, 균열자
- [x] 추천 총기 페이지 (총기 · 추천 콘텐츠 · 시트 링크)
- [x] 파밍 루트: 테크런, 가구런 (추천 5곳)
- [x] 공식 이미지 4장 (무꿈 메인, 얕은 잠, 깊은 잠, 영면자)

### 이미지 추가 필요

이미지 파일을 아래 경로에 넣고, 페이지의 점선 박스(`<div class="oh-img-placeholder">…</div>`)를 이미지로 바꾸면 됩니다.

```markdown
![설명](../../images/endless-dream/파일명.png){ width="600" }
```

| 페이지 | 파일 경로 (`docs/` 기준) | 내용 |
|---|---|---|
| 무한한 꿈 | `images/endless-dream/awareness-clock.png` | 자각의 시계 |
| 무한한 꿈 | `images/endless-dream/pyramid-map.png` | 맵에서 영면자 클릭 화면 |
| 무한한 꿈 | 버프 아이콘 3개 (표의 `?` 칸) | 가하는 피해 증가 / 받는 피해 감소 / 쉴드 버블 |
| 무꿈 영역 현상 | `images/endless-dream/law-lightning.png` | 벼락 |
| 무꿈 영역 현상 | `images/endless-dream/law-explosion.png` | 폭탄 |
| 무꿈 영역 현상 | `images/endless-dream/law-darkness.png` | 암흑 |
| 회상 양 상점 | `images/endless-dream/sheep.png` | 회상 양 |
| 회상 양 상점 | `images/endless-dream/sheep-shop.png` | 상점 목록 전체 화면 |
| 회상 양 상점 | 아이템 아이콘 9개 (표의 `?` 칸) | 판매 아이템 |
| 테크런 · 가구런 | `images/farming/recommended-spots.png` | 추천 5곳 지도 (두 페이지 공용) |
| 테크런 | `images/farming/tech-run-map.png` | 테크런 동선 지도 |
| 가구런 | `images/farming/blackfell-route.png` | 블랙펠 동선 지도 |
| 가구런 | `images/farming/snow-route.png` | 설산 동선 지도 |

### 내용 작성 필요

- [ ] 테크런 · 가구런: 추천 5곳 메모 칸 (맵, 출발 워프 타워, 소요 시간)
- [ ] 영면자: 무킨 설명
- [ ] 실버게이트: 다키니 패턴
- [ ] 응축기: 페이즈별 공략
- [ ] 회상 양 상점: 아이템 가격
- [ ] 터치 오브 스카이, 군도 (지금은 "추후 작성"으로 숨김. 작성 후 `mkdocs.yml`의 `nav`에 다시 추가하고 `not_in_nav`에서 빼기, 홈 · 시나리오 카드 링크 복구)

## 새 PC 준비 (처음 한 번)

1. [Git](https://git-scm.com/download/win), [Python](https://www.python.org/downloads/) 설치 (Python 설치 시 "Add to PATH" 체크)
2. 터미널에서:

```bash
git clone https://github.com/Jun1p11/oncehuman-guide.git
cd oncehuman-guide
pip install -r requirements.txt
git config user.name Jun1p11
git config user.email talon000505@gmail.com
```

처음 push할 때 GitHub 로그인 창이 뜨면 **Jun1p11** 계정으로 로그인합니다.

## 작업할 때마다

```bash
git pull                          # 1. 시작 전: 최신 내용 받기
mkdocs serve                      # 2. 미리보기 → http://127.0.0.1:8000/oncehuman-guide/
# ... 파일 수정 ...
git add -A
git commit -m "변경 내용 요약"     # 3. 변경 저장
git push                          # 4. GitHub에 올리기 → 사이트 자동 반영
```

> 시작할 때 `pull`, 끝날 때 `push`. 두 PC에서 같은 파일을 동시에 고치지 않기.

## 폴더 구조

```
docs/
├─ index.md                  홈
├─ scenario/                 시나리오 (터치 오브 스카이, 무한한 꿈, 군도)
│  └─ endless-dream/         무한한 꿈 세부 공략
├─ trans/                    트랜스
│  └─ retrograde-star/       역행하는 별 세부 공략
├─ module/                   모듈
├─ images/                   이미지
└─ stylesheets/extra.css     디자인
mkdocs.yml                   사이트 설정, 메뉴(nav)
```

## 자주 쓰는 문법

| 하고 싶은 것 | 쓰는 법 |
|---|---|
| 다른 페이지 링크 | `[깊은 잠](deep-sleep.md)` |
| 페이지 안 특정 제목으로 링크 | `[무얕](shallow-sleep.md#무얕-무한-얕잠)` |
| 이미지 | `![설명](../../images/endless-dream/파일.jpg){ width="600" }` |
| 팁 박스 | `!!! tip "팁"` 다음 줄에 4칸 들여쓰고 내용 |
| 구글 시트 버튼 연결 | 페이지 맨 아래 `[sheet]: #` 의 `#` 자리에 주소 |

새 페이지를 만들면 `mkdocs.yml`의 `nav:`에도 추가해야 메뉴에 나옵니다.

배포 결과는 저장소 **Actions** 탭에서 확인합니다. 로그에 `[deploy] 배포 완료 → 주소`가 찍히면 성공입니다.
