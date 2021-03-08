# Commit Message 수정하는 방법

## 개요
커밋 기록은 저장소에 누적되기 때문에 특정 커밋만 수정할 수는 없다.
협업을 할 때 코드는 한 방향으로 수정되어야 하는데 과거의 커밋을 자주 수정한다면 협업하는 모든 사람들이 커밋 기록을 수정해야하는 불상사가 발생한다. 따라서 커밋 메시지는 꼭 필요한 경우가 아닌 이상 수정하지 않는 것이 좋다.
<br>

## 일반적인 커밋 로그 수정
```bash
git reset HEAD^N  # 가장 최신 커밋으로부터 N개까지 커밋을 취소하겠다.

# 다음 단계 N회 반복
git add "file1"
git commit -m "New Commit Message"
```
커밋 ID를 유지하기 위해 커밋을 되돌리고 새로 쌓는다.
<br>

## 커밋 로그 수정 방법 1 : amend
> 딱 하나만 바꿔야 할 때 파일을 지우고 추가하고 새로 커밋하는건 너무 귀찮다. 방법 1은 이 때 사용할 수 있는 방법이다.

```bash
git commit --amend -m "New Commit Message"
git push -f  # -f 옵션은 되도록 지양하는 편이 좋다.
```
amend는 약간 수정한다는 뜻이다. --amend 옵션은 git history를 조작하며 커밋 객체를 새로 만든다. 새 객체이기 때문에 commit ID가 바뀌므로 협업 시 주의해야한다.<br>

이 때, 커밋 객체란?<br>
* object = blob + tree + commit
    * blob : 파일 내용
    * tree : 디렉토리와 blob 정보 (파일 명), commit할 때의 index (stage) 를 스냅 샷 찍어 저장한다.
* 개별 git은 blob, tree, commit, tag 객체로 구성되어있다.
* 두번째 commit 객체부터는 이전 commit 객체를 저장하며 이를 parent 라고 한다.

## 커밋 로그 수정 방법 2 : rebase
> 하지만 커밋 로그가 수 많은 새 커밋 밑에 깔려있다면? 커밋을 죄다 되돌리기에도 번거롭고 amend를 사용할 수도 없다.
> 앞서 말한 것 처럼 덮어쓰는게 여러모로 좋지만 꼭 수정을 하고 싶다면 `rebase`를 사용하도록 하자.


<br>
<hr>

## 참고
[git amend](http://ohyecloudy.com/pnotes/archives/1983/)
[git object](https://sjh836.tistory.com/37)

