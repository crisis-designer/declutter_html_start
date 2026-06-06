# Declutter 디자인 시스템 명세서

**버전** 1.1.0 · **작성일** 2026-05-29
**기준 환경** Mobile-first (iOS/Android WebView · 375px 기준)
**폰트** Pretendard · **아이콘** Lucide Icons (SVG)

---

## 1. 브랜드 콘셉트

> **"덜어냄의 미학"** — 군더더기 없는 흑백 모노톤 위에 숨 쉬는 여백. 물건을 버리는 행위처럼, 화면에서도 불필요한 것은 모두 걷어낸다.

- **무드**: 극단적 미니멀리즘 (Radical Minimalism)
- **키워드**: 절제, 고요, 가벼움, 성취
- **포인트 컬러**: 딥블랙 `#111111` — 단 하나의 색으로 무게감과 신뢰를 동시에 표현

---

## 2. 컬러 시스템

### 2.1 코어 컬러

| 토큰 | 값 | 설명 |
|:---|:---|:---|
| `--background` | `#F9F9F9` | 오프화이트 배경 |
| `--foreground` | `#111111` | 메인 텍스트 |
| `--card` | `#FFFFFF` | 카드 배경 |
| `--primary` | `#111111` | 포인트 블랙 |
| `--primary-fg` | `#F9F9F9` | primary 위 텍스트 |
| `--secondary` | `#F2F2F7` | 보조 Surface |
| `--muted` | `#8E8E93` | 비활성/플레이스홀더 |
| `--destructive` | `#FF3B30` | 삭제/오류 (iOS Red) |
| `--accent` | `#F2F2F7` | 호버/눌림 배경 |
| `--border` | `#E5E5EA` | 경계선 |
| `--radius` | `12px` | 기본 곡률 |
| `--radius-sm` | `8px` | Badge, Tag |
| `--radius-lg` | `16px` | Card, Sheet |

### 2.2 카테고리 컬러 팔레트

| 카테고리 | 배경 | 텍스트 | 설명 |
|:---:|:---:|:---:|:---|
| `#의류` | `#E8EEF4` | `#3A5A7C` | 연 스틸블루 |
| `#잡화` | `#EEF0E8` | `#5A6340` | 연 올리브 |
| `#도서` | `#F4EDE8` | `#7C5A3A` | 연 샌드베이지 |
| `#가구` | `#EDE8F4` | `#5A3A7C` | 연 라벤더 |
| `#전자기기` | `#E8F0EE` | `#3A6358` | 연 민트그레이 |
| `#기타` | `#F0EFE8` | `#6E6452` | 연 크림 |

---

## 3. 타이포그래피 스케일

**기준 폰트**: Pretendard Variable
**기준 해상도**: 375px (모바일)

| 토큰 | 역할 | Size | Line-height | Font-weight | 사용 예시 |
|:---|:---|:---:|:---:|:---:|:---|
| `--text-display` | 앱 타이틀 / 감성 문구 | `28px` | `1.3` | `700` | 빈 상태 메시지 |
| `--text-heading-1` | 섹션 헤더 | `20px` | `1.4` | `700` | "지금까지 비운 기록" |
| `--text-heading-2` | 날짜 소제목 | `16px` | `1.4` | `600` | "2026년 5월 29일" |
| `--text-body-1` | 기본 본문 / 입력값 | `16px` | `1.5` | `400` | 물건 이름 텍스트 |
| `--text-body-2` | 보조 본문 | `15px` | `1.5` | `400` | 카드 상세 텍스트 |
| `--text-label` | 버튼 레이블 | `16px` | `1` | `600` | CTA 버튼 문구 |
| `--text-caption` | 배지 / 보조 정보 | `12px` | `1.4` | `500` | 카테고리 배지 |
| `--text-counter` | 카운터 숫자 | `13px` | `1` | `500` | "0 / 3" |

---

## 4. 컴포넌트 상세 사양

### 4.1 Input (텍스트 입력창)

| 속성 | 값 |
|:---|:---|
| Height | `52px` |
| Padding X | `16px` |
| Border Radius | `12px` |
| Border | `1px · #E5E5EA` |
| Focus Ring | `2px · #111111/10%` |

**상태별 토큰**

| 상태 | Background | Border | Text |
|:---|:---|:---|:---|
| Default | `#FFFFFF` | `#E5E5EA` | `#111111` |
| Focus | `#FFFFFF` | `#111111` | `#111111` |
| Disabled | `#F2F2F7` | `#E5E5EA` | `#8E8E93` |
| Error | `#FFF5F5` | `#FF3B30` | `#111111` |

---

### 4.2 Button (CTA 와이드 버튼)

| 속성 | 값 |
|:---|:---|
| Height | `56px` |
| Width | `100%` (좌우 margin 16px) |
| Border Radius | `12px` |
| Font | `16px / SemiBold` |
| Bottom Safe Area | `env(safe-area-inset-bottom)` |

**상태별 토큰**

| 상태 | Background | 트리거 조건 |
|:---|:---|:---|
| Disabled | `#8E8E93` | 입력값 전부 빈 값 |
| Enabled | `#111111` | 1개 이상 입력 시 |
| Pressed | `#2C2C2E · opacity 0.9` | 터치 다운 |

---

### 4.3 Badge (카테고리 태그)

| 속성 | 값 |
|:---|:---|
| Height | `28px` |
| Padding X | `10px` |
| Border Radius | `8px` |
| Font | `12px / Medium` |

---

### 4.4 Card (아카이브 카드)

| 속성 | 값 |
|:---|:---|
| Padding | `16px` |
| Border Radius | `16px` |
| Shadow | `0 1px 3px rgba(0,0,0,0.06)` |
| Gap (cards) | `10px` |
| Name → Badge gap | `6px` |

---

## 5. 스페이싱 시스템 · 4px Grid

| 토큰 | 값 | 사용 예시 |
|:---|:---:|:---|
| `--space-1` | `4px` | 아이콘 ↔ 텍스트 최소 간격 |
| `--space-2` | `8px` | 배지 내부 간격, 소항목 간격 |
| `--space-3` | `12px` | 입력 행 내부 요소 간격 |
| `--space-4` | `16px` | 화면 좌우 마진, 카드 패딩 |
| `--space-5` | `20px` | 섹션 헤더 하단 여백 |
| `--space-6` | `24px` | 섹션 간 여백 |
| `--space-8` | `32px` | 주요 섹션 구분 |
| `--space-10` | `40px` | 화면 상단 safe area 여유 |

---

## 6. 하단 탭바 (Bottom Navigation Bar)

| 속성 | 값 |
|:---|:---|
| Height | `56px` + `env(safe-area-inset-bottom)` |
| Background | `#FFFFFF` + `backdrop-filter: blur(12px)` |
| Border Top | `1px solid #E5E5EA` |
| Icon Size | `24px` |
| Active | `#111111` · Bold |
| Inactive | `#8E8E93` · Regular |
| Transition | `color 150ms ease-out` |

---

## 7. 변경 이력

| 버전 | 날짜 | 변경 내용 |
|:---|:---|:---|
| 1.1.0 | 2026-05-29 | 키워드 매칭 기반 카테고리 자동 태깅 규칙 추가, 아카이브 수정/삭제 기능 추가, 카테고리 드롭다운 Drop-up 규칙 정의 |
| 1.0.0 | 2026-05-29 | 초안 작성 — 컬러, 타이포그래피, 4개 컴포넌트 사양 정의 |
