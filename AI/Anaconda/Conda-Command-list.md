# Conda

### conda 관리
```bash
# 현재 conda의 정보
conda info

# conda 업데이트
conda update conda
```


# 가상환경

### 가상환경 생성 및 삭제

```bash
# 가상환경 생성
# 가상환경 이름은 설치한 패키지 또는 파이썬의 버전으로 짓는 것이 좋다
conda create -n '가상환경이름' python='설치를 원하는 버전'
conda create -n python36 python=3.6

# 가상환경 삭제
conda env remove -n '가상환경이름'
conda env remove -n python36
```

### 가상환경 관리

```bash
# 가상환경 목록 확인
conda env list

# 가상환경 활성화
conda activate '가상환경이름'
conda activate python36

# 가상환경 비활성화
conda deactivate


# 가상환경 복제
conda create --clone '복제할 가상환경이름' -n '새 가상환경 이름'
conda create --clone python36 -n python36-clone
```

### 패키지 관리
```bash
# 가상환경에 설치된 패키지 확인
conda list

# 현재 가상환경에 패키지 설치
# 패키지 이름을 공백으로 구분하여 나열하면 여러개를 설치할 수 있다.
conda install '패키지 이름'
conda install tensorflow
conda install tensorflow numpy

# 현재 활성화 되지 않은 다른 가상환경에 패키지 설치
conda install -n '가상환경이름' '패키지 이름'
conda install -n tensorflow2 tensorflow

# 패키지 업데이트
conda update '패키지 이름'
conda update tensorflow

# 모든 패키지 업데이트
conda update -all

# 패키지 삭제
conda remove- n '가상환경이름' '패키지 이름'
conda remove -n tensorflow2 tensorflow

# 패키지 유무, 버전 확인
conda list '패키지 이름'
conda list tensorflow
```


##### 참고
[꼭 알아야 할 conda 명령어 정리](https://bskyvision.com/713)