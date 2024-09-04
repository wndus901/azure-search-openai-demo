# Backend

이 디렉토리는 백엔드 코드를 포함하고 있습니다. 백엔드는 [Quart](https://quart.palletsprojects.com/) 프레임워크를 사용하여 비동기 웹 애플리케이션을 구축합니다.

## 디렉토리 구조

- `approaches/`: 다양한 RAG (Retrieval Augmented Generation) 접근 방식을 구현한 클래스들이 포함되어 있습니다.
  - [`chatreadretrieveread.py`](approaches/chatreadretrieveread.py): 기본 채팅 접근 방식.
  - [`chatreadretrievereadvision.py`](approaches/chatreadretrievereadvision.py): GPT Vision 모델을 사용하는 채팅 접근 방식.
  - [`retrievethenread.py`](approaches/retrievethenread.py): 검색 후 읽기 접근 방식.
  - [`retrievethenreadvision.py`](approaches/retrievethenreadvision.py): GPT Vision 모델을 사용하는 검색 후 읽기 접근 방식.
- `prepdocslib/`: 문서 준비 및 벡터화 전략을 포함한 라이브러리.
  - [`strategy.py`](prepdocslib/strategy.py): 문서 준비 전략.
  - [`integratedvectorizerstrategy.py`](prepdocslib/integratedvectorizerstrategy.py): 통합 벡터화 전략.
- [`app.py`](app.py): 백엔드 애플리케이션의 진입점.
- [`config.py`](config.py): 설정 파일.
- [`utils.py`](utils.py): 유틸리티 함수들.

## 환경 변수

백엔드 애플리케이션은 다음과 같은 환경 변수를 사용합니다:

- `AZURE_STORAGE_ACCOUNT`
- `AZURE_STORAGE_CONTAINER`
- `AZURE_USERSTORAGE_ACCOUNT`
- `AZURE_USERSTORAGE_CONTAINER`
- `AZURE_SEARCH_SERVICE`
- `AZURE_SEARCH_INDEX`
- `AZURE_OPENAI_CHATGPT_MODEL`
- `AZURE_OPENAI_EMB_MODEL_NAME`
- `AZURE_OPENAI_EMB_DIMENSIONS`
- `AZURE_OPENAI_SERVICE`
- `AZURE_OPENAI_GPT4V_DEPLOYMENT`
- `AZURE_OPENAI_GPT4V_MODEL`
- `AZURE_OPENAI_CHATGPT_DEPLOYMENT`
- `AZURE_OPENAI_EMB_DEPLOYMENT`
- `AZURE_OPENAI_CUSTOM_URL`
- `AZURE_VISION_ENDPOINT`
- `OPENAI_API_KEY`
- `OPENAI_ORGANIZATION`
- `AZURE_TENANT_ID`
- `AZURE_USE_AUTHENTICATION`
- `AZURE_ENFORCE_ACCESS_CONTROL`
- `AZURE_ENABLE_GLOBAL_DOCUMENT_ACCESS`
- `AZURE_ENABLE_UNAUTHENTICATED_ACCESS`
- `AZURE_SERVER_APP_ID`
- `AZURE_SERVER_APP_SECRET`
- `AZURE_CLIENT_APP_ID`
- `AZURE_AUTH_TENANT_ID`
- `KB_FIELDS_CONTENT`
- `KB_FIELDS_SOURCEPAGE`
- `AZURE_SEARCH_QUERY_LANGUAGE`
- `AZURE_SEARCH_QUERY_SPELLER`
- `AZURE_SEARCH_SEMANTIC_RANKER`
- `AZURE_SPEECH_SERVICE_ID`
- `AZURE_SPEECH_SERVICE_LOCATION`
- `AZURE_SPEECH_VOICE`
- `USE_GPT4V`
- `USE_USER_UPLOAD`
- `ENABLE_LANGUAGE_PICKER`
- `USE_SPEECH_INPUT_BROWSER`
- `USE_SPEECH_OUTPUT_BROWSER`
- `USE_SPEECH_OUTPUT_AZURE`

## 로컬 개발

로컬에서 백엔드를 실행하려면 다음 단계를 따르세요:

1. `azd auth login` 명령어를 실행하여 Azure에 로그인합니다.
2. `app` 디렉토리로 이동합니다.
3. `./start.ps1` 또는 `./start.sh` 스크립트를 실행하거나, VS Code에서 "Start App" 작업을 실행합니다.

## 테스트

테스트는 `tests` 디렉토리에 위치해 있습니다. 테스트를 실행하려면 다음 명령어를 사용하세요:

```sh
python -m pytest