# 📄 Instagram UI Clone Coding (HTML/CSS)
---
[목표] HTML5와 CSS3를 사용하여 인스타그램 웹페이지의 메인 피드 UI 구현

### 핵심 구현 목표 및 특징

#### 1. 페이지 구성 및 레이아웃 구조
1열 : header
2열 : sidebar-left / content-main / sidebar-right

content-main : story-area/feed-list-area
sidebar-right :user-status-card / recommend-list
우측하단 : fixed-message-btn

#### 2. 폴더 구조
```
instagram-clone/
instagram-clone/
├── index.html
├── README.md
├── assets/
│   └── (이미지, 아이콘, 폰트 등)
└── styles/
    ├── style.css           # (Main Hub) 모든 CSS 파일을 @import
    ├── 01-general.css      # (Base) 초기화, 전역 변수, 폰트
    ├── 02_layout.css       # (Layout) CSS Grid 기반 전체 영역 배치
    ├── 03_utilities.css    # (Utils) .hidden, .mt-20 등 보조 클래스
    └── components/         # (Components) 재사용 가능한 UI 부품
        ├── c-icon-button.css
        ├── c-text-button.css
        ├── c-user-profile.css
        ├── c-post-card.css
        ├── c-sidebar-item.css
        └── c-input-field.css

```

---
