# issue를 써보자
> `Activity overview : Commits 100%` 에서 벗어나기 프로젝트

일반적으로 github project에서 issue는 아래 단계를 따른다. 

```
1. 문제상황 발생
2. issue 발급 : create issue
3. issue 해결 : 작업 후 PR, code review
4. issue 반영 : merge
```

## 갑자기 웬 issue?
이 기능은 협업 과정에서 주로 사용한다고 알고 있는데 Django Project를 진행할 때마다 문제상황을 commit message에 기록하는것도 한계가 있고 무엇보다 문제가 발견됐을 때 마다 그 자리에서 해결하는게 슬슬 어려워지다 보니 이런 문제/issue들을 모아두고 관리할 수 있는 기능의 필요성을 느끼게 되었다.

## template을 만들어보자
프로젝트 관리를 위한 기능이니 여러사람이 사용해야 하고, 그렇게 되면 당연히 정해진 형식이 필요하다. 이걸 위한 기능이 **template**이다.  
repository settings/Features/Issues에서 관리할 수 있으며 기본적으로 `Bug report`와 `Feature request` template을 제공하며 사용자가 형식을 정의 할 수도 있다.

- template 작성도 커밋으로 집계된다. 
- 한 번에 여러 template을 생성하고 수정할 수 있는데 반드시! **Propose changes**를 눌러야 한다. 하지 않으면 애써 작성한 형식이 다 날아간다. (ㅠㅠ)

## issue를 만들어보자
issue는 repository의 issue탭에서 만들 수 있다.  
repository에서 issue를 사용하지 않게 만들 수도 있는데 내가 알기론 별도의 설정 없이 저장소를 열 때 issue도 기본적으로 열린다.  
상단 바의 issue탭으로 들어가서 `New issue`를 클릭하면 새로운 issue를 발급할 수 있다.

이 때 template을 작성해두었다면 골라서 issue를 생성할 수 있다.  

제목과 본문 말고도 책임자(Assignees), 분류(Labels), 관련 Project(Projects), 세부분류? (Milestone) 등을 지정할 수 있다.
- 이것도 template에서 미리 지정할 수 있는데, 지정해두었다면 issue 생성과 동시에 기본값이 설정된다. 편리하다!


## issue를 해결하자 : 닫기
문제를 해결하면 된다. 한 issue 안에서 comments를 달 수도, emoji를 남길수도 있다.  
issue 안에서 일어나는 모든 변화는 (label 변경 등) commit 처럼 내부에 기록된다.  
(그리고 본문에서 `:` 콜론을 쓰면 바로 이모티콘을 쓸 수 있어 편하다.)

문제를 해결했다면 issue를 닫아야 하는데 웹에서 그냥 닫을 수는 없고 comment와 함께 닫아야 하는 것 같다.  

comment 할 것이 없다면 commit message로 닫을 수도 있다. commit할 때 **종료를 의미하는 키워드**를 입력하고, **issue 번호**를 기입했다면 자동으로 issue를 종료한다.

- 종료 키워드 : close, fix, resolve
    - 각 단어의 변형 (closed, fixes ...) 또한 인식한다.