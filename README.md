# 202230120 왕도현
## 09월 09일 (2주차)

## 1. 프로젝트 수동 생성
- 명령어 : `pnpm i next@latest react@latest react-dom@latest`
- `next dev` : 개발 서버 시작
- `next buid` : 프로덕션을 위한 애플리케이션 빌드
- `next start` : 프로덕션 서버 시작
- 타입스크립트 환경에서 `react`와 `react-dom`을 사용할 수 있도록 제공하는 패키지를 설치해야 함 <br>
→ `pnpm add -D @types/react @types/react-dom`
- 서버 시작 : `pnpm dev`
- `paths` 옵션을 통해 모듈 경로를 별칭으로 사용
- 자동 생성 : `package.json` 파일에 `script` 자동 추가, TypeScript, Eslint, Tailwind CSS, src 디렉토리, App Router (선택)
- 실습 : `pnpm create next-app@latest` / `npx create-next-app@latest`
- 디렉토리 : `src/`

# 2. 구조
## 2-1. 폴더 및 파일 규칙
- `최상위 폴더 (Top-level folders)` : 애플리케이션 코드와 정적 자산을 구성
- 사용 : 애플리케이션 구성, 종속성 관리, 프록시 실행, 모니터링 도구 통합, 환경 변수 정의 (js, ts, env, json)
- app, package, public, …
- `라우팅 파일` : 경로 노출할 페이지 추가, 헤더, 내비게이션, 푸터와 같은 레이아웃, 스켈레톤(로딩, 오류)
- layout, page, loading, not-found, …
- `중첩 라우팅`
  - URL의 세그먼트 정의
  - 디렉토리 중첩 시 세그먼트 중첩
  - 모든 수준의 레이아웃은 하위 세그먼트 감쌈
  - 페이지나 경로 파일이 존재하면 해당 경로는 공개됨
- `동적 라우팅` : 대괄호 사용하여 세그먼트를 매개변수화
  - `[segment]` : 단일 매개변수
  - `[...segment]` : 모든 값 포괄
  - `[[...segment]]`: 선택적 포괄 매개변수
 - `param` 속성을 통해 값에 접근함
 - 1개의 특정 경로 세그먼트만 동적으로 매칭 (/posts) → X
- `Catch-all 라우팅` : 해당 경로 아래에 오는 모든 하위 경로를 하나의 배열로 전달하여 매칭
- `Optional Catch-all 라우팅` : Catch-all 라우팅과 같지만 동적 파라미터가 없는 기본 경로(/post)도 매칭

## 09월 02일 (1주차)
## 1. Next.js
- 정의 : 풀스택 웹 애플리케이션 구축을 위한 React 프레임워크
- 특징 : 번들러 및 컴파일러와 같은 하위 수준 도구를 자동으로 구성

## 1-1. 공식 문서 챕터
- `Gutting Start` : 핵심 기능
- `guide` :  사용 사례 (자신에게 맞는 내용 선택)
- `API Reference` : 모든 기능에 대한 자세한 기술 참조

## 2. 라우터
- `App Router` : 최신 라우터 (새로운 React 기능 지원)
- `Pages Router` : 초기 라우터

## 3. 접근성
- 정의 : 웹 접근성
- 화면 판독기 : FireFox, NVDA, Safari, VoiceOver

 ## 4. pnpm
 - 정의 : `performant(성능이 좋은) npm` 약자
 - 개선점 : 디스크 공간 낭비 / 복잡한 의존성 관리 / 느린 설치 속도 문제

## 4-1. 특징
- 하드 링크 기반의 효율적 저장 공간 사용 <br>
  → 패키지 설치
- 이미 설치된 패키지 재사용 O <br>
  → 종속성 설치 및 업데이트할 때 빠른 속도 경험
- 효율적인 종속성(= 의존성) 관리
- 다른 패키지 매니저(npm, yarn)의 비효율성 개선
- 속도 ↑, 디스크 사용량 ↓

## 5. 하드 링크 (Hard Link)
- 종류
  - `Directory Entry` : 파일 이름과 해당 inode 번호를 매핑 정보가 있는 특수 파일
  - `incode` : 파일 또는 디렉토리에 대한 모든 메타 데이터를 저장하는 구조체 (권한, 소유자, 크기, 데이터 블록 위치 …)
  - `data blocks` : 실제 데이터가 존재하는 영역
    
- 특징
  - 디렉토리 엔트리에 매핑 정보 추가
  - 원본과 하드 링크는 동일한 파일 <br>
  → inode 참조, 하나만 삭제하면 디렉토리 엔트리에서 이름만 삭제
  - `link count`가 0이 되지 않는 한 데이터 존재
 
## 6. 심볼릭 링크 (Symbolic Link)
  - `inode` 공유 X, 경로 문자열을 저장함
  - 경로를 따라가서 원본 파일을 찾음
  - 원본이 삭제되면 더 이상 사용할 수 없음


## 7. Installation
- `--yes`: 저장된 기본 설정이나 기본값을 사용하여 프롬프트를 건너뜀
- 최신 브라우저(크롬, 엣지)를 지원함
- 폴리필 구성 방법 및 특정 브라우저를 대상으로 지원함
