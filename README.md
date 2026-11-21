# 초록 한 장

사진으로 식물을 알아보고 브라우저에 나만의 도감을 저장하는 웹앱입니다.

## 로컬 실행

1. Node.js 22.9 이상을 설치합니다.
2. 프로젝트 폴더의 `env_local.txt`에 Azure AI 설정을 넣습니다. 파일에는 실제 키가 있으므로 GitHub에 올리거나 다른 사람에게 공유하지 마세요.

   ```text
   AI_ENDPOINT=Azure OpenAI 호환 API의 /openai/v1/ 주소
   AI_API_KEY=Azure API 키
   AI_DEPLOYMENT=이미지 입력과 JSON 응답을 지원하는 배포 이름
   ```

3. 터미널에서 `npm run dev`를 실행하고 `http://localhost:3000`을 엽니다. Windows PowerShell에서 npm 실행이 차단되면 `npm.cmd run dev`를 사용합니다.
4. 자동 테스트는 `npm test`로 실행합니다.

기존 `env_local.txt`를 그대로 사용할 수 있습니다. 필요하다면 `.env.example`을 참고해 `.env.local`을 사용할 수도 있습니다. 값은 서버에서만 읽습니다.

## Vercel 배포

GitHub에 코드를 올린 뒤 Vercel에서 프로젝트를 가져오고 `AI_ENDPOINT`, `AI_API_KEY`, `AI_DEPLOYMENT`를 서버 환경변수로 등록하세요. `env_local.txt`와 `.env.local`은 저장소에 올리지 않습니다. 환경변수를 바꾼 뒤에는 재배포해야 합니다.

Azure 배포 모델이 이미지 입력과 JSON 응답을 지원해야 합니다. 공개 전 Azure의 사용량 제한과 비용 경고, 데이터 처리 정책 및 공개 API 남용 방지 대책을 운영자가 확인하세요. 현재 앱 자체에는 사용자 인증이나 요청 빈도 제한이 없습니다.

## 데이터와 사용 안내

- 이름과 도감은 현재 브라우저의 `localStorage`에만 저장됩니다. 다른 기기에 동기화되지 않으며 브라우저 데이터 삭제나 저장 공간 제한의 영향을 받습니다.
- 사진과 질문은 분석을 위해 Azure AI에 전송됩니다. 대화는 현재 화면에서만 유지됩니다.
- AI 답변이 틀릴 수 있으므로 식용이나 안전성은 반드시 어른과 전문가에게 확인하세요.
- 모바일 카메라 실행 방식은 브라우저와 기기에 따라 다릅니다.
- PDF는 외부 CDN과 Google Fonts에 연결할 수 있어야 만들 수 있습니다.
