# Git의 개념

## 1. Git이란?

Git은 **프로젝트의 상태 변화**(스냅샷)를 기록하고 관리하는 대표적 **분산 버전 관리 시스템**(Distributed Version Control System)이다.  
파일을 단순히 저장하는 것이 아니라, 시간의 흐름에 따라 어떻게 변경되었는지를 기록하는 것을 목적으로 한다.

Git에서 하나의 프로젝트는 여러 시점의 기록으로 구성되며,  
각 기록은 특정 시점의 상태를 나타낸다.  
이를 통해 프로젝트의 변화 과정을 체계적으로 추적할 수 있다.

## 2. Git의 기본 구조

Git은 프로젝트를 하나의 연속된 파일이 아닌,
여러 시점의 기록이 연결된 DAG(방향성 비순환 그래프)형태의 구조로 관리한다.

DAG(Directed Acyclic Graph, 방향성 비순환 그래프)는
방향성을 가지는 그래프이면서, 순환 구조가 존재하지 않는 형태를 의미한다.

![DAG그래프 구조](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FxshF9%2Fbtrrwe0lLeN%2FAAAAAAAAAAAAAAAAAAAAAEop-KPmURXnLRjYMpbV2IjmtBhS6kGPJbDMeN4WlmOS%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1777561199%26allow_ip%3D%26allow_referer%3D%26signature%3DRYNfpldu67gQRGkhhnQkkovq%252BEA%253D)

즉, 하나의 방향으로만 연결이 이어지며,
어떤 경로를 따라가더라도 다시 출발 지점으로 돌아오는 순환이 발생하지 않는다.

Git에선 미래 commit이 과거 commit을 가리킬 순 있지만 과거 commit이 미래 commit을 가리킬 수 없는 구조로 각 commit은 이전 commit을 부모(parent commit)로 참조하는 구조로써 DAG그래프 구조를 사용중이다.

Git의 작업 흐름은 아래 그림과 같이 단계적으로 진행된다.
사용자의 작업은 왼쪽에서 시작하여 단계적으로 오른쪽으로 이동하며,
변경 사항은 add, commit, push 과정을 거쳐 저장되고 공유된다.
또한 pull을 통해 원격 저장소의 변경사항이 다시 반영되며, 이러한 작업 과정은 반복적으로 이루어진다.

이처럼 Git은 여러 영역이 유기적으로 연결된 구조를 통해
프로젝트의 변경 과정을 체계적으로 관리한다.

![git 구조](https://cheris8.github.io/assets/images/ETC/GIT/git_structure.png)

### 2.1 Working Directory

**Working Directory**는 현재 작업 중인 깃 프로젝트 파일들이 있는 자신의 로컬 PC의 디렉토리입니다. 평소 작업하듯 프로젝트를 작업할 수 있습니다.

### 2.2 Staging Area

`git add` 명령어를 사용하여 **Working directory**에서 변경된 파일 중 `commit`할 파일을 선택하여 올리는 공간이며, `commit`전에 대기하는 공간이다.

### 2.3 Local Repository

`git commit` 명령어를 사용해 **Staging Area**에 있는 변경사항을 `commit`으로 기록하여 **Local Repository**에 저장한다. 이 저장소는 `commit`들의 히스토리를 관리한다.

### 2.4 Remote Repository

원격 서버에 위치한 저장소로, 다른 사용자와 협업하거나 백업을 위해 사용되며 `push/pull`을 통해 로컬 저장소와 동기화된다. 대표 예시로는 GitHub, GitLab 등이 있다.

## 3. Git 주요 명령어

Git은 명령어를 통해 파일의 상태를 기록하고 관리한다.  
각 명령어는 프로젝트의 변화 과정을 단계적으로 저장하는 역할을 한다.
다음은 Git에서 자주 사용되는 주요 명령어와 그 기능을 간략히 정리한 내용이다.

### 3.1 add

`add`는 변경된 파일을 **다음 `commit`에 포함될 파일을 선택하는 명령어**이다.  
즉, 작업한 내용을 바로 저장하는 것이 아니라,  
저장하기 전에 선택하는 과정이라고 볼 수 있다.

### 3.2 commit

`commit`은 **준비된 변경 내용을 하나의 기록으로 저장하는 명령어**이다.  
이때 하나의 commit은 특정 시점의 프로젝트 상태를 의미한다.
`commit` 시에는 변경 내용을 설명하는 메시지를 함께 기록하여, 이후 변경 이력을 이해하는 데 활용된다.

### 3.3 status

`status`는 **현재 작업 상태를 확인하는 명령어**이다.  
어떤 파일이 변경되었는지, 어떤 파일이 준비 상태인지 등을 확인할 수 있다.

### 3.4 log

`log`는 **지금까지의 기록을 확인하는 명령어**이다.  
이 명령어를 통해 프로젝트가 어떻게 변화해왔는지 확인할 수 있다.
commit 간의 연결 관계를 통해 프로젝트의 변화 흐름을 시간 순서대로 확인할 수 있다.

### 3.5 init

`init`은 **새로운 Git 저장소로 초기화하는 명령어**이다.  
프로젝트를 Git으로 관리하기 위해 가장 먼저 수행되는 단계이다.
이 명령어를 실행하면 해당 디렉토리에 .git 폴더가 생성되며,
Git이 프로젝트를 추적할 수 있는 상태가 된다.

### 3.6 clone

`clone`은 **원격 저장소를 복사하여 로컬 환경에 가져오는 명령어**이다.
기존 프로젝트를 처음 시작할 때 사용된다.

### 3.7 push

`push`는 **Local Repository에 저장된 commit을 원격 저장소로 업로드하는 명령어**이다.
이를 통해 변경사항을 다른 사용자와 공유할 수 있다.

### 3.8 pull

`pull`은 **원격 저장소의 변경사항을 가져와 로컬 저장소에 반영하는 명령어**이다.
이를 통해 최신 상태를 유지할 수 있다.

### 3.9 branch

`branch`는 **새로운 작업 흐름을 생성하거나 기존 브랜치를 확인하는 명령어**이다.
브랜치를 통해 서로 다른 작업을 독립적으로 진행할 수 있다.

---
