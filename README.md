# 📸 Instagram Clone Coding Project

HTML/CSS 학습을 목적으로 하는 **Instagram UI 클론 코딩** 프로젝트입니다.
다양한 디바이스 크기에 대응하는 **반응형 웹 디자인**을 Git 브랜치 관리를 통해 체계적으로 구현합니다.

## 주요 목표

* **HTML/CSS 심화 학습:** Flexbox 및 Grid 시스템을 활용한 복잡한 레이아웃 구현.
* **반응형 디자인 (RWD) 적용:** Media Query를 활용하여 PC 및 모바일 환경에 최적화된 UI 제공.
* **Git & Branch 관리:** Git Flow(간소화) 전략을 적용하여 기능별 브랜치 관리 연습.


## 파일 구조
```
project-folder/
├── index.html
└── styles/
    ├── 01-general.css    (공통 스타일: 폰트, reset 등)
    ├── 02-pc-layout.css  (PC 레이아웃 전용)
    ├── 03-mobile.css     (모바일 레이아웃 전용)
    └── 04-components.css (버튼, 카드 등 공통 컴포넌트)
```

## 레이아웃 구성

프로젝트의 핵심 레이아웃은 **PC (Desktop)** 및 **모바일 (Mobile)** 환경에 따라 다르게 구성됩니다.

### 1. PC (Desktop) 레이아웃

PC 환경에서는 3열 그리드 시스템을 기본으로 사용하며, 화면 크기에 따라 사이드바를 축소하거나 숨깁니다.

| 영역 | CSS 선택자 | 포함 내용 |
| :--- | :--- | :--- |
| **왼쪽 사이드바** | `sidebar-left` | 네비게이션 메뉴 (아이콘 또는 전체 LNB) |
| **중앙 콘텐츠** | `content-main` | 스토리 영역, 피드 목록 |
| **오른쪽 사이드바** | `sidebar-right` | 사용자 상태 카드, 추천 목록 |
| **고정 버튼** | `fixed-message-btn` | 우측 하단의 고정된 메시지 버튼 |

#### 중앙 콘텐츠 (`content-main`) 상세

* `story-area`
* `feed-list-area`

#### 오른쪽 사이드바 (`sidebar-right`) 상세

* `user-status-card`
* `recommend-list`

### 2. 모바일 (Mobile) 레이아웃

모바일 환경에서는 상단 및 하단 고정 내비게이션을 통해 화면 활용도를 높입니다.

| 영역 | CSS 선택자 | 특징 |
| :--- | :--- | :--- |
| **상단 헤더** | `header` | 상단 고정 |
| **중앙 콘텐츠** | `content-main` | 상하단 고정 메뉴에 가려지지 않도록 여백 설정 |
| **하단 내비게이션** | `nav` / `.bottom-nav-bar` | 하단 고정 메뉴 |
| **고정 버튼** | `fixed-message-btn` | 크기가 작게 조정됨 |

### 3. 반응형 구현 계획

| Breakpoint | CSS 선택자 및 로직 | 레이아웃 상태 및 변경 사항 |
| :--- | :--- | :--- |
| **기본 (1301px 이상)** | `.pc-container { display: grid; ... }` | **3열 Grid** (Full LNB + Main + Sidebar) |
| **1300px 이하** | `.pc-container`의 `grid-template-columns` 조정 | **LNB 축소** (아이콘만) 유지 |
| **1024px 이하** | `.sidebar-right { display: none; }` | **오른쪽 사이드바 숨김** / 2열 Grid (축소 LNB + Main) |
| **768px 이하** | 1. `.pc-container { display: none; }` | **PC 레이아웃 전체 숨김** |
| | 2. `.header, .bottom-nav-bar { display: flex; position: fixed; }` | **모바일 상단 헤더 및 하단 메뉴 등장** |
| | 3. `.content-main { padding-top/bottom: ... }` | 중앙 콘텐츠 상하 여백 추가 (고정 메뉴 가림 방지) |
| | 4. `.fixed-message-btn` | **크기 작게 조정** (width/height 감소) |

## Git Branch 관리 계획

| 브랜치 | 개발 내용 (예시) |
| :--- | :--- |
| `main` | 최종 배포 코드 |
| `develop` | 기능 통합 및 주 개발 브랜치 |
| `feature/pc-layout` | 1301px 이상 PC 기본 3열 그리드 구현 |
| `feature/responsive-sidebar` | 1300px 및 1024px 이하 사이드바 축소/숨김 로직 구현 |
| `feature/mobile-layout` | 768px 이하 모바일 레이아웃 (헤더, 하단 메뉴) 구현 |
| `feature/story-feed` | 스토리 영역 및 피드 목록 (`content-main` 내부) 구현 |



## 💻 Git 활용 및 브랜치 전략 가이드

### 1. Git 기본 설정 및 저장소 생성

| 명령어 | 설명 |
| :--- | :--- |
| `git init` | 현재 디렉토리를 **Git 저장소**로 초기화합니다. 프로젝트 폴더 안에서 실행하세요. |
| `git add .` | 현재 작업 디렉토리의 모든 변경 사항을 **스테이징 영역**에 추가합니다. |
| `git commit -m "커밋 메시지"` | 스테이징된 변경 사항을 **로컬 저장소**에 기록합니다. 메시지는 작업 내용을 요약합니다. |

### 2. 브랜치 전략: Git Flow 기초 (간소화)

소규모 클론 코딩 프로젝트에서는 **`main`** 브랜치와 **`develop`** 브랜치, 그리고 기능별 **`feature`** 브랜치를 사용하는 간소화된 전략을 추천합니다.

| 브랜치 이름 | 목적 |
| :--- | :--- |
| **`main`** | **배포 가능한 안정적인 최종 코드**를 보관합니다. 이 브랜치에서는 직접 작업하지 않습니다. |
| **`develop`** | **주요 개발이 진행되는 브랜치**입니다. 모든 새로운 기능은 이 브랜치로 통합됩니다. |
| **`feature/*`** | **특정 기능 개발**을 위한 브랜치입니다. (예: `feature/pc-layout`, `feature/mobile-nav`) |

### 3. 브랜치 생성 및 작업 흐름 (예시)

1.  **`develop` 브랜치 생성 및 전환:**
    ```bash
    git branch develop  # develop 브랜치 생성
    git checkout develop # develop 브랜치로 이동
    # 또는 git checkout -b develop (생성과 이동을 동시에)
    ```
2.  **새 기능 브랜치 생성 및 전환 (PC 레이아웃 작업 시작):**
    ```bash
    git checkout -b feature/pc-layout
    ```
3.  **작업 후 커밋:**
    HTML/CSS 작업을 완료하고 변경 사항을 커밋합니다.
    ```bash
    git add .
    git commit -m "feat: PC 기본 레이아웃 (3열 그리드) 구현"
    ```
4.  **`develop` 브랜치로 통합 (Merge):**
    기능 개발이 완료되면 **`develop`** 브랜치로 돌아와서 합칩니다.
    ```bash
    git checkout develop
    git merge feature/pc-layout
    ```
5.  **기능 브랜치 삭제 (선택 사항):**
    합친 후에는 브랜치를 정리할 수 있습니다.
    ```bash
    git branch -d feature/pc-layout
    ```
    **👉 이 과정을 반복하여 다른 기능(모바일, 피드, 사이드바 등)을 개발하고 `develop`에 통합합니다.**