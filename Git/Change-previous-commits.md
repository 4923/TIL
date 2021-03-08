# How to modify Commit Message

## 개요
커밋 기록은 저장소에 누적되기 때문에 특정 커밋만 수정할 수는 없다.
협업을 할 때 코드는 한 방향으로 수정되어야 하는데 **push 된**과거의 커밋을 자주 수정한다면 협업하는 모든 사람들이 커밋 기록을 수정해야하는 불상사가 발생한다. 따라서 **push 된 커밋 메시지**는 꼭 필요한 경우가 아닌 이상 수정하지 않는 것이 좋다.
<br>

## 일반적인 커밋 로그 수정
```bash
git reset HEAD^N  # 가장 최신 커밋으로부터 N개까지 커밋을 취소하겠다.

# 다음 단계 N회 반복
git add "file1"
git commit -m "New Commit Message"
```
커밋 ID를 유지하기 위해 커밋을 되돌리고 새로 쌓는다.
<br><br>

## 커밋 로그 수정 방법 1 : amend
> 딱 하나만 바꿔야 할 때 파일을 지우고 추가하고 새로 커밋하는건 너무 귀찮다. 방법 1은 이 때 사용할 수 있는 방법이다.

### 1. 수정
```bash
git commit --amend -m "New Commit Message"
git push -f  # -f 옵션은 되도록 지양하는 편이 좋다.
```
amend는 약간 수정한다는 뜻이다. --amend 옵션은 git history를 조작하며 *커밋 객체*를 새로 만든다. 새 객체이기 때문에 commit ID가 바뀌므로 협업 시 주의해야한다.<br>

**이 때, 커밋 객체란?**
git commit 명령어로 생성하는 객체이며 커밋 메타데이터가 담겨있다.
* object = blob + hash of tree + hash of parent commit + User info + commit message
    - blob : 파일 내용. 메타데이터는 저장되지 않는다.
    - tree : 특정 시점의 한 디렉토리를 표현.
        디렉토리와 blob 정보 (파일 명), commit할 때의 index (stage) 를 스냅 샷 찍어 저장한다.
    - hash of parent commit : 두번째 commit 객체부터는 이전 commit 객체를 저장하며 이를 parent 라고 한다. 이전 커밋을 가리키는 포인터로 이해하면 쉽다.

amend 할 경우 이전 객체는 사라지지 않으나 최종 커밋인 HEAD는 amend 한 커밋 객체를 가리킨다.
<br>

### 2. push
만약 커밋에서 작은 오타나 사소한 내용을 고칠 경우 커밋 메시지를 수정하지 않도록 `git commit --amend --no-edit`을 사용한다. 이 명령어를 사용하면 커밋 메시지를 수정하는 편집기가 열리지 않는다.<br>
다시 말하지만, ID가 달라지므로 이미 push한 commit을 amend 하지 않도록 주의한다.<br>
불가피하게 push 된 로그를 변경해야 한다면 `git push -f` 처럼 `-f` 옵션을 사용해주자.
<br><br>

## 커밋 로그 수정 방법 2 : rebase
> 하지만 커밋 로그가 수 많은 새 커밋 밑에 깔려있다면? 커밋을 죄다 되돌리기에도 번거롭고 amend를 사용할 수도 없다.
> 앞서 말한 것 처럼 덮어쓰는게 여러모로 좋지만 꼭 수정을 하고 싶다면 `rebase`를 사용하도록 하자.

<br>

### 1. `rebase`
```bash
git rebase HEAD~N
# -i 옵션을 추가하면 대화형 모드로 reabse 가능하다
```

특정 시점(~N개 전 커밋)부터 HEAD 까지의 커밋을 한번에 rebase, 즉 index (stage area)로 되돌린다.
<br>
위 명령어를 실행하면 이전까지의 커밋들이 객체를 유지한 채로 index로 돌아오고, 커밋 메시지들이 담긴 스크립트가 편집기에서 열린다.<br>

* `git log`와는 반대 방향으로 정렬됨에 주의하자. (오래된 커밋이 가장 위)

<br>

### 2. 수정 (`pick` -> `edit`)
수정하고자 하는 커밋을 찾고 `pick`을 `edit`으로 수정하면 index로 rebase 되었던 커밋들이 다시 push 되다가 `edit`으로 수정한 커밋에서 멈춘다.<br>

이 때 bash의 안내에 따라 `git commit --amend`를 입력하면 커밋 메시지를 수정할 수 있는 편집 창이 나타난다.<br>

메시지를 수정 하고 저장한 후 편집기를 끈다.<br>

<br>

### 3. 마저 커밋한다 (`--continue`)
다시 `git rebase --continue` 를 입력하면 rebase 되었던 커밋 객체들이 커밋된다.

<br>

## 참고
* [git amend](http://ohyecloudy.com/pnotes/archives/1983/)
* [git object](https://sjh836.tistory.com/37)
* [Git 내부 구조를 알아보자 (1) — 기본 오브젝트](https://medium.com/happyprogrammer-in-jeju/git-내부-구조를-알아보자-1-기본-오브젝트-81b34f85fe53)
* [Git 히스토리 단장하기](https://git-scm.com/book/ko/v2/Git-도구-히스토리-단장하기)