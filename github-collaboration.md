# GitHub 협업 방법 (Collaboration Workflow)

## 1. GitHub 협업의 필요성

팀 프로젝트에서는 다음과 같은 문제가 자주 발생한다.

- 버전 관리 혼란  
- 변경 이력 추적 어려움  
- 협업 비효율  

GitHub는 이러한 문제를 해결하기 위한 **협업 플랫폼**이다.  
특히 다음 기능을 하나로 통합한다.

> **버전 관리 + 협업 + 문서화 + 작업 관리**

→ 여러 개발자가 동시에 작업해도 안정적으로 프로젝트를 유지할 수 있다.  

---

## 2. 협업의 시작 (Collaborator & Fork)

### 2.1 Collaborator

Repository에 팀원을 추가하여 협업을 시작한다.

- `Write` 권한 → 코드 수정 및 push 가능  
- `Admin` 권한 → 저장소 전체 관리  

→ 팀 프로젝트에서는 **Collaborator 방식**을 사용한다  

---

### 2.2 Fork

Fork는 다른 사람의 저장소를 **내 계정으로 복사**하는 기능이다.

- 원본 저장소에 영향을 주지 않음  
- 자유롭게 수정 가능  
- Pull Request로 기여 가능  

→ **오픈소스 협업**에서 주로 사용  

---

## 3. Clone (저장소 복제)

Clone은 원격 저장소를 **내 컴퓨터로 복사**하는 것이다.

- 로컬에서 자유롭게 작업 가능  
- 원격 저장소와 연결 유지  
- `push` / `pull`로 동기화  
→ 협업의 **첫 단계**  

---

## 4. Branch 기반 협업 구조

![Git Branch Workflow](https://softwareplanetgroup.co.uk/wp-content/uploads/2020/11/Git-flow-03.png)

GitHub 협업에서는 **main 브랜치**를 기준으로 작업한다.

- `main` → 항상 **안정 상태 유지**  
- `feature branch` → 기능 개발  

→ 모든 작업은 **branch에서 수행 후 merge**  

---

## 5. 협업 흐름 (Workflow)

![Git Workflow](https://git-scm.com/book/en/v2/images/basic-branching-3.png)

일반적인 협업 흐름은 다음과 같다.

1. Repository **clone**  
2. 새로운 **branch 생성**  
3. 작업 후 **commit**  
4. 원격 저장소에 **push**  
5. **Pull Request 생성**  
6. 리뷰 후 **merge**  

→ GitHub 협업의 **표준 프로세스**  

---

## 6. Issue (작업 관리)

Issue는 프로젝트의 모든 작업을 관리하는 도구이다.

- 할 일을 **티켓 형태**로 생성  
- 담당자 지정 (`Assignee`)  
- 진행 상태 추적  

→ 작업 흐름  
```
Issue 생성 → 개발 → PR → 완료
```

PR과 연결하여 **작업 이력을 명확하게 관리**할 수도 있다.  

---

## 7. Pull Request (PR)

Pull Request는 작업한 내용을 `main` 브랜치에 반영 요청하는 과정이다.

### 주요 기능

- 코드 리뷰  
- 변경 사항 공유  
- 협업 커뮤니케이션  

→ 협업의 **핵심 단계**  

---

## 8. Merge (병합)

Merge는 branch의 작업을 `main`에 반영하는 과정이다.

### Merge 방식 비교

| 방식 | 특징 |
|------|------|
| **Merge Commit** | 이력 유지 (복잡) |
| **Squash Merge** | 커밋 하나로 압축 (깔끔) |
| **Rebase Merge** | 선형 구조 (충돌 위험 有) |

→ 팀 프로젝트에서는 **Squash Merge**를 많이 사용한다  

---

## 9. 충돌 해결 (Merge Conflict)

![Merge Conflict](https://docs.appsmith.com/img/seperate-conflicts-git.png)

같은 파일의 같은 부분을 수정하면 충돌이 발생한다.

```
<<<<<<< HEAD
현재 코드
=======
다른 코드
>>>>>>> branch
```

### 해결 방법

1. 충돌 부분 직접 수정  
2. 다시 `commit`  후 `push`

---

## 10. Wiki (문서화)

Wiki는 프로젝트의 **문서 관리 공간**이다.

- 개발 환경 설정  
- 팀 규칙 및 가이드  
- API 문서  

→ 코드 외의 정보 관리  

---

## 11. Projects (작업 시각화)

Projects는 작업 흐름을 **시각적으로 관리**하는 도구이다.

- `To Do / In Progress / Done` 구조  
- Issue 및 PR 연결  
- 진행 상황 한눈에 확인  

→ 협업 상태를 직관적으로 파악 가능  

---

## 12. 정리

GitHub 협업의 핵심 요소

- **Clone** → 프로젝트 복제  
- **Branch** → 작업 분리  
- **Commit** → 변경 기록  
- **Issue** → 작업 관리  
- **PR** → 협업 및 리뷰  
- **Merge** → 코드 통합  
- **Wiki** → 문서 관리  
- **Projects** → 진행 관리  

> GitHub는 협업 과정을 **모두 기록하는 통합 플랫폼**이다
