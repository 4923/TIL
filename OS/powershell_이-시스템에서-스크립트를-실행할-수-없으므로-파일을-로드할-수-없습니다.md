# . : 이 시스템에서 스크립트를 실행할 수 없으므로 C:\Users\du\Documents\WindowsPowerShell\profile.ps1 파일을 로드할 수 없습니다. 자세한 내용은 about_Execution_Policies([https://go.microsoft.com/fwlink/?LinkID=135170](https://go.microsoft.com/fwlink/?LinkID=135170))를 참조하십시오.

### 보안 정책 문제
<br>

1. 문제 상황
    * HUFS Missing Semester - Shell & Shell Editors (1강) 실습 중 PowerShell 실행할 때 확인 됨

2. 원인
    * 에러보다는 보안 정책 문제에 가깝다. PowerShell을 실행할 때 발생하는 일반적인 문제

3. 해결
    * 보안 정책을 변경하면 해결된다. [참고](https://vast.tistory.com/116)
    1. 관리자 권한으로 Power Shell 실행
    2. `Get-ExecutionPolicy` 입력시 현재 컴퓨터의 사용자 권한 정책이 출력됨. 
    3. 권한을 RemoteSigned로 바꾸기 위해 `Set-ExecutionPolicy RemoteSigned` 입력
    4. 다시 `Get-ExecutionPolicy` 명령어 입력하여 사용자 권한이 RemoteSigned으로 변경되었는지 확인
    5. 재실행하면 동일한 에러가 발생하지 않는것을 확인할 수있다.

