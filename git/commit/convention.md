# Git Commit Convention에 대한 가이드라인

# Git Commit Convention 이란 무엇일까요?

```
🤔 기능 구현하기도 힘든데, 커밋 메시지… 그게 중요한가요?
```

우리는 협업 과정에서 **버전 관리 툴**을 사용합니다. 소스코드의 공유, 소스코드의 백업 등 셀 수도 없이 다양한 이유가 있겠지만 **‘이력 관리’**라는 강력한 기능을 활용하기 위해 버전 관리 툴을 사용하죠.

둘 이상이 소프트웨어 개발에 참여하다보면 서로가 개발한 부분이 `Conflict`가 발생하기도 하고, 어제까지만 해도 이슈 없이 동작했던 부분이 오늘 확인해보면 갑자기 안되기도 합니다.

이럴 때 보통 어디부터 잘못 되었나 History를 살펴봅니다. Git에는 History를 Commit Message를 통해 확인할 수 있습니다. 이렇게나 중요한 History를 규칙 없이 적었었고, 이런 문제를 해결하기 위해 해외의 개발자들이 무수한 논의 끝에 Commit Message 작성 규칙을 만들었습니다. 개발자들이 Commit Convention을 지키는 것은 당연한 능력이 되었고, 채용에도 중요한 요소로 자리잡았습니다.

Git Commit Message를 잘 작성해야 하는 이유가 또 있습니다.

```
1. 더 좋은 커밋 로그 가독성
커밋 메시지를 메뉴얼에 따라 적성하면, 커밋 로그의 가독성이 높아집니다.

2. 더 나은 협업과 리뷰 프로세스
커밋 메시지는 협업에서 매우 중요합니다. 협업을 하는데 커밋 메시지를 중구난방으로 작성한다면, 팀원이 이 코드를 왜 작성했는지에 대해 파악할 수 없습니다. 따라서, 협업을 할때에 특히 더 신경써서 커밋 메시지를 작성해주세요.

3. 더 쉬운 코드 유지보수
커밋 메시지가 잘 작성되어있으면, 내가 어떤 코드를 어디에 작성했는지 쉽게 찾을 수 있기 때문에 유지보수가 쉽습니다.

```

# 좋은 Git Commit Message를 작성하기 위한 6가지 약속

`본 약속은 영어 작성 기준입니다.`

1. 제목과 본문을 한 줄 띄워 분리하기
2. 제목은 영문 기준 50자 이내로 (한글 기준으로 70자 이내)
3. 제목 끝에 `.` 금지
4. 제목은 `명령조`로
5. 본문은 영문 기준 72자마다 줄 바꾸기
6. 본문은 `어떻게` 보다 `무엇을`, `왜`에 맞춰 작성하기

# Git Commit Message의 규칙

커밋 메시지는 아래와 같은 구조로 이루어집니다.


`타입(적용 범위-선택사항):` `설명`

`본문(선택사항)`

`꼬리말(선택사항)`



- 타입: 어떤 의도로 커밋했는지를 type에 명시합니다.
- 적용 범위: 코드베이스가 적용되는 영역을 기술하는 명사로 괄호로 감싸져야 합니다
- 본문: 최대 50글자가 넘지 않도록 하고 마침표는 찍지 않습니다. 영문으로 표기하는 경우 동사(원형)를 가장 앞에 두고 첫 글자는 대문자로 표기합니다.
- 본문: 긴 설명이 필요한 경우에 작성합니다. 어떻게 했는지가 아니라, 무엇을 왜 했는지를 작성합니다. 최대 75자를 넘기지 않도록 합니다.
- 꼬리말: issue tracker ID를 명시하고 싶은 경우에 작성합니다.

그렇다면, 메시지 구조를 어떻게 더 명확하게 작성할 수 있는지, 살펴보겠습니다.

## 제목(subject, 필수)

### WHAT 무엇을 했는지

### 형태

`타입(적용 범위): 설명`

- : 과 설명사이에 한개의 공백을 유지하고 작성할 것
- type은 대문자나, 소문자 하나로 통일을 권장
- 설명 일관되게 통일(~기능 구현, ~작성, ~출력, ~삭제, ~생성, ~수정..)
- 명령형, 현재형으로 작성하기
- 끝에 `.` 금지
- 적용 범위는 추가적인 문맥 정보를 제공하기 위한 목적으로 작성

```markdown
feat: 회원가입 기능을 개발함 (x)
feat(api): 회원가입 기능 개발 (o)
feat: 회원가입 기능 개발. (x)
```

### 타입(type)

- feat: 새로운 기능(기능 구현)
- fix: 버그 수정
- docs: documentation 변경
- style: 코드 의미에 영향을 주지 않는, 코드 스타일에 관련된 변경 사항(포맷, 공백, 빼먹은 세미콜론, 함수 이름 변경, 줄간격, 파일 이름, 의미없는 주석 삭제)
- refactor: 리팩토링에 대한 커밋(버그를 수정하지 않고 기능을 추가하지 않는 코드 변경)
- chore: 패키지 매니저 설정할 경우, 코드 수정 없이 설정을 변경(eslint, prettier…패키지 설정), 이외에도 특정 영역에 들어가기 애매한 잡다한 작업들

```markdown
feat: 회원가입 기능 개발
fix: 회원가입 시 사용자 이름이 안보이는 이슈
```

## 내용(body, description, 선택)


#### WHY 왜 이 커밋을 작성하게 되었는지, 왜 그렇게 했는지


- 일반적으로 제목까지만 기재하면 충분하기 때문에 선택사항으로 기재합니다.
- 약간의 설명이나 전체 문맥을 설명해야 할 때만 사용합니다.
- commit 메시지는 간단히 요약한 내용을 작성하고, 부족한 부분이 있으면 description 에 추가합니다.
- 작성할 때는 커밋에 대해 어떻게(HOW)가 아닌 무엇(WHAT) 그리고 이유(WHY)에 대해 설명을 합니다.
- 현재형으로 작성합니다.
- 본문을 작성하고 싶을 때는, 제목과 본문을 한 줄 띄워서 분리합니다.

## 마무리(Footer, 선택)

이슈트래킹을 위해 ID 등을 참조할 때 사용합니다.(#382, #188 등…)

```markdown
Resolved: #110
```

# 좋은 Commit 예시

```markdown
feat(auth): 회원 가입 기능 구현

SMS, 이메일 중복확인 API 개발

Resolves: #123
Ref: #456
Related to: #48, #45
```

# 참고 자료

[Conventional Commits](https://www.conventionalcommits.org/ko/v1.0.0/)
