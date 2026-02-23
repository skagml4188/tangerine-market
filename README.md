# 🍊 감귤마켓 (Tangerine Market)

## 🛠 기술 스택
- **Environment:** Vite, React, TypeScript
- **Styling:** [팀에서 정한 스타일링 툴 입력, 예: Styled-components]
- **Deployment:** Netlify
- **Package Manager:** npm

## 🌿 브랜치 전략
안전한 협업을 위해 `develop` 브랜치를 중심으로 작업합니다.
- `main`: 최종 배포용 브랜치 (직접 커밋 절대 금지 ❌)
- `develop`: 개발 통합용 메인 브랜치 (이곳으로 PR)
- `feature/기능이름`: 각자 개인 작업 시 생성하는 브랜치 (예: `feature/login`, `feature/feed`)

## 🤝 팀 그라운드 룰 및 컨벤션

### 1. 코드 포맷팅
- 작업 전 반드시 **Prettier**와 **ESLint** 확장 프로그램을 설치해 주세요.
- VS Code 설정에서 `Format on Save`를 켜두어 저장 시 자동으로 코드가 정렬되게 합니다.

### 2. 절대 경로 사용
- 상대 경로 지옥(`../../../`)을 피하기 위해 절대 경로를 사용합니다.
- 예시: `import Button from '@/components/Button'`

### 3. 디자인 시스템 (메인 컬러)
피그마에 명시된 공통 컬러를 변수로 지정하여 사용합니다.
- **Primary (주황색):** `#F26E22` (포커스 된 선, 활성화 버튼 등)
- **Inactive (회색):** `#DBDBDB` (기본 선 색상 등)

## 📝 커밋 메시지 컨벤션
어떤 작업을 했는지 알아보기 쉽게 말머리를 통일합니다.
- `feat:` 새로운 기능 추가 (예: `feat: 로그인 이메일 유효성 검사 추가`)
- `issue:` 문제 발생 보고 (예: `issue: 로그인 오류 발생`)
- `fix:` 버그 및 에러 수정 (예: `fixed: 로그인 오류 수정`)
- `style:` UI/UX 디자인 변경 (CSS 등)
- `etc:` 기타 변경사항

## 🚀 로컬 실행 방법
```bash
# 1. 패키지 설치
npm install

# 2. 로컬 서버 실행
npm run dev
```

### Issue 기반 작업 플로우

> 페이지 배치 작업부터 이 플로우를 사용합니다.

#### 1. GitHub에서 Issue 생성

- **제목**: 해야 할 작업 작성 (기능 1~2개 정도 크기)
- **Description**: 제목으로 충분하므로 생략 가능

옆 창에 있음

- **Assignees**: 본인 등록
- **Labels**: 선택 사항 (필요시 추가)
- **Create** 버튼 클릭

#### 2. 브랜치 생성 및 체크아웃

옆 창에 있음

1. Issue 페이지에서 **Projects** → **No status**를 **In Progress**로 변경
2. **Development** 섹션의 **Create a branch** 클릭
3. 브랜치 이름 컨벤션에 맞게 지정
4. 생성된 명령어를 로컬에서 실행:

```bash
git fetch origin
git checkout 브랜치명
```

#### 3. 작업 및 커밋

Issue에 등록한 기능을 구현한 후:

```bash
git add .
git commit -m "feat: 구현한 기능 설명"
git push origin 브랜치명
```

#### 4. Pull Request 생성 및 병합

1. GitHub에서 **Create pull request** 클릭
2. **Merge pull request** 클릭
3. **Confirm merge** 클릭
4. **Delete branch** 클릭 (원격 브랜치 삭제)

#### 5. 로컬 정리

```bash
git checkout develop # ⚠️ main이 아닌 develop 브랜치로 이동!
git pull
git branch -d 브랜치명 # 다 쓴 로컬 브랜치 삭제
```

작업 완료!

#### 태그 형식 규칙

- **형식**: `<folder-file>` (kebab-case)
- **예시**:
  - `<input-button>` → `src/component/input/button.js`
  - `<user-profile-card>` → `src/component/user/profile-card.js`

#### 폴더/파일 이름 규칙

**폴더명**: 소문자, 하이픈 없이 작성 (예: `hodu`, `imput`, `user`)
**파일명**: 소문자, 하이픈 사용 가능 (예: `footer.js`, `button.js`, `profile-card.js`)

```
src/component/
├── input/             ✅ 올바른 폴더명
│   └── button.js      → <imput-button>
└── user-profile/      ❌ 잘못된 폴더명 (하이픈 사용 불가)