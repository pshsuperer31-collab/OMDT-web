# z-anatomy.com 웹 뷰어 → OMDT 근육 그림 캡처 레시피

설치 없이 브라우저에서. 목표: 근육 그림 스크린샷 → 크롭 → `C:\project\OMDT\img\`에 저장.

## 기본 조작
- **회전**: 인체 위에서 마우스 왼쪽 드래그
- **확대/이동**: 휠 스크롤 / 손바닥 아이콘으로 이동
- **정확한 각도**: 왼쪽 아래 좌표공(X·Y·Z) 클릭 → 정면/후면/측면 딱 맞춤
- **근육 켜고 끄기**: 오른쪽 Lexicon 목록의 **눈 아이콘(👁)**
- **균일 색**: 목록에서 그룹 이름 클릭 = 전체 선택(한 색). ⚙ 설정에 realistic 색 옵션 있으면 그걸로
- **패널 닫기**: 목록 오른쪽 위 **X** (그림 가리지 않게)

## 한 뷰 뽑기
1. **근육 켜기**: 목록 맨 위 "Muscular system" 눈 아이콘 ON → 전신 근육
2. **덮개 끄기**(심층 볼 때): 덮는 근육 눈 아이콘 OFF
   - 어깨 후면 회전근개 → Deltoid(삼각근)·Trapezius(승모근) 끄기
3. **각도**: 좌표공으로 정면/후면/측면 맞추고 휠로 부위 크게
4. **색 균일화**: 알록달록하면 그룹 이름 클릭해 한 색으로
5. **패널 X로 닫기**
6. **스크린샷** (윈도우: `Win + Shift + S` 로 영역 캡처)
7. **인체 부분만 크롭** (그림판 등) → 아래 이름으로 저장

## 파일명 (tools/calib.html이 이 이름으로 부름)
| 부위 | 파일명 |
|---|---|
| 상체 후면 천층 | `back-upper-super.png` |
| 상체 후면 심층 | `back-upper-deep.png` |
| 어깨 후면(삼각근 제거) | `back-shoulder.png` |
| 어깨 전면 | `front-shoulder.png` |
| 상체 전면 천/심 | `front-upper-super.png` / `front-upper-deep.png` |
| 상체 측면 천/심 | `lateral-upper-super.png` / `lateral-upper-deep.png` |
| 아래팔 신전/굴곡 | `external-lower-arm.png` / `medial-lower-arm.png` |
| 대퇴 전/후 | `front-upper-leg.png` / `back-upper-leg.png` |
| 하퇴 전/후 | `front-lower-leg.png` / `back-lower-leg.png` |
| 발목·발 | `ankle.png` |
| 요부·둔부 천/심 | `back-lower-super.png` / `back-lower-deep.png` |

## 팁
- **색을 하나로 통일**하세요(전부 주황이든 전부 자연색이든). 뷰마다 색 다르면 OMDT가 들쭉날쭉.
- 같은 부위 천층·심층은 **각도·확대를 똑같이** 두고 덮개 근육만 껐다 켜서 두 장 = 정합 잘 맞음.
- 크롭할 때 상하좌우 여백 비슷하게. 인체가 프레임 중앙에 오도록.

## 라이선스
OMDT 정보 화면에 표기: "해부 그림: Z-Anatomy / BodyParts3D (CC BY-SA 4.0)"
