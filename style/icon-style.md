# 아이콘 스타일 규칙

찌부 캐릭터와 **같은 재질 DNA를 공유하는** 3D 아이콘 시스템이다.
캐릭터와 아이콘을 한 화면에 놓았을 때 하나의 세계로 읽히는 것이 목표다.

- 골격은 `templates/icon.md`
- 재질·표면·조명은 `style/art-direction.md`를 **상속**한다. 여기서는 **아이콘 고유 규칙만** 정의한다.
- 현재 사용 도구: **GPT** (Negative Prompt 사용 안 함 — `templates/character-design.md` 3번 참조)

---

## A. art-direction.md에서 상속하는 것

아래는 아이콘에도 **그대로 적용**된다. 여기 다시 쓰지 않는다.

| 블록 | 내용 |
|---|---|
| B. 재질·텍스처 | 매끄러운 벨벳 매트 표면, 소프트터치 매트 비닐 앵커, RENDER INTENT |
| F. 팔레트 | 밝은 아이보리 베이스 + 차콜 액센트 |
| H. 조명 | 소프트 스튜디오 라이팅, 접지 그림자 |
| H. 배경 | 배경 A(딥 블랙 + 글로우) 기본 |

---

## B. 아이콘 고유 규칙

### 1. 모든 것은 덩어리다 — 선이 없다 ★

이 시스템의 가장 중요한 아이콘 규칙이다.

```
The whole icon is built from thick, solid, rounded volumes — every part is a chunky
3D piece with fully rounded edges and corners. There are no thin lines, no wireframe
strokes, and no flat cut-out shapes; even the smallest detail is a plump little
volume you could pick up and hold.
```

- 선으로 그리는 아이콘(라인 아이콘)은 이 스타일에서 성립하지 않는다. 점토로 빚을 수 없는 형태이기 때문이다.
- 얇은 요소가 필요하면 **두툼한 막대**로 바꾼다. 최소 두께는 **아이콘 전체 폭의 1/10** 이상.
- 뾰족한 끝·날카로운 모서리 금지. 모든 끝은 둥글게 마감한다.

### 2. 비대칭은 캐릭터보다 약하게

캐릭터의 시그니처인 손맛은 아이콘에도 있지만 **강도를 낮춘다.** 기능 아이콘은 인지가 최우선이다.

| | 캐릭터 | 아이콘 |
|---|---|---|
| 형태 불균일 | 강하게 (`1 : 0.8`) | 약하게 (`1 : 0.95`) |
| 목적 | 손으로 빚은 개성 | 부드러운 손맛 + **즉시 읽히는 실루엣** |

```
The forms are shaped a little unevenly by hand, with gently irregular curves, while
the surface itself stays perfectly smooth. The silhouette stays simple and instantly
readable.
```

### 3. 실루엣 우선

- **32px로 줄여도 무엇인지 읽혀야 한다.** 디테일보다 외곽 형태가 우선이다.
- 한 아이콘에 개념 하나. 요소가 3개를 넘으면 쪼갠다.
- 오브젝트를 알아보게 하는 **핵심 식별 요소를 프롬프트에 괄호로 나열**하면 형태 왜곡이 크게 준다.
  예: `must read clearly as a bell (dome body, small ball clapper, flat base)`

---

## C. 팔레트 — 모노 + 액센트 1색

| 역할 | 색 | 사용 비중 | 용도 |
|---|---|---|---|
| 베이스 | 밝은 아이보리 `bright ivory` | **70% 이상** | 아이콘 본체 |
| 메인 액센트 | 차콜 그레이 `soft charcoal gray` | 20% 내외 | 포인트 파츠, 대비 |
| 서브 액센트 | **뮤트 세이지 그린** `muted sage green — a soft desaturated grey-green` | **10% 이하** | 강조 1곳 |

```
COLOUR: mainly bright ivory, with {차콜 파츠} in soft charcoal gray, and {세이지 파츠}
in muted sage green — a soft desaturated grey-green.
```

- **세이지 그린은 아이콘당 한 곳에만** 쓴다. 두 곳 이상 쓰면 세트가 산만해진다.
- 세이지 그린을 쓸 자리가 마땅치 않으면 **안 쓴다.** 억지로 넣지 않는다.
- 캐릭터에는 세이지 그린을 쓰지 않는다. **아이콘 전용 색**이다.

---

## D. 구도

```
Single object centered in a square frame, slight 3D tilt, generous empty space around
it, soft studio lighting from the upper left, gentle contact shadow.
```

- 비율 **1:1** 고정
- 오브젝트가 프레임의 **60~70%**를 차지하게. 꽉 채우면 세트로 늘어놨을 때 답답하다
- 정면 정투영이 아니라 **살짝 기울인 3D 시점** — 두께가 보여야 점토 덩어리로 읽힌다
- 기울기 각도는 **세트 전체가 같아야 한다** (E 참조)

---

## E. 세트 일관성 (★ 아이콘의 핵심 문제)

아이콘은 **혼자 쓰이지 않고 세트로 쓰인다.** 개별 완성도보다 세트 통일성이 중요하다.
캐릭터의 '앵커' 개념과 같다 — **앵커 아이콘을 먼저 확정하고 나머지를 파생시킨다.**

세트 전체에서 고정해야 하는 값:

| 항목 | 지정 방식 |
|---|---|
| 프레임 점유율 | `fills about 65% of the square frame` |
| 3D 기울기 | `slight 3D tilt, rotated about 15 degrees` |
| 최소 두께 | `no part thinner than 1/10 of the icon's width` |
| 조명 방향 | `soft key light from the upper left` |
| 액센트 비중 | 차콜 20% / 세이지 10% 이하 |

- 2번째 아이콘부터는 **앵커 아이콘 이미지를 레퍼런스로 첨부**하고 형태만 바꾼다.
- 확정 아이콘은 `assets/icons/final/`에 저장한다.

---

## F. 용도별 차이

| | 서비스·기능 아이콘 | 카테고리·콘텐츠 아이콘 |
|---|---|---|
| 요소 수 | **1~2개** | 2~3개 |
| 소품 | 없음 | 허용 |
| 비대칭 | 최소 | 조금 더 허용 |
| 판단 기준 | 32px에서 읽히는가 | 주제가 전달되는가 |
| 예 | 알림, 검색, 설정, 저장 | 학습, 커뮤니티, 리포트 |

- 기능 아이콘은 **관용적 형태를 따른다.** 종=알림, 돋보기=검색. 창의적으로 비틀지 않는다.
- 카테고리 아이콘은 오브젝트 조합이 가능하지만, 조합해도 **덩어리 3개 이내**.

---

## G. 이 파일을 고치는 규칙

1. 아이콘에만 해당하는 문제 → 여기에 반영
2. 캐릭터에도 해당하는 재질·표면 문제 → `style/art-direction.md`에 반영
3. 특정 아이콘 하나의 문제 → 해당 아이콘 로그에만 기록
