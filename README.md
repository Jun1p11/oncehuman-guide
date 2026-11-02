# 원스휴먼 공략

사이트: https://jun1p11.github.io/oncehuman-guide/

MkDocs Material로 만든 사이트입니다. `main`에 push하면 GitHub Actions가 자동으로 배포합니다 (1~2분).

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
