# 이미지 자산 (assets)

생성한 캐릭터 이미지를 보관하는 곳이다.
**확정 컷은 Element 등록과 재생성의 유일한 기준**이므로, 반드시 원본 해상도로 저장한다.

---

## 폴더 구조

```
assets/
  characters/
    {영문명 소문자}/
      final/        # 확정 컷 — 레퍼런스·Element 등록에 쓰는 것만
      candidates/   # 후보·미채택 컷
  icons/
    final/          # 확정 아이콘 — 앵커 아이콘 포함
    candidates/     # 후보·미채택
```

- `final/`에는 **확정된 것만** 넣는다. 여기 있는 이미지는 그대로 레퍼런스로 사용된다.
- `candidates/`는 버리지 말 것. 미채택 컷은 "무엇이 안 됐는지"의 기록이라 재생성 때 도움이 된다.
- 캐릭터를 새로 만들면 `characters/{영문명}/final`, `.../candidates` 두 폴더를 만든다.

---

## 파일 이름 규칙

```
{영문명소문자}-{용도}-v{차수}-{YYYYMMDD}.png
```

| 용도 | 의미 | 비율 |
|---|---|---|
| `front` | 전신 정면 (기본 컷) | 3:4 |
| `turnaround` | 정면·측면·후면 시트 | 16:9 |
| `expression` | 표정 시트 | 4:3 |
| `pose` | 포즈 시트 | 4:3 |
| `icon` | 아이콘용 크롭 | 1:1 |

예시:
```
jjibu-front-v1-20260814.png
jjibu-turnaround-v1-20260815.png
```

- **원본 해상도 그대로 저장한다.** 리사이즈·재압축한 이미지를 레퍼런스로 넣으면 재질과 비대칭 디테일이 뭉개진다.
- 같은 용도를 다시 뽑으면 v 차수를 올린다. 이전 버전을 덮어쓰지 않는다.

---

## 등록 절차

1. 확정 컷을 `final/`에 위 규칙대로 저장
2. `style/characters.md`의 **확정 시트** 열에 경로를 적는다
   ```
   | 찌부 | JJIBU | 강아지 puppy | `확정` | — | `assets/characters/jjibu/final/jjibu-front-v1-20260814.png` |
   ```
3. Element 등록 후 ID를 채우고 상태를 `등록됨`으로 올린다
