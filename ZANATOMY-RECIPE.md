# Z-Anatomy → OMDT 근육 도해 렌더 레시피

목표: **글자 없는 · 정면 · 흰(투명) 배경 · 일정 프레이밍**의 근육 PNG를 뽑아
`C:\project\OMDT\img\`에 저장 → tools/calib.html로 좌표 찍기 → OMDT 표식 연결.

정사영(orthographic) 렌더라 클로즈업 각도 틀어지던 문제도 사라지고,
**카메라 안 움직이고 레이어만 껐다 켜서 천층·심층을 뽑으면 픽셀 단위로 정합**됩니다.

---

## A. 최초 1회 설치

1. **Blender 설치** — https://www.blender.org/download/ (무료, Windows)
2. **Z-Anatomy 템플릿 내려받기** — https://lluisv.itch.io/z-anatomy (또는 GitHub Z-Anatomy)
   → `Z-Anatomy_Template.zip` 다운로드, 압축 풀기
3. Blender 실행 → 좌상단 Blender 아이콘 → **Install Application Template** → `Z-Anatomy.zip` 선택
4. **File → New → Z-Anatomy** 로 인체 모델 열기

> 라이선스: CC BY-SA 4.0. OMDT 정보 화면에 반드시 표기 —
> "해부 그림: Z-Anatomy / BodyParts3D (CC BY-SA 4.0)". 뽑은 이미지도 CC BY-SA가 됨.

---

## B. 깨끗한 기본 세팅 (1회, 저장해두고 재사용)

### B-1. 신경·혈관 숨기기 (노란 신경선 제거)
- 우측 **Outliner**(계층 목록)에서 신경(Nerves)·혈관(Vessels) 컬렉션의 **눈 아이콘 끄기**
- 근육(Muscles)·뼈(Skeleton)만 남김

### B-2. 배경 투명 (기존 Gemini 그림과 합성 톤 맞춤)
- 우측 속성창 → **Render Properties**(카메라 뒷면 아이콘) → **Film** → **Transparent** 체크
- (흰 배경 원하면 대신 World Properties → Color 흰색)

### B-3. 렌더 엔진·해상도
- Render Properties → 엔진 **EEVEE**(빠름)
- **Output Properties**(프린터 아이콘) → Resolution **1000 × 1200** 정도, 형식 **PNG / RGBA**

### B-4. 조명 평탄하게
- 강한 그림자 없이 균일하게 — 기본 스튜디오 라이팅이면 대개 OK.
  그림자 세면 World 밝기 살짝 올리기.

→ 여기까지 하고 **File → Save As** 로 `zanatomy-base.blend` 저장. 다음부턴 이거 열고 시작.

---

## C. 한 뷰 뽑는 루틴 (반복)

### C-1. 시야 각도 맞추기 (정사영)
- 마우스를 3D 뷰 위에 두고 **넘패드**로:
  - `1` 정면(앞) / `Ctrl+1` 후면(뒤)
  - `3` 우측면 / `Ctrl+3` 좌측면
  - `5` 정사영↔원근 토글 (반드시 **정사영** 상태로 = 원근 왜곡 없음)
- 휠로 확대해 원하는 부위가 화면에 꽉 차게

### C-2. 카메라를 이 시야에 고정
- `Ctrl+Alt+넘패드0` → 카메라가 현재 시야로 이동
- 카메라 속성(초록 필름 아이콘) → **Lens → Type: Orthographic** 확인

### C-3. 레이어 격리 (근육 노출)
- **천층**: 그대로
- **심층**: Outliner에서 덮는 근육(예: 승모근·삼각근) **눈 아이콘 끄기** → 속근육 노출
- 필요 없는 부위(반대쪽 팔 등)도 눈 끄면 깔끔
- ★ **카메라 그대로 두고** 천층 렌더 → 덮개 끄고 심층 렌더 하면 두 장이 완벽 정합

### C-4. 렌더 & 저장
- `F12` 렌더 → 렌더창 → **Image → Save As** → `C:\project\OMDT\img\` 에 저장
- 파일명 규칙(아래) 지키기

---

## D. 파일명 규칙 (tools/calib.html이 이 이름으로 부름)

| 부위 | 천층 | 심층 |
|---|---|---|
| 상체 후면 | `back-upper-super.png` | `back-upper-deep.png` |
| 상체 전면 | `front-upper-super.png` | `front-upper-deep.png` |
| 상체 측면 | `lateral-upper-super.png` | `lateral-upper-deep.png` |
| 어깨 후면(삼각근 제거) | — | `back-shoulder.png` |
| 어깨 전면 | — | `front-shoulder.png` |
| 아래팔 신전측 | — | `external-lower-arm.png` |
| 아래팔 굴곡측 | — | `medial-lower-arm.png` |
| 대퇴 전/후 | — | `front-upper-leg.png` / `back-upper-leg.png` |
| 하퇴 전/후 | — | `front-lower-leg.png` / `back-lower-leg.png` |
| 발목·발 | — | `ankle.png` (단일 발 권장) |
| 요부·둔부 후면 | `back-lower-super.png` | `back-lower-deep.png` |

> 같은 이름으로 덮어쓰면 tools/calib.html에서 근육 목록·좌표가 그대로 이어짐.

---

## E. 우선순위 (다 할 필요 없음)

진료 빈도순으로 몇 개만 먼저:
1. **어깨 후면**(삼각근 제거) — 회전근개·소원·대원. 지금 제일 아쉬운 부분
2. **아래팔 신전/굴곡** — 엘보
3. 나머지는 필요할 때

한 뷰 뽑을 때마다 tools/calib.html에서 좌표 찍고 💾 전체 저장 → 채팅에 올리면 연결.

---

## F. 막히면

- 근육 이름을 모르겠으면 Z-Anatomy에서 구조 클릭 → 라벨 표시 기능으로 확인
- 특정 근육이 다른 데 가려 안 보이면, 가리는 근육 눈만 꺼서 노출
- 스크린샷/렌더가 어색하면 각도(C-1)부터 다시. 정사영(넘패드5) 꼭 확인
