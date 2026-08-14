# 템플릿: 3D 아이콘 (Icon)

"아이콘", "칩", "심볼" 류 요청 시 이 골격을 쓴다.
스타일 규칙은 `style/icon-style.md`, 재질·표면은 `style/art-direction.md`를 따른다.

- **현재 도구: GPT** → Negative Prompt를 쓰지 않는다. 아래 골격은 GPT용이다.
- 비율 **1:1** 고정

---

## 1. GPT용 골격

```
A cute minimalist 3D icon of {OBJECT}, in the same soft matte toy style as the JJIBU
character set.

SHAPE: {형태를 부위별로 서술 — 두께·비율은 숫자로}
It must read clearly as {OBJECT} ({핵심 식별 요소 2~3개 나열}).
The whole icon is built from thick, solid, rounded volumes — every part is a chunky
3D piece with fully rounded edges and corners. There are no thin lines and no flat
cut-out shapes; even the smallest detail is a plump little volume you could hold.
No part is thinner than one tenth of the icon's width.

SURFACE: one smooth, clean, velvety matte surface in bright ivory — a very light
creamy off-white close to white, warm but luminous, never beige or dull — like a
soft-touch matte vinyl designer toy, even and flawless everywhere.

COLOUR: mainly bright ivory, with {차콜 파츠} in soft charcoal gray{, and {세이지 파츠}
in muted sage green — a soft desaturated grey-green}.

FEEL: the forms are shaped a little unevenly by hand, with gently irregular curves
and a size ratio of about 1 : 0.95 between any paired parts, while the surface itself
stays perfectly smooth. The silhouette stays simple and instantly readable.

Single object centered in a square frame, filling about 65% of it, slight 3D tilt
rotated about 15 degrees, generous empty space around it, soft studio lighting from
the upper left, gentle soft drop shadow beneath it, clean stylized 3D render on a
soft bright pale warm gray background with a subtle radial gradient — the background
sits a shade deeper than the ivory body so the silhouette stays clearly separated.
```

> **배경은 오브젝트보다 한 톤 어둡게.** 순백 배경을 쓰면 밝은 아이보리 본체가 묻힌다.
> 다크 버전이 필요하면 `style/art-direction.md`의 배경 A 블록으로 교체한다.

> **서술 순서를 바꾸지 말 것.** 형태 → 표면 → 색 → 느낌 → 구도.
> 배경·구도를 앞으로 올리면 형태 묘사가 밀려 실루엣이 뭉개진다.

---

## 2. 슬롯

| 슬롯 | 채울 내용 | 예 (알림 벨) |
|---|---|---|
| `{OBJECT}` | 아이콘이 나타내는 사물 | `a bell` |
| `{SHAPE}` | 부위별 형태. 두께·비율 수치 포함 | `a plump dome-shaped body with a thick rounded top loop, a small round ball hanging just below the open bottom rim` |
| `{핵심 식별 요소}` | 이게 있어야 그 사물로 읽히는 것 | `dome body, top loop, small ball clapper` |
| `{차콜 파츠}` | 차콜로 칠할 부분 (20% 내외) | `the top loop and the clapper ball` |
| `{세이지 파츠}` | 세이지 그린 강조 1곳 (10% 이하, 생략 가능) | 생략 |

### 슬롯 작성 규칙

- **`{핵심 식별 요소}` 나열은 생략하지 않는다.** 이 괄호 하나가 형태 왜곡을 가장 크게 줄인다.
- **얇은 것은 두툼하게 번역한다.** 시계 바늘·와이파이 호·문서 줄 같은 요소는 그대로 쓰면 부러진 선으로 나온다.
  `thin needle` ❌ → `a short thick rounded bar` ✅
- 세이지 그린은 **쓸 자리가 명확할 때만.** 애매하면 슬롯째 삭제하고 아이보리+차콜로 간다.
- 요소가 3개를 넘으면 아이콘을 쪼갠다.

---

## 3. 세트로 만들 때 (★ 대부분의 경우)

아이콘은 세트로 쓰인다. **개별 완성도보다 세트 통일성이 중요하다.**

1. **앵커 아이콘 1개**를 먼저 확정한다. 가장 단순하고 관용적인 것으로 고른다 (예: 알림 벨, 검색 돋보기).
2. 앵커를 `assets/icons/final/`에 저장한다.
3. 2번째부터는 **앵커 이미지를 레퍼런스로 첨부**하고 아래 문장을 앞에 붙인다.
   ```
   Use the attached image as a STYLE, MATERIAL, SCALE and LIGHTING reference only.
   Keep the surface, colours, thickness, tilt angle, framing and lighting identical.
   The SHAPE is different: this icon is {OBJECT}.
   ```
4. 세트 고정값은 프롬프트마다 **똑같은 문장으로** 넣는다 (`65%`, `15 degrees`, `1/10 width`, `upper left`).
5. 다 만든 뒤 **한 줄로 나란히 놓고 본다.** 크기·기울기·두께가 어긋난 것만 재생성한다.

> 여러 개를 한 이미지에 한꺼번에 생성하면 통일성은 좋지만 낱장으로 쓰기 어렵고,
> 하나가 마음에 안 들면 전부 다시 뽑아야 한다. **낱장 생성 + 앵커 레퍼런스**를 권장한다.

---

## 4. 작성 요령

- **32px로 줄여서 읽히는지 본다.** 이게 유일한 합격 기준이다. 디테일이 예뻐도 실루엣이 안 읽히면 실패다.
- 기능 아이콘은 **관용적 형태를 따른다.** 종=알림, 돋보기=검색, 톱니=설정. 창의적으로 비틀면 인지가 무너진다.
- 형태가 안 잡히면 형용사를 바꾸지 말고 **`{핵심 식별 요소}` 나열을 늘린다.**
  (캐릭터 3차 실측: 형용사 교체는 두 번 연속 실패했다)
- 비율·두께·각도는 **숫자로.** `slightly`, `chunky` 같은 부사는 무시된다.
- 점토 질감이 건조하게 나오면 원인은 대개 `clay`라는 단어다. `matte vinyl`로 바꾼다.
- 확정된 아이콘은 `assets/icons/final/`에 `{이름}-v{차수}-{YYYYMMDD}.png`로 저장한다.

---

## 5. Higgsfield로 옮길 경우

- `style/art-direction.md` J 블록(공통 Negative)을 프롬프트 끝에 붙인다.
- 아이콘 전용 Negative를 추가한다:
  ```
  thin lines, wireframe, flat 2D icon, cut-out shape, sharp edges, pointed tips,
  cluttered detail, multiple objects, text, watermark
  ```
- 찌부 Element가 등록돼 있어도 **아이콘에는 바인딩하지 않는다.** 캐릭터 형태가 섞여 나온다.
