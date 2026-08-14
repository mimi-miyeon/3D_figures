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
Soft matte BRIGHT IVORY — a very light, clean, creamy off-white that sits close to
pure white, warm but luminous, never beige, tan, or dull — with a SMOOTH, VELVETY,
evenly hand-smoothed surface.
The surface is soft and satin-matte, polished smooth all over by hand, with a clean
uniform finish. Surface variation is extremely subtle — only the faintest softness in
the larger forms — and NEVER reads as visible grain or texture detail.
The clay is smooth and slightly waxy: NOT dry, NOT powdery, NOT chalky, NOT porous.
There are no visible pores, no speckles, no cracks, no crumbs, no sand-like grain,
no fingerprints, and no rough patches anywhere.
SURFACE ANCHOR: the finish is that of a SOFT-TOUCH MATTE VINYL DESIGNER TOY — an
even, flawless, factory-clean matte skin. Think smooth painted vinyl, not raw clay.
The material has low reflectivity with a soft diffuse light response. Highlights are
broad, soft, and subdued — a gentle satin sheen, not a hard specular glint.
EVERY component — the ivory base, the charcoal-gray parts, and any accent-colour
piece — shares the exact same smooth velvety surface.

RENDER INTENT: This is a CLEAN, STYLIZED 3D CHARACTER RENDER of an idealized soft clay
toy — NOT a photograph of a real clay sculpture. The surface stays idealized and
digitally clean while the FORMS stay soft and handmade. Do not add photographic
material realism, scanned clay detail, or documentary surface texture.
No glossy coating, no polished ceramic, no rubber, no hard plastic, no metallic
reflection, no glass.
```

> ⚠️ **실측 (2026-08-14, 찌부 2차):** 이전 버전은 `powdery / porous / microscopic pores /
> faint grain / fingerprints` + `must feel like real handcrafted modelling clay`
> 조합이었고, 그 결과 **바짝 마른 실사 점토 사진**이 나왔다. Negative에 있던
> `perfectly smooth clay texture`가 매끄러운 표면을 오히려 차단하고 있었다.
> → 그레인 계열 어휘를 전부 제거하고, "실제 점토"가 아니라 **"양식화된 3D 렌더"**임을
> 명시(RENDER INTENT)하는 방향으로 뒤집었다.

---

## C. 핸드메이드 불완전성 (Handmade Imperfection) — ★ 시그니처, 항상 포함

이 블록이 이 프로젝트를 다른 3D 캐릭터와 구분 짓는 핵심이다. **절대 빼지 않는다.**

```
The character should look like a person shaped it by hand, placing each tiny clay
feature individually, so the eyes, nose, and ears are visibly misplaced, uneven,
crooked, and asymmetrical. This handmade imperfection is a key part of the design.

CRITICAL — WHERE the imperfection lives: the imperfection is ONLY in the SHAPE,
SIZE, ANGLE, and PLACEMENT of the individual parts. It is NEVER in the surface
quality. The surface itself stays perfectly smooth, clean, and velvety everywhere.
Wonky forms, flawless finish.
```

> ⚠️ **이 구분이 이 프로젝트에서 가장 중요한 문장이다.**
> "손으로 만든 느낌"을 표면 질감으로 해석하면 마른 실사 점토가 나온다 (2026-08-14 실측).
> 손맛은 **형태의 어긋남**으로만 표현하고, **표면은 완벽하게 매끄럽게** 유지한다.

---

## D. 비율 · 몸통 · 팔다리 (Proportion & Body) — 항상 포함

```
**Proportion:** The character has an oversized rounded head and a small compact body
with simple chibi proportions. The head is large and slightly wider than the body.
The body is short and plump with tiny stubby legs and short stubby arms.

**Body:** The body is a small plump rounded form in plain bright ivory, flowing out
of the head with almost no neck. The arms are very short, soft, rounded stubs
emerging from the sides of the body.

**One continuous surface — no hard edges:** the arms, the torso, and the legs are all
ONE single soft continuous form. Where an arm meets the torso there is only a very
soft, shallow crease — exactly the same gentle way the two legs blend into the lower
body. Every transition is a smooth gradual swell of the same surface, as if the whole
figure were pinched out of one lump. There are no hard seams, no sharp outlines, no
visible joints, and no separately-attached-looking limbs anywhere.

**Legs:** The legs are short, thick, and rounded, divided only by a shallow soft
notch at the bottom, giving the character a stable cute standing pose. The two legs
have subtle differences in width, curvature, or positioning.
```

> ⚠️ **팔·몸통 경계 (2026-08-14 반영):** 팔이 몸통에 따로 붙인 것처럼 뚜렷한 외곽선으로
> 나오는 문제가 있었다. **다리처럼** 얕은 주름 하나로만 구분되게, 전체가 한 덩어리에서
> 빚어져 나온 형태로 지시한다.

> ⚠️ **비율은 텍스트만으로 잡히지 않는다.** 수치를 넣어도 모델이 몸통을 늘린다.
> 2번째 캐릭터부터는 **앵커 캐릭터의 Element를 바인딩**해 비율을 상속시킨다.
> 자세한 건 `templates/character-design.md`의 '앵커 파생 규칙' 참조.

---

## E. 얼굴 (Face) — 항상 포함

```
**Face:** No mouth, eyebrows, eyelashes, or other facial details. The facial
expression is calm, innocent, gentle, and slightly expressionless, with a charming
handmade imperfection.

**Eyes:** Two small solid charcoal-black eyes, matte and softly domed off the face
like little pieces pressed on by hand.
Each eye is a small VERTICAL OVAL — an upright egg shape about **1.25 times taller
than it is wide**, slightly fuller toward the bottom. It is an oval, not a circle.
They are SMALL against the huge head — each eye is roughly **one twelfth of the
head's width** — and set WIDE APART, sitting a little above the middle of the face.
The two eyes differ slightly but visibly:
- Size ratio between them is about **1 : 0.92**.
- The smaller eye sits about **0.2 eye-heights higher** on the face.
- Each eye is tilted a few degrees at a DIFFERENT angle — they are not parallel.
- The distance from each eye to the centre line of the face is slightly unequal.
They read as two separate oval pieces placed by hand in slightly wrong spots — never
as beads, buttons, flat round dots, or perfect circles.
```

> **수치로 쓴다.** `slightly`, `subtle`, `noticeably` 같은 부사는 모델이 무시하고
> 기본값(= 완벽한 대칭 정원)으로 처리한다 (2026-08-14, 2·3차 연속 실측).
> 비율·배수·각도를 **숫자로** 지정해야 반영된다.
> 위 `1.4배` / `1 : 0.92` / `0.2 eye-heights`는 조정 가능한 값이다. 결과를 보고 튜닝할 것.

- **입·눈썹·속눈썹은 어떤 캐릭터에도 넣지 않는다.** 이 캐릭터군의 고정 규칙이다.
- 코는 종에 따라 형태가 달라지므로 `templates/character-design.md`의 `{NOSE}` 슬롯에서 정의한다.

---

## F. 팔레트

| 역할 | 색 | 사용처 |
|---|---|---|
| 베이스 | **밝은 아이보리** `bright ivory / very light creamy off-white` — 화이트에 가깝게, 베이지·탠 금지 | 머리·몸통·팔·다리 (전 캐릭터 공통) |
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
minimalist 3D character, cute collectible toy, stylized clay-toy render, Japanese
character aesthetic, chibi proportions, soft rounded forms, smooth matte clay,
velvety satin-matte surface, clean idealized surface, soft studio lighting, premium
product render, simple silhouette, handcrafted imperfection, intentional asymmetry,
wonky facial features, uneven oval eyes, crooked nose, irregular clay pieces, organic
shapes, charmingly imperfect forms, flawlessly smooth finish.
```

> `natural fingerprints on the clay texture` / `tactile clay texture` / `soft clay sculpture`를
> 제거했다 (2026-08-14) — 전부 표면 그레인을 유발했다.
> 손맛 키워드는 **형태 계열만** 남긴다 (`wonky`, `uneven`, `crooked`, `irregular`).

---

## J. 공통 Negative

> 🚫 **GPT(ChatGPT 이미지 생성)에서는 이 블록을 쓰지 않는다.**
> GPT는 Negative Prompt를 지원하지 않는다. 금지어를 나열하면 오히려 그 단어를
> 끌어다 쓴다 — `dry clay, cracked, porous`를 적을수록 건조한 질감이 강해진다 (3차 실측).
> GPT용 운용법은 `templates/character-design.md`의 '도구별 프롬프트 운용' 참조.
>
> ✅ 아래 블록은 **Higgsfield / Stable Diffusion 계열** 전용이다.

```
realistic animal, photorealistic animal, detailed fur, hairy texture, fluffy fur,
sharp edges, realistic anatomy, open mouth, smile, teeth, tongue, eyebrows, eyelashes,
clothing, accessories, collar, complex patterns, excessive facial details, human
features, aggressive expression, dramatic pose, complex background, scenery, props,
text, letters, logo, watermark, outline, glossy plastic, metallic material, glass,
excessive reflections, perfectly rounded outline, perfect handmade sculpture, regular
clay pieces, perfect facial symmetry, perfectly identical eyes, perfectly aligned
eyes, perfectly centred nose, perfectly geometric eyes, polished black beads, plastic
eyes, glossy buttons, manufactured-looking facial pieces, computer-perfect geometry,
sterile perfection, mirrored features, symmetrical ears, symmetrical arms,
symmetrical legs,

dry clay, cracked clay, chalky surface, powdery surface, porous surface, visible clay
pores, speckled texture, coarse grain, sandy texture, gritty surface, rough surface,
crumbly clay, unfinished clay, visible fingerprints, photorealistic clay photograph,
photograph of a real clay sculpture, scanned clay, documentary material realism,
hyperreal material detail,

round eyes, circular eyes, perfectly round dot eyes, bead eyes, identical eyes,
evenly placed eyes, level eyes, parallel eyes, symmetrical eye placement,

boxy head, square head, rounded-cube head, rounded-square head, flat-sided head,
angular jaw, straight jawline, corners on the head.
```

> ⚠️ Negative에서 **`perfectly smooth clay texture`를 제거했다** (2026-08-14).
> 이 항목이 매끄러운 표면을 차단해 마른 점토를 유발했다. 다시 넣지 말 것.
> 마찬가지로 `flawless surfaces`도 제거했다 — 표면은 flawless여야 한다.

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
