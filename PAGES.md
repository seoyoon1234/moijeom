# 모이점 GitHub Pages

모이점은 함께 만날 장소와 시간을 정하는 웹앱입니다.

## Pages 배포

`node scripts/export-pages.mjs`로 `docs/`를 갱신합니다.
전체 프로젝트를 올릴 때는 GitHub Settings → Pages → Deploy from a branch → main /docs → Save.
현재 GitHub에는 정적 웹앱 파일을 저장소 최상위에 올렸으므로 main /(root)를 선택합니다.

## 현재 가능한 기능

- 지도 중심 첫 화면, 카카오맵 상세주소 검색과 장소 검색
- 월간 캘린더: + → 날짜·시작·종료 시간·참여자 → 저장
- 일정 아래 작은 참여자 이름 표시, 일정 수정·삭제
- 전원 가능 시간 찾기와 약속 시간 선택
- 모임별 브라우저 로컬 저장 (다른 기기와 자동 공유되지 않음)

## 연결이 필요한 기능

카카오맵은 앱의 ‘연결 설정’에 JavaScript 키를 입력해야 합니다. 카카오 개발자 콘솔에 Pages 도메인 `https://seoyoon1234.github.io`를 등록하세요. JavaScript 키는 공개용 SDK 키이며, 관리자 키나 REST API 키를 입력하지 마세요.

GitHub Pages는 정적 호스팅이므로 `app/api/` 서버가 실행되지 않습니다. Pages에서 AI 추천을 사용하려면 별도 API 서버와 인증·호출 제한·CORS 설정이 필요합니다. 이 버전에서는 서버가 없으면 AI 연결 필요 상태를 표시합니다. 가짜 추천을 생성하지 않습니다.

서버용 환경변수는 `.env.example`에 이름만 있습니다. OpenAI 비밀 키를 소스나 브라우저에 넣지 마세요. 현재 실제 대중교통 소요시간과 요금 API는 연결되지 않았으며, 장소 비교는 명확히 표시된 직선거리 기준입니다.
