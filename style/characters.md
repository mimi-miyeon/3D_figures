# 캐릭터 레지스트리

이 프로젝트에서 만들고 있는 캐릭터 목록이다.
캐릭터 이름이 요청에 등장하면 **이 파일을 먼저 읽는다.**

1. 상태가 `등록됨`이면 → 프롬프트 맨 앞에 `<<<element-id>>>` 토큰으로 바인딩 + 아래 영문 블록을 그대로 복사
2. 상태가 `확정`이면 → 확정 시트를 레퍼런스 이미지로 넣고 영문 블록을 그대로 복사
3. 상태가 `탐색중`이면 → **장면 프롬프트에 쓰지 않는다.** 먼저 확정할 것인지 사용자에게 확인
4. 목록에 없는 이름 → 생성하지 말고 먼저 확인

공용 시각 DNA는 `style/art-direction.md`, 생성 골격은 `templates/character-design.md`에 있다.
이 파일에는 **캐릭터마다 다른 부분만** 기록한다.

---

## 상태 정의

| 상태 | 의미 | 장면에 쓸 수 있나 |
|---|---|---|
| `탐색중` | 후보 생성 단계. 외형 미확정 | ❌ |
| `확정` | 외형 확정, 시트 확보. Element 미등록 | △ (레퍼런스 이미지로만) |
| `등록됨` | Element ID 발급 완료 | ✅ (바인딩) |

---

## 캐릭터 목록

| 이름 | 영문명 | 종 | 상태 | Element ID | 확정 시트 |
|------|--------|-----|------|-----------|----------|
| 찌부 | JJIBU | 강아지 puppy | `탐색중` | — | — |

> 🔖 **앵커 캐릭터 미정.** 첫 확정 캐릭터가 앵커가 되며, 이후 모든 캐릭터의 비율 기준이 된다.
> 앵커가 정해지면 이 줄에 표시하고 `templates/character-design.md`의 '앵커 파생 규칙'을 적용한다.

---

## 캐릭터별 슬롯 블록

`templates/character-design.md`의 슬롯에 그대로 넣는 값이다. **즉석에서 다시 쓰지 말고 복사한다.**

### 찌부 (JJIBU) — 강아지 · `탐색중`

- **1차 생성일:** 2026-08-14
- **비율/배경:** 배경 A (딥 블랙 + 화이트 글로우)
- **미확정 항목:** 최종 귀 각도, Element 등록 여부

프롬프트의 `{NAME}` 슬롯에는 `JJIBU`를 넣는다.

```
**Head**
The head is large and slightly wider than the body. Seen from the front, the outline
of the head is an OVAL — a wide egg shape resting with its broad end down, about
1.05 times wider than it is tall. The entire outline is one single continuous curve,
exactly like an egg or a balloon: every point along the edge is curving. The sides
bulge outward into full round cheeks and the bottom is a wide arc.
If you traced the head with one stroke it would be an ellipse, NOT a square with
rounded corners.

**Nose**
The nose is one small rounded black oval clay piece, slightly off-centre and
intentionally crooked. The nose is slightly tilted, and subtly uneven in shape.

**Ears**
The puppy has two long, floppy, rounded ears attached to the upper sides of the head,
drooping outward and downward. They are dark charcoal gray to nearly black.
The two ears are ALMOST THE SAME SIZE — the size ratio between them is about
**1 : 0.95**, a barely noticeable difference. They must clearly read as a matching
pair. Only their curve and hanging angle differ a little, giving a gentle handmade
feel — never a big or obvious size difference between the two ears.

**Tail**
A small dark charcoal-gray rounded tail is visible behind the character on the lower
right side of the body. The tail should also have a slightly irregular handmade shape
rather than a mathematically perfect sphere or capsule.

**Body**
The body wears NO clothing and NO accessories of any kind — completely plain and bare.
```

**Style keywords 추가:** `adorable puppy character`

**항상 적용되는 제약:**
- 주둥이(머즐)가 튀어나오면 안 됨 — 얼굴은 평평한 면. Negative: `snout, muzzle, protruding nose bridge`
- 귀는 반드시 아래로 처짐. 서 있는 귀 금지. Negative: `pointed ears, upright ears, standing ears`
- 몸통에 무늬·반점 금지 — 아이보리 단색. Negative: `spots, patches, fur markings, two-tone body`
- **머리가 각지면 안 됨** — 둥근 돔. 고질적 문제이므로 Head 블록 + Negative 이중 기재.
  Negative: `boxy head, square head, rounded-cube head, flat-sided head, angular jaw`

**Negative 추가:** `realistic dog, dog breed features, snout, muzzle, boxy head, square head, flat-sided head`

**시행착오:**

| 차수 | 도구 | 결과 | 원인 → 조치 |
|---|---|---|---|
| 1차 | (레퍼런스) | 기준 컷 | 스타일 원본 |
| 2차 | GPT | ❌ 4개 항목 어긋남 | 아래 참조 |
| 3차 | GPT | ❌ 질감·눈·얼굴 재발 + 귀 비대칭 과함 | 아래 참조 |

- **2차 (2026-08-14, GPT) 실패 4건**
  1. 질감이 건조·거침 → `art-direction.md` B 블록 전면 수정 (그레인 어휘 제거 + RENDER INTENT 추가)
  2. 눈이 정원·대칭 → `art-direction.md` E 블록 수정 (vertical oval 명시 + 좌/우 개별 지정)
  3. 실사 점토 사진처럼 나옴 → 1번과 동일 원인. Negative의 `perfectly smooth clay texture` 제거
  4. 얼굴이 각짐 (`rounded-trapezoid`를 둥근 정사각형으로 해석) → 위 Head 블록을 ROUNDED DOME으로 교체
- 1·2·3번은 **모든 캐릭터 공통 문제**라 `art-direction.md`에 반영했고, 4번만 찌부 개별 문제라 여기에 넣었다.

- **3차 (2026-08-14, GPT) — 같은 문제 재발 + 신규 1건**
  - 질감·눈·얼굴 3건이 그대로 재발. 서술을 강화했는데도 안 잡혔다.
    → 원인은 문장이 아니라 **GPT가 Negative Prompt를 무시(역효과)한다는 점**이었다.
      `art-direction.md` J 블록에 GPT 사용 금지 경고를 달고, GPT용 단축 골격을
      `templates/character-design.md`에 신설했다.
  - **부사가 아니라 숫자로 써야 한다**는 걸 확인했다. `noticeably`, `slightly`는
    무시되고 기본값(완벽한 대칭·정원)으로 처리된다. → 눈 `1.4배 세로 타원`,
    `1 : 0.92`, 얼굴 `1.05배 가로 타원`처럼 전부 수치화했다.
  - 신규: **귀 크기 차이가 과했다.** 2차의 `noticeably asymmetrical`이 이번엔 과잉
    반영됐다. → **1 : 0.95**로 못박고 "한 쌍으로 읽혀야 한다"를 명시.
  - 교훈: 비대칭 지시는 **방향(크다/작다)이 아니라 비율**로 준다. 방향만 주면
    무시되거나 과잉되거나 둘 중 하나다.

---

## 새 캐릭터 추가 절차

1. `templates/character-design.md` 골격으로 후보 생성 → 마음에 드는 컷 확보
2. 턴어라운드 시트로 검증 (같은 템플릿 4번 섹션)
3. 위 표에 행 추가, 상태 `확정`, 확정 시트 경로 기록
4. 이 섹션에 **슬롯 블록**을 복사 가능한 형태로 남긴다
5. Element 등록 후 ID를 채우고 상태를 `등록됨`으로 올린다
6. 생성 중 재수정 피드백이 나왔으면 **'항상 적용되는 제약'에 영구 반영**한다.
   모든 캐릭터에 해당하는 문제면 여기가 아니라 `style/art-direction.md`에 넣는다.
