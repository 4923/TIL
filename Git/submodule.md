# Submodule


## 개요
기본적으로 한 원격 저장소(repo)에는 하나의 `.git` 폴더만 존재할 수 있다. 그러나 다른 원격 저장소를 참고해야 할 때나, 저장해야 한다면 어떻게 해야겠는가? 

`README.md`에 해당 원격 저장소를 링크하는 방법도 있으나 임시 방편일 뿐 아니라 두 가지 원격 저장소를 동시에 사용할 수는 없다는 단점이 있다.


이 단점을 해결할 수 있는 기능이 `submodule` 이다. **여러개의 프로젝트를 동시에, 그러나 개별적으로 개발해야 할 때 사용**한다.

## 방법

사용방법은 간단하다.

1. 먼저 두 원격저장소를 준비한다. 상위의 저장소를 A, 포함시킬 저장소를 B라고 하겠다.<br>저장소 A에서 저장소 B로 접근할 수 있게 하는 것이 목표다.
2. 저장소 A가 로컬(local)에 존재한다면 `.git`이 위치한 경로로 이동하고, 그렇지 않다면 `clone` 등을 통해 로컬로 해당 파일을 옮겨온다.
    ```bash
    # 로컬에 있을 경우 생략
    $ git clone (URL of repository A)
    ```
3. 추가하기를 원하는 저장소의 URL을 `submodule add` 명령어로 추가한다.
    ```bash
    # 상위 저장소(저장소 A)에서 사용하는 명령어임에 주의하자.
    # directory name은 submodule로 추가되는 저장소 B를 부를 방법이다. 저장소 B의 본래 이름에는 영향을 끼치지 않는다.

    $ git submodule add (URL of repository B) (directory name)
    # 예) git submodule add https://github~ repository-B
    ```
    * 이렇게 `submodule add` 명령어를 사용하면 `.git`에 `.gitmodules` 파일이 생성된다. 이 파일은 서브디렉토리와 하위 프로젝트 URL의 매핑 정보를 담은 설정파일이다. *[출처](https://git-scm.com/book/ko/v2/Git-도구-서브모듈)*

## 참고
1. [Git - 서브모듈](https://git-scm.com/book/ko/v2/Git-도구-서브모듈)