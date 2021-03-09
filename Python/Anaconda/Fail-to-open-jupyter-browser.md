# jupyter notebook 설치 후 실행 시 자동으로 브라우저가 켜지지 않는 문제

설정파일을 수정하면 된다.
1. 위치: jupyter notebook이 설치 된 폴더인 `.jupyter`에서 `jupyter_notebook_config.py`를 찾는다.
2. 에디터에서 열고 `#c.NotebookApp.browser = ''` 항목을 찾는다. 기본적으로 주석처리 되어있을 것이다.
3. 주석처리를 해제하고 작은따옴표 (`''`) 안에 실행할 브라우저의 경로를 작성한다.
    * 이 때 경로구분자인 `\`를 `/`로 바꾸어야하며 마지막에 `%s`를 붙인다.
4. jupyter notebook을 실행하면 열리는 것을 확인 할 수 있을 것이다.


### 참고
[how to set jupyter notebook to open on browser automatically](https://stackoverflow.com/questions/55756151/how-to-set-jupyter-notebook-to-open-on-browser-automatically)
[Jupyter Notebook 시작시 브라우저가 자동실행 되지 않을 때](https://domini21.tistory.com/23)