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

![Git Branch Workflow](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Git_branching_diagram.svg/800px-Git_branching_diagram.svg.png)

GitHub 협업에서는 **main 브랜치**를 기준으로 작업한다.

- `main` → 항상 **안정 상태 유지**  
- `feature branch` → 기능 개발  

→ 모든 작업은 **branch에서 수행 후 merge**  
