# LucyInk D-Day Banner Template Guide

이 문서는 루시잉크 다이어리의 디데이 배너 템플릿을 AI에게 의뢰할 때 쓰는 제작 지시서입니다.

## 목표

디데이 배너는 사용자가 등록한 이미지가 없어도 완성된 카드처럼 보여야 하고, 이미지가 있을 때는 이미지 위에 텍스트가 안정적으로 읽혀야 합니다.

## 출력 형식

AI에게 아래 형식으로 결과를 요청하세요.

```json
{
  "id": "template-id",
  "label": "템플릿 이름",
  "mood": "짧은 무드 설명",
  "layout": "left-title | center-title | split",
  "background": "CSS background 값",
  "overlay": "이미지 위에 올릴 linear-gradient 값",
  "textColor": "#ffffff",
  "accentColor": "#7b9bff",
  "border": "CSS border 값",
  "shadow": "CSS box-shadow 값",
  "notes": "적용 시 주의할 점"
}
```

## 제작 조건

- 권장 비율: 16:9, 3:1, 2:1 모두에서 자연스럽게 보여야 합니다.
- 텍스트 영역은 최소 48px 높이, 좌우 12px 이상의 여백을 확보합니다.
- 긴 제목, `D-1000`, `D+1000`까지 겹치지 않아야 합니다.
- 이미지가 들어올 수 있으므로 `overlay`는 반드시 포함합니다.
- 별도 이미지 에셋은 만들지 말고 CSS 배경, 그라데이션, 테두리, 그림자만 제안합니다.
- 색상은 루시잉크 테마 변수와 섞기 좋게 `accentColor`를 분리합니다.

## AI 프롬프트 예시

```text
루시잉크 다이어리 앱용 디데이 배너 템플릿 5종을 만들어줘.
각 템플릿은 JSON 형식으로 id, label, mood, layout, background, overlay,
textColor, accentColor, border, shadow, notes를 포함해줘.
이미지 에셋 없이 CSS만으로 구현 가능해야 하고,
D-1000 같은 긴 디데이 텍스트와 긴 제목이 겹치지 않게 설계해줘.
무드는 고급 문구류, 유리 질감, 밤하늘, 봄빛, 모노 잉크로 나눠줘.
```

## 앱 반영 메모

현재 앱에는 기본 템플릿 `theme`, `glass`, `paper`가 들어 있습니다. 새 템플릿을 반영할 때는 `app.js`의 `DIARY_DDAY_TEMPLATES`와 `index.html`의 `.template-{id}` 스타일을 함께 추가하면 됩니다.
