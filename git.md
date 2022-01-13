# 220112

## Git

> 분산버전관리 시스템 (DVCS)

- 파일 만들기 : touch 파일명

- 폴더 만들기 : mkdir 폴더명



## 1. Git 저장소 만들기

```bash
$ git init
Initialized empty Git repository in C:/Users/채송지/Desktop/first/.git/
```

- `.git` 폴더가 숨김폴더로 만들어졌다! **버전이 기록되는 저장소**
  - 해당 폴더를 지우게 되면 모든 버전이 삭제되니까 주의할 것. 숨김폴더인 데에는 이유가 있구나...
- `(master)` git bash에 기능이 보이게 된다.



## 2. 버전 기록하기

### add

```bash
$ git add 파일명
$ git add a.txt
$ git add my_folder/
$ git add a.txt b.txt
```

### commit

```bash
$ git commit -m '커밋메시지'
```

- 커밋 메시지는 항상 버전의 내용(변경 사항)에 대해서 나타낼 수 있도록 기록한다.

### status

```bash
$ git status
```

- 현재 상태를 볼 수 있다.

```bash
# 커밋 할 변경사항들 (Staging area)
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    b.txt

# 커밋을 위해 준비되지 않은 변경사항 (Staging area X -> Working directory)
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   a.txt

# 트래킹 되지 않은 파일들 (Working Directory)
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        c.txt
```

- 파일을 조작하는 방법은 총 4가지

  - 생성 Create

  - ~~읽기 Read~~

  - 수정 Update

  - 삭제 Delete

    ```bash
    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
            deleted:    b.txt
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   a.txt
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
            c.txt
    ```

### git에서 관리하는 파일 변경사항 상태

- untracked : 커밋에 포함된 적 없는 파일
- tracked
  - modified : 커밋에 비해서 수정된 경우
  - staged : 커밋 되기 전 목록 (Staging area)
  - commited : 커밋 된 상태



### log

```bash
$ git log
```

- 커밋된 버전들을 볼 수 있다.





# 원격저장소 활용 (GitHub)

## 원격저장소 (remote repository) 추가

### 조회

```bash
$ git remote -v
origin  https://github.com/youthful15/first.git (fetch)
origin  https://github.com/youthful15/first.git (push)
```

### 추가

```bash
$ git remote add <원격저장소이름> <url>
$ git temote add origin https://github.com/username/repository.git
```

- ``origin`` : 일반적으로 많이 활용되는 원격저장소 이름

### 삭제

```bash
$ git remote rm <원격저장소이름>
$ git remote rm origin
```



## 원격저장소 push

> Update remote refs along with associated objects

```bash
$ git push <원격저장소이름> <브랜치이름>
$ git push origin master
```



## pull

> Fetch from and integrate with another repository or a local branch

```bash
$git pull <원격저장소이름> <브랜치이름>
$git pull origin master
```



## 원격저장소 clone

>  Clone a repository into a new directory

```bash
$git clone <원격저장소 주소>
$git clone https://github.com/username/repository.git
```

