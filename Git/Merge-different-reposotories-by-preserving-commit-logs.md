# 서로 다른 두 원격 저장소 병합하기

깃허브를 관리하다 보면 연관된 두 원격 저장소를 병합해야 할 때가 있다. 파일들만 옮겨서 새로 커밋하는 방법도 있지만 커밋 로그까지 함께 옮겨지지는 않는다. 이럴 때 사용할 수 있는 명령어가 있다.

## 병합 명령어

```bash
# 병합할 저장소와 유지할 저장소에 동일한 이름의 파일이 없도록 한다. (README.md 등)

$ git remote add <병합할 저장소 이름> <병합할 저장소 주소>
$ git fetch <병합할 저장소 이름>
$ git merge --allow-unrelated-histories <병합할 저장소 이름>/<병합하고 싶은 branch 이름>
$ git remote remove <병합할 저장소 이름>
$ git commit -m "Merge : <병합할 저장소 이름> into <유지할 저장소 이름>"
```

<br>

## 명령어를 살펴보자
### 1. 커밋 로그를 병합하기 위해 병합할 원격 저장소를 <병합할 저장소 이름>으로  추가한다.
```bash
$ git remote add <병합할 저장소 이름> <병합할 저장소 주소>  # 기본 형태
$ git remote add pre https://github.com/... .../pre  # pre: 병합할 저장소 예시
```

원격 저장소의 기본 별칭은 `origin`이며 우리는 이를 `git push origin master` 등 자주 쓰는 git 명령어에서 확인할 수 있다.

원격 저장소의 별칭에 기본값이 있다면 다른 별칭도 지정할 수 있을까? 그렇다면 다른 별칭은 어떻게 설정하며 어떨 때 사용할 수 있을까?

로컬 폴더와 원격저장소를 연결하는 명령어는 `git remote add origin <주소>` 였다. origin 대신에 지정하고 싶은 별칭을 적고, 원격 저장소의 주소를 적으면 로컬 폴더와 원격 저장소가 지정한 별칭으로 연결된다. 이 때 `git push 별칭 master`를 사용하면 별칭과 함께 지정한 원격 저장소로 커밋 기록이 업로드 될 것이다.

<br>

### 2. 원격 저장소에 저장된 커밋 기록들을 가져온다. (병합은 하지 않는다.)
```bash
$ git fetch <병합할 저장소 이름>
$ git fetch pre
```

`git pull`은 `git fetch`와 `git merge`가 합쳐진 명령어였다. 원격 저장소의 내용과 로컬의 최신 커밋 내용이 동일하다면 바로 pull을 해도 되지만 이 경우는 그렇지 않으므로 `git fetch`로 병합할 저장소의 커밋로그를 가져와 현재 로컬 저장소의 파일들과 비교하는 단계를 거친다.

이 때 충돌하는 파일이 있거나, 제외하고 병합하려는 파일이 있다면 `git reset HEAD 파일이름` 으로 병합할 목록에서 제외해준다.    
    
* HEAD는 현재 작업중인 가장 최근의 커밋이다. bash를 쓰던 중 `HEAD -> master` 또는 `origin/master`를 본 적이 있을 것이다. 이 때 `HEAD -> master` 는 master로 이동될 예정인 로컬의 최신 커밋이며 `origin/master`는 원격저장소의 최신 커밋이다.

<br>

### 3. 연관이 없는 기록들을 병합한다.
```bash
$ git merge --allow-unrelated-histories <병합할 저장소 이름>/<병합하고 싶은 branch 이름>
$ git merge --allow-unrelated-histories pre/master
```

단계 2에서 파일 충돌이 일어나지 않도록 파일명을 변경하거나 제외해줬다면 `git merge`로 두 저장소의 커밋기록을 병합한다.

단, 새로운 커밋은 이전의 커밋기록과 연결되어야 하므로 서로 다른 원격 저장소를 병합할 때에는 refusing to merge unrelate histories error가 발생하거나 아예 merge가 불가능하게 된다.

이 때 `--allow-unrelated-histories` 옵션을 사용하면 문제없이 병합이 완료된다. 해당 옵션은 말 그대로 관계 없는 (커밋) 기록을 병합할 수 있게 허용한다는 뜻이다. (커밋 기록이 달라 push가 불가능 할 때에도 이 옵션을 사용해 push 한다.)

<br>

### 4. 병합이 완료되었으니 병합된 원격 저장소를 지운다.
```bash
$ git remote remove <병합할 저장소 이름>
$ git remote remove pre
```

보통 두 원격 저장소를 병합하고 나면 병합된 원격저장소는 지우게 된다. 없앨 원격 저장소를 로컬과 연결해 둘 필요는 없으니 `git remote remove`로 지운다.

<br>

### 5. 병합 완료된 로그를 커밋한다.
```bash
$ git commit -m "Merge : <병합할 저장소 이름> into <유지할 저장소 이름>"
```

4번까지의 과정은 HEAD에서 일어난 것이니 아직까지는 `git log`로 병합된 커밋 로그를 확인할 수 없다. 그렇다고 병합이 실패한 것은 아니니 침착하게 커밋을 하면 병합 된 최종 커밋로그를 확인 할 수 있다.

<br>

### 6. 폴더 정리
이렇게 병합이 되었다면 어떤 폴더에서 bash를 열고 작업했든 병합한 저장소(코드예시에서 pre 저장소)의 파일과 폴더들이 `.git` 폴더가 존재하는 위치에 생성 될 것이다. 하나하나 이동해주면 된다.
* *지정한 폴더 안에 원격 저장소 안의 내용을 옮겨오는 방법을 찾고싶은데 아직은 방법을 모르겠다. 찾게되면 추가 할 것 (21-03-05)*

<br>
<hr>

## 참고
* [Git 저장소를 병합하는 방법(How to merge repositories in Git)
](https://mansoo-sw.blogspot.com/2017/08/git-repository-merge.html)
* [6. 병합할 때 발생하는 충돌 해결하기](https://backlog.com/git-tutorial/kr/stepup/stepup2_7.html)