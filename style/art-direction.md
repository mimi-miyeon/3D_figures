# 아트 디렉션 — 공용 시각 DNA

이 프로젝트의 **모든** 캐릭터가 공유하는 시각 규칙이다.
새 캐릭터를 만들 때 아래 영문 블록을 **그대로 복사**해서 프롬프트에 넣는다. **즉석에서 다시 쓰지 않는다.**
캐릭터마다 달라지는 부분(종·귀·코·꼬리·액세서리)은 `templates/character-design.md`의 슬롯에서 채운다.

- **기준 레퍼런스:** 강아지 캐릭터 1차 (2026-08-14). 이 결과물이 스타일 원본이다.
- 이 파일을 고치면 **이미 확정된 캐릭터와 어긋난다.** 수정 전 `style/characters.md`의 확정 캐릭터 목록을 확인할 것.

---

## A. 한 줄 정체성

> 손으로 빚은 매트한 아이보리 점토 인형. 일본식 캐릭터 토이 감성의 치비 비율.
> **완벽하지 않은 것이 이 캐릭터군의 정체성이다** — 눈·코·귀가 미묘하게 어긋나 있다.

---

## B. 재질 · 텍스처 (Material & Texture) — 항상 포함

```
Soft matte ivory-white clay with a fine, natural handcrafted clay grain.
The surface is softly hand-smoothed, velvety, slightly powdery, and gently porous,
with very fine microscopic pores and subtle organic surface variations. Include tiny
uneven areas, faint grain, soft dents, barely visible fingerprints, and slight
variations in smoothness caused by being shaped and smoothed by hand.
The texture should be delicate and refined rather than rough or gritty. It should
remain mostly smooth and soft, with the handmade texture becoming visible mainly in
the subtle variations across the surface.
The material has very low reflectivity and soft diffuse light response. Highlights
are broad, soft, and subdued.
EVERY clay component — the ivory base, the charcoal-gray parts, and any accent-colour
piece — shares the exact same tactile handmade clay texture.
The material must feel like real handcrafted modelling clay or fine sculpting clay,
not digitally generated plastic.
No glossy coating, no polished ceramic, no rubber, no plastic, no metallic reflection,
no glass, no excessive roughness, no sand-like grain, no cracks, no dust.
```

---

## C. 핸드메이드 불완전성 (Handmade Imperfection) — ★ 시그니처, 항상 포함

이 블록이 이 프로젝트를 다른 3D 캐릭터와 구분 짓는 핵심이다. **절대 빼지 않는다.**

```
The character should look like a person made the face by hand, placing each tiny clay
feature individually, so the eyes and nose are slightly misplaced, uneven, crooked,
and imperfect. This handmade imperfection is a key part of the character design.
```

---

## D. 비율 · 몸통 · 팔다리 (Proportion & Body) — 항상 포함

```
**Proportion:** The character has an oversized rounded head and a small compact body
with simple chibi proportions. The head is large and slightly wider than the body.
The body is short and plump with tiny stubby legs and short stubby arms.

**Body:** The body is completely plain ivory-white. The arms are very short and
rounded, naturally protruding from the sides of the body. The arms have subtle
differences in size, angle, and shape, avoiding perfect bilateral symmetry.

**Legs:** The legs are short, thick, rounded, and slightly separated, giving the
character a stable cute standing pose. The two legs have subtle differences in width,
curvature, or positioning, reinforcing the feeling of a handmade clay figure.
```

> ⚠️ **비율은 텍스트만으로 잡히지 않는다.** 수치를 넣어도 모델이 몸통을 늘린다.
> 2번째 캐릭터부터는 **앵커 캐릭터의 Element를 바인딩**해 비율을 상속시킨다.
> 자세한 건 `templates/character-design.md`의 '앵커 파생 규칙' 참조.

---

## E. 얼굴 (Face) — 항상 포함

```
**Face:** No mouth, eyebrows, eyelashes, or other facial details. The facial
expression is calm, innocent, gentle, and slightly expressionless, with a charming
handmade imperfection.

**Eyes:** Two small solid charcoal-black rounded clay eyes. One eye is slightly
larger or smaller than the other, with subtle differences in shape, angle, and
position. Each eye is slightly tilted and sits at a different angle. Their vertical
positions differ slightly, and the distance between each eye and the centre of the
face is not perfectly equal. They MUST NOT look like smooth plastic beads, flat clay,
polished buttons, or perfectly computer-generated geometric shapes.
```

- **입·눈썹·속눈썹은 어떤 캐릭터에도 넣지 않는다.** 이 캐릭터군의 고정 규칙이다.
- 코는 종에 따라 형태가 달라지므로 `templates/character-design.md`의 `{NOSE}` 슬롯에서 정의한다.

---

## F. 팔레트

| 역할 | 색 | 사용처 |
|---|---|---|
| 베이스 | 아이보리 화이트 `ivory-white` | 머리·몸통·팔·다리 (전 캐릭터 공통) |
| 메인 액센트 | 차콜 그레이~거의 블랙 `dark charcoal gray to nearly black` | 눈·코·귀·꼬리 등 포인트 파츠 |
| 서브 액센트 | 뮤트 세이지 그린 `muted sage green` | **아직 미사용** — 소품·액세서리용으로 예약 |

- 베이스 아이보리는 **전 캐릭터 고정**이다. 몸 색으로 캐릭터를 구분하지 않는다.
- 캐릭터 구분은 **실루엣(귀·꼬리·머리 형태)**으로 한다. 색을 바꾸면 시리즈 통일감이 깨진다.
- 새 액센트 색이 필요하면 이 표에 먼저 추가하고 쓴다.

---

## G. 포즈 · 카메라 · 비율

```
**Pose:** Front-facing character, standing upright, centered composition, full body
visible, overall silhouette simple and cute but not perfectly symmetrical, simple
neutral pose.
```

| 용도 | 비율 | 비고 |
|---|---|---|
| **전신 정면 (기본 · Element 등록용)** | **3:4** | 캐릭터 확정용 기본 컷 |
| 턴어라운드 시트 (정면/측면/후면) | 16:9 | 확정 직전 검증용 |
| 표정 · 포즈 시트 | 4:3 | 확정 이후 |
| 썸네일 · 배너 | 16:9 | |
| 아이콘 | 1:1 | |

---

## H. 조명 · 배경

```
**Light:** Soft studio lighting, subtle ambient occlusion, gentle contact shadow
beneath the feet, soft realistic shadows, premium 3D product render, Cinema 4D /
Octane Render aesthetic, physically based rendering, smooth clay material, soft
global illumination, high-quality 3D collectible figure.
```

배경은 **용도에 따라 둘 중 하나를 골라 명시**한다.

**배경 A — 쇼케이스용 (1차 결과물이 이것)**
```
Deep black background with a soft white ambient glow radiating behind the character
and a gentle contact shadow beneath the feet. No environment, no props, no text,
no logo, no outline.
```

**배경 B — Element 등록 / 시트용 (권장)**
```
Plain flat neutral off-white background, evenly lit, no gradient, no vignette, no
glow, no environment, no props, no text, no logo, no outline. The character is fully
isolated with only a soft contact shadow beneath the feet.
```

> ⚠️ **1차 프롬프트의 `Clean isolated background`는 배경 A(검정+글로우)로 나왔다.**
> "isolated"만으로는 배경색이 통제되지 않는다. 원하는 쪽을 위 블록 그대로 명시할 것.
> Element 등록 레퍼런스는 배경 A의 글로우가 실루엣에 섞이므로 **배경 B를 쓴다.**

---

## I. 스타일 키워드 (프롬프트 말미에 항상 포함)

```
minimalist 3D character, cute collectible toy, soft clay sculpture, Japanese character
aesthetic, chibi proportions, rounded forms, matte clay, soft studio lighting, premium
product render, simple silhouette, handmade clay figure, natural fingerprints on the
clay texture, handcrafted imperfection, intentional asymmetry, wonky facial features,
uneven eyes, crooked nose, irregular clay pieces, organic shapes, imperfect handmade
sculpture, charmingly imperfect, tactile clay texture.
```

---

## J. 공통 Negative (항상 포함)

```
realistic animal, photorealistic animal, detailed fur, hairy texture, fluffy fur,
sharp edges, realistic anatomy, open mouth, smile, teeth, tongue, eyebrows, eyelashes,
clothing, accessories, collar, complex patterns, excessive facial details, human
features, aggressive expression, dramatic pose, complex background, scenery, props,
text, letters, logo, watermark, outline, glossy plastic, metallic material, glass,
excessive reflections, perfectly rounded outline, perfect handmade sculpture, regular
clay pieces, perfectly smooth clay texture, perfect facial symmetry, perfectly
identical eyes, perfectly aligned eyes, perfectly centred nose, perfectly geometric
eyes, perfectly smooth facial features, polished black beads, plastic eyes, glossy
buttons, manufactured-looking facial pieces, computer-perfect geometry, sterile
perfection, mirrored features, symmetrical ears, symmetrical arms, symmetrical legs,
flawless surfaces.
```

캐릭터별 추가 Negative는 `style/characters.md`의 각 캐릭터 항목에 쌓는다.

---

## K. 이 파일을 고치는 규칙

1. 생성 결과가 잘못 나와 고쳤고, 그 원인이 **모든 캐릭터에 해당**하면 → 여기에 반영한다.
2. **특정 캐릭터만의 문제**면 → `style/characters.md`의 해당 캐릭터 제약 블록에 넣는다. 여기 넣지 않는다.
3. 반영했으면 사용자에게 "○○ 파일에 반영했다"고 알린다.
4. 확정 캐릭터가 이미 있는 상태에서 A~E 블록을 고치면 기존 캐릭터와 어긋난다. 고치기 전에 영향 범위를 먼저 확인할 것.

---

## L. 1차 프롬프트에서 손본 곳 (기록)

원본 프롬프트를 분해하면서 아래를 정리했다. 결과에 영향을 줄 만한 변경은 없다고 판단했으나, 재현이 어긋나면 이 목록부터 되돌려 볼 것.

| 원본 | 변경 | 이유 |
|---|---|---|
| `let characterName;` / `[characterName;]` | 삭제, `{NAME}` 슬롯으로 통일 | JS 문법 잔재, 대괄호·세미콜론 표기 불일치 |
| `including ivory, charcoal gray, and muted sage green pieces` | `the ivory base, the charcoal-gray parts, and any accent-colour piece` | 세이지 그린은 이 캐릭터에 없는 색. 하드코딩 대신 일반화 |
| `Each eyes are slightly tilted, they sits at...` | `Each eye is slightly tilted and sits at...` | 문법 |
| `natural fingure print` | `natural fingerprints` | 오타 |
| Eyes 블록에 색 지정 없음 | `Two small solid charcoal-black rounded clay eyes.` 추가 | 원본은 눈 색을 명시하지 않았음. **차콜 블랙으로 확정 (2026-08-14 사용자 확인).** |
| `perfect rounded shape of outline` (Negative) | `perfectly rounded outline` | 표현 정리 |
| `***Body***` / `**Body**` 혼용 | `**Body**`로 통일 | 마크다운 강조 표기 일관성 |
