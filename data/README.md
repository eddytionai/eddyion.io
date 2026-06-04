# 프로젝트 관리 가이드

## 디렉토리 구조

```
eddytion.io/
├── data/
│   ├── work.json      # Work 페이지 프로젝트 데이터
│   ├── play.json      # Play 페이지 프로젝트 데이터
│   └── README.md      # 이 파일
└── assets/
    ├── work/          # Work 프로젝트 이미지
    │   ├── project-1/
    │   │   └── thumbnail.jpg
    │   ├── project-2/
    │   │   └── thumbnail.jpg
    │   └── ...
    └── play/          # Play 프로젝트 이미지
        ├── play-1/
        │   └── thumbnail.jpg
        ├── play-2/
        │   └── thumbnail.jpg
        └── ...
```

## 새 프로젝트 추가 방법

### 1. Work 프로젝트 추가

1. **이미지 추가**: `assets/work/` 폴더에 새 프로젝트 폴더 생성
   ```
   assets/work/my-new-project/
   └── thumbnail.jpg  (썸네일 이미지)
   ```

2. **데이터 추가**: `data/work.json` 파일에 프로젝트 정보 추가
   ```json
   {
     "id": "my-new-project",
     "title": "프로젝트 제목",
     "subtitle": "프로젝트 설명",
     "thumbnail": "assets/work/my-new-project/thumbnail.jpg",
     "link": "content.html?id=my-new-project"
   }
   ```

### 2. Play 프로젝트 추가

1. **이미지 추가**: `assets/play/` 폴더에 새 프로젝트 폴더 생성
   ```
   assets/play/my-experiment/
   └── thumbnail.jpg
   ```

2. **데이터 추가**: `data/play.json` 파일에 프로젝트 정보 추가
   ```json
   {
     "id": "my-experiment",
     "title": "실험 제목",
     "subtitle": "실험 설명",
     "thumbnail": "assets/play/my-experiment/thumbnail.jpg",
     "size": "size-large"
   }
   ```

## Play 프로젝트 크기 옵션

Play 페이지는 4가지 크기를 지원합니다:

- `size-square`: 1x1 정사각형
- `size-vertical`: 1x2 세로형
- `size-horizontal`: 2x1 가로형
- `size-large`: 2x2 큰 정사각형

**레이아웃 팁**: 빈 공간을 최소화하려면 큰 카드(`size-large`, `size-horizontal`, `size-vertical`)를 먼저 배치하고, 작은 카드(`size-square`)를 나중에 배치하세요.

## 프로젝트 순서 변경

JSON 파일에서 프로젝트 객체의 순서를 변경하면 웹사이트에 표시되는 순서가 바뀝니다.

## 프로젝트 수정

JSON 파일에서 해당 프로젝트의 `title`, `subtitle` 등을 수정하면 즉시 반영됩니다.

## 프로젝트 삭제

1. JSON 파일에서 해당 프로젝트 객체 삭제
2. `assets/` 폴더에서 해당 프로젝트 폴더 삭제 (선택사항)

## 권장 이미지 사양

### Work 페이지
- **비율**: 1:1 (정사각형)
- **권장 크기**: 1200x1200px 이상
- **포맷**: JPG, PNG, WebP

### Play 페이지
- **size-square**: 1:1 비율
- **size-vertical**: 3:4 비율
- **size-horizontal**: 4:3 비율
- **size-large**: 1:1 비율
- **권장 크기**: 최소 800px (짧은 변 기준)
- **포맷**: JPG, PNG, WebP

## 예시

### Work 프로젝트 추가 예시
```json
{
  "id": "nike-rebrand",
  "title": "Nike Rebrand 2024",
  "subtitle": "Brand Identity Redesign",
  "thumbnail": "assets/work/nike-rebrand/thumbnail.jpg",
  "link": "content.html?id=nike-rebrand"
}
```

### Play 프로젝트 추가 예시
```json
{
  "id": "abstract-motion",
  "title": "Abstract Motion Study",
  "subtitle": "Generative Animation",
  "thumbnail": "assets/play/abstract-motion/thumbnail.jpg",
  "size": "size-large"
}
```
