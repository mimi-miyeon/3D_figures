# 템플릿: 캐릭터 생성 (Character Design)

**새 캐릭터를 만들어내는** 프롬프트 골격이다.
이미 확정된 캐릭터를 장면에 등장시킬 때는 이 파일이 아니라 `templates/character-scene.md`를 쓴다.

- `{...}` 슬롯만 채운다. 대문자 영문 블록은 `style/art-direction.md`에서 **그대로 복사**한다.
- 실전 검증: 강아지 캐릭터 1차 (2026-08-14)

---

## 1. 프롬프트 골격

```
# {NAME} — {SPECIES} character

**Style**
A cute minimalist 3D toy-figurine {SPECIES} character, designed in a soft Japanese
character-toy aesthetic.

**Material & Texture**
{art-direction B 블록 그대로 복사}

**Important**
{art-direction C 블록 그대로 복사}

**Proportion**
{art-direction D 블록의 Proportion 문단 그대로 복사}

**Head**
The head is large and slightly wider than the body, with a soft {HEAD_SHAPE} shape.

**Face**
{art-direction E 블록의 Face 문단 그대로 복사}

**Eyes**
{art-direction E 블록의 Eyes 문단 그대로 복사}

**Nose**
{NOSE}

**Ears**
{EARS}

**Body**
{art-direction D 블록의 Body 문단 그대로 복사}
{ACCESSORY}

**Legs**
{art-direction D 블록의 Legs 문단 그대로 복사}

**{EXTRA_PART_NAME}**
{EXTRA_PART}

**Pose**
{art-direction G 블록 그대로 복사}

**Light**
{art-direction H 블록의 Light 그대로 복사}

**Background**
{art-direction H 블록의 배경 A 또는 B 중 택1, 그대로 복사}

**Style keywords**
{art-direction I 블록 그대로 복사} + {SPECIES_KEYWORDS}

**Negative Prompt**
{art-direction J 공통 Negative 그대로 복사}, {SPECIES_NEGATIVE}
```

> **서술 순서를 바꾸지 말 것.** 재질 → 불완전성 → 비율 → 부위 → 포즈 → 조명 → 배경 순이다.
> 배경·조명을 앞으로 올리면 캐릭터 묘사가 밀려서 재질과 얼굴 파츠가 뭉개진다.

---

## 2. 캐릭터별 슬롯

| 슬롯 | 채울 내용 | 강아지 1차 실제 값 |
|---|---|---|
| `{NAME}` | 캐릭터 이름 (영문 대문자) | *(미정)* |
| `{SPECIES}` | 종 | `puppy` |
| `{HEAD_SHAPE}` | 머리 실루엣 | `rounded-trapezoid` |
| `{NOSE}` | 코 형태·색·비대칭 | 아래 참조 |
| `{EARS}` | 귀 형태·색·비대칭 — **캐릭터 구분의 1순위** | 아래 참조 |
| `{EXTRA_PART}` | 꼬리·뿔·볏 등 종 고유 파츠 | 꼬리 (아래 참조) |
| `{ACCESSORY}` | 액세서리. 없으면 아래 '없음' 문장 | 없음 |
| `{SPECIES_KEYWORDS}` | 종 관련 키워드 | `adorable puppy character` |
| `{SPECIES_NEGATIVE}` | 종 고유 Negative | `realistic dog, dog breed features, snout, muzzle` |

### 슬롯 작성 규칙

**`{EARS}` — 캐릭터를 구분하는 가장 강한 신호.** 몸 색·비율은 전 캐릭터 공통이므로, 실루엣에서 종을 읽히게 하는 건 귀와 `{EXTRA_PART}`다. 형태·길이·방향·색을 구체적으로 쓰고 **비대칭 문장을 반드시 붙인다.**

**`{ACCESSORY}` — 없을 때도 문장을 넣는다.** 비워두면 모델이 목줄이나 리본을 임의로 붙인다.
```
The body wears NO clothing and NO accessories of any kind — completely plain and bare.
```

**`{EXTRA_PART}`가 없는 종**(예: 꼬리 없는 캐릭터)이면 섹션 자체를 지우지 말고 없다고 명시한다.
```
**Tail**
The character has NO tail. The back and lower body are completely plain.
```

### 강아지 1차 슬롯 원문 (참고용)

```
{NOSE}
The nose is one small rounded black oval clay piece, slightly off-centre and
intentionally crooked. The nose is slightly tilted, and subtly uneven in shape.

{EARS}
The puppy has two long, floppy ears attached to the upper sides of the head. The ears
are rounded and organically shaped, noticeably asymmetrical, with slightly different
sizes, thicknesses, curves, and angles. Each ear should have its own naturally
irregular handmade shape. They droop outward and downward. The ears are dark charcoal
gray to nearly black.

{EXTRA_PART} — Tail
A small dark charcoal-gray rounded tail is visible behind the character on the lower
right side of the body. The tail should also have a slightly irregular handmade shape
rather than a mathematically perfect sphere or capsule.
```

---

## 3. 앵커 파생 규칙 (★ 2번째 캐릭터부터)

**1번 캐릭터(앵커)가 나머지 전부의 기준자가 된다.**

1. **앵커 캐릭터 1명을 만족할 때까지 뽑는다.** 여기서 아끼면 전체가 흔들린다.
2. 앵커를 Higgsfield **Element로 등록**하고 `style/characters.md`에 ID를 기록한다.
3. **2번째부터는 앵커 Element를 바인딩**하고 `{EARS}`·`{EXTRA_PART}`·`{HEAD_SHAPE}`만 교체한다.
   ```
   <<<앵커-element-id>>> # {NAME} — {SPECIES}

   Use the bound character ONLY as a reference for the clay material, the body
   proportions, the eye style, and the overall handmade sculpting quality.
   This is a DIFFERENT character: a {SPECIES}, not a {앵커 SPECIES}.
   Keep the material, proportions, and face style identical; change only the ears,
   the head silhouette, and {EXTRA_PART_NAME}.
   ```
   Negative 추가: `{앵커 SPECIES} ears, {앵커 SPECIES} features, copy of the reference character`
4. 그래도 앵커 캐릭터가 그대로 복제돼 나오면, 바인딩을 빼고 **레퍼런스 이미지로만** 넣은 뒤 스타일은 텍스트로 강제한다.

> 3~4명을 각자 따로 만들어놓고 나중에 나란히 세우면 키·머리 크기가 제각각이 된다. 그 시점엔 되돌릴 방법이 없다.

---

## 4. 확정 전 검증 시트

전신 정면 컷이 마음에 들어도 **바로 확정하지 말고** 아래 둘을 뽑아 본다. 여기서 무너지면 장면에서도 무너진다.

**턴어라운드 시트 (16:9)**
```
Character turnaround sheet of {NAME}: the SAME single character shown three times in
a row on one flat neutral off-white background — front view on the left, exact side
profile in the middle, back view on the right. Identical scale, identical height,
identical eye level across all three. Even flat lighting, no glow, no gradient.
The three figures are the SAME character, not three different characters.
```
Negative 추가: `different characters, inconsistent height, inconsistent scale, varying proportions between views, extra characters`

**표정 시트 (4:3)** — 입·눈썹이 없으므로 표정은 **눈 크기·기울기·머리 각도·팔 위치**로만 만든다.
```
Expression sheet of {NAME}: the SAME character repeated in a {N}-cell grid on one flat
neutral off-white background. Each cell shows a different subtle mood conveyed ONLY by
head tilt, eye size and angle, and arm position — {표정1}, {표정2}, ...
Still NO mouth, NO eyebrows, NO eyelashes in any cell.
```

---

## 5. 작성 요령 (실측·주의)

- **비대칭과 재현성은 서로 충돌한다.** '의도적 비대칭'이 이 캐릭터군의 시그니처인데, 같은 캐릭터를 다시 뽑을 때 **그 비대칭 패턴까지 같아야** 동일 캐릭터로 읽힌다. 텍스트로는 절대 안 잡힌다. → **확정 시트 이미지 + Element 바인딩**이 유일한 방법이다. 확정 컷은 반드시 원본 해상도로 보관할 것.
- **비대칭 지시가 과하면 기형이 된다.** 눈·귀·팔·다리에 전부 비대칭을 걸면 얼굴이 무너진 결과가 나온다. 그럴 땐 **눈·코·귀만 비대칭으로 두고 팔다리는 대칭 허용**으로 완화한다.
- 문제됐던 요소는 **3중 방어**: 해당 부위 블록 안에 강조 + `**Important**` 블록 + Negative 중복 기재.
- 재질이 플라스틱처럼 나오면 원인은 대개 **배경 A의 글로우**다. 배경 B로 바꾸면 점토 질감이 살아난다.
- 요구 조건이 4개 이상이면 **하나를 잡는 순간 다른 하나가 풀리는 시소 현상**이 난다. 3회 안에 안 잡히면 가장 근접한 결과를 보여주고 남은 항목을 물어보는 편이 낫다.
- 확정된 캐릭터는 `style/characters.md`에 등록하고 상태를 `확정`으로 올린다. **`탐색중` 캐릭터를 장면 프롬프트에 쓰지 않는다.**
