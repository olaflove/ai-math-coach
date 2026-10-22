# WIDN Math

AI 분석 기반 수학 취약 유형 분석 및 학습 코칭 서비스입니다.
퀴즈 설정·풀이·결과 확인·AI 코칭·보완 학습으로 이어지는 학습 흐름을 제공합니다.

## 프로젝트와 담당 역할

- 개발 기간: 2026.05.26 ~ 2026.06.26
- 2인 공동 프로젝트
- 조유진: 기획, UI/UX 디자인, Vue 기반 프론트엔드 전체 구현
- 핵심 구현: Pinia 기반 퀴즈 세션 상태 관리, 학습 결과·AI 코칭·보완 학습 연결,
  학습 이력·마이페이지·커뮤니티 화면

이 저장소는 공동 작업의 커밋 이력과 작성자 정보를 보존한 개인 포트폴리오용 보관본입니다.
원본 공동 작업 저장소: [ai-math-coach](https://github.com/suvinn/ai-math-coach)

## 구성과 주요 기술

| 경로 | 내용 |
| --- | --- |
| `front/` | Vue 3, Vite, Pinia 기반 프론트엔드 |
| `app/` | Django 기반 API 및 퀴즈·사용자·커뮤니티 기능 |
| `src/preprocessing/`, `scripts/` | 학습 문제 전처리·데이터 준비 스크립트 |
| `data/` | 문제 데이터 및 전처리 결과 |

## 로컬 실행

Python 가상환경에서 의존성을 설치하고 환경변수를 설정합니다.
루트의 `.env.example`은 변수 이름 안내용입니다. 앱 실행 전에 해당 값을 셸 환경변수로
등록하거나, 개발 환경의 환경변수 로딩 도구를 사용해야 합니다.

```bash
python -m pip install -r requirements.txt
python app/manage.py migrate
python app/manage.py runserver
```

별도 터미널에서 프론트엔드를 실행합니다.

```bash
cd front
npm ci
npm run dev
```

퀴즈 이용에는 문제 데이터 준비·DB 적재와 외부 AI API 설정이 추가로 필요합니다.
위 명령만으로 전체 서비스 데이터와 AI 기능이 자동 준비되지는 않습니다.

## 공개본 정리

- 과거 SQLite DB와 로컬 Vite 캐시를 커밋 이력에서 제외했습니다.
- 과거 코드에 직접 들어 있던 Django 비밀키는 가렸습니다.
- 실제 비밀키·API 인증 값은 포함하지 않으며, 실행 시 개인 환경변수로 설정합니다.
