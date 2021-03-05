# Udacity Commit Message Style Guide
 
들쭉날쭉한 커밋로그. 어떻게 해야 통일성 있게 작성할 수 있을까?<br>
[원본](https://udacity.github.io/git-styleguide/)을 간략하게 번역 후 정리했다.

## 메시지 구조

> **분류 : 제목**
> **본문**
> **꼬리말**

### Type / 분류
커밋의 주제와 부합하는 항목을 아래의 카테고리에서 하나를 고른다.

* feat : 새 기능 추가
* fix : 오류 해결
* docs : 문서 수정
* style : 코드의 내용을 변경하지 않는 한에서의 자잘한 수정 (코드구조, 세미콜론 추가 등)
* refactor : 코드 리팩토링
    * 코드를 이해하기 쉽고, 수정하기 쉽도록 만드는 것. 소프트웨어의 기능을 변경하지 않으며 코드의 구조에 집중한다.
* test : 코드 테스트, 리팩토링 테스트 추가 (프로덕션 코드 변경 없음)
* chore : 빌드 업데이트, 패키지 매니저 설정 (프로덕션 코드 변경 없음)

### Subject / 제목
* 50글자 이내로 작성한다.
* 첫 글자는 대문자로 작성한다.
* 마지막에 마침표를 붙이지 않는다.
* 현재시제와 명령어만 사용한다.

### Body / 본문 (선택)
* 부가 설명이 필요 할 때 작성한다.
* 제목과 본문 사이에 한 줄을 띄우고 작성한다.
* **어떤** 커밋을 **왜** 했는지 작성한다.
* **어떻게** 커밋했는지는 작성하지 않는다.
* 한 줄에 72글자를 넘지 않게 작성한다.

### Footer / 꼬리말 (선택)
* 출처나 이슈트래커 ID를 작성한다.

<br>

## 예시 커밋 메시지
> feat: Summarize changes in around 50 characters or less
>
More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.
>
Explain the problem that this commit is solving. Focus on why you
are making this change as opposed to how (the code explains that).
Are there side effects or other unintuitive consequences of this
change? Here's the place to explain them.
>
Further paragraphs come after blank lines.
>
 - Bullet points are okay, too
>
 - Typically a hyphen or asterisk is used for the bullet, preceded
   by a single space, with blank lines in between, but conventions
   vary here
>
If you use an issue tracker, put references to them at the bottom,
like this:
>
Resolves: #123
See also: #456, #789