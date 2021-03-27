# 함수의 soft한 버전이란 무엇인가

프로그래밍인사이트 출판사의 `머신러닝, 딥러닝에 필요한 기초수학 with 파이썬`을 읽다가 아래 문구를 봤다.

> softmax 함수는 max 함수의 soft한 버전인 것 같다. 그러나 max 함수의 soft한 버전은 softplus 이며 softmax 함수는 argmax 함수의 soft한 버전이며 관행적으로 arg를 생략하여 softmax 함수가 된 것이다. (p72)

max 함수, softplus 함수, argmax 함수가 도대체 무엇이냐 이전에 궁금한 점이 있다. 함수의 soft한 버전은 도대체 뭘까

## functiona called 'soft' : differentiable function
한국어로 검색해도 잘 나오지 않는다. 일단 뭐라고 검색해야 할 지도 모르겠다. 일단 영문 위키에서 [rectifier](https://en.wikipedia.org/wiki/Rectifier_(neural_networks)) 를 검색해보라고 해서 검색해봤다.
- rectifier : 정류기
- 아니 놀라운 사실을 알았다. ReLU가 Rectified Linear Unit의 약자였다.
- 아니? 더 놀라운 사실을 알았다. max 함수가 뭔가 했는데 ReLU였다! ($ f(x) = max(0, x) $)

<br>
<center>
<img src="https://cdn-images-1.medium.com/max/800/1*w275Sin5bKAIaWBaJ6zXcA.png" width=400>
<br>
<i>이 그래프를 보길 원한 것 같다.</i>
</center>
<br>

책이 출간된 이후로 업데이트가 이루어졌는지 위키피디아에 올라온 그래프는 ReLU와 GELU였다. 그래프 형태를 봐서는 조금 더 완화된 개형을 가진 함수들을 soft함수라고 부르는 것 같은데 맞는지 확인하는 작업을 거쳤다.  
결론부터 말하자면 soft한 함수, 부드러운 함수는 미분이 가능하도록 변형한 함수다. ReLU함수와 argmax 함수의 공통점을 생각해보면 답이 나온다. 두 함수 모두 미분이 불가능한 함수다. (ReLU는 첨점, argmax는 큰 값의 인덱스를 반환한다는 함수특성)  
딥러닝에서 미분이 불가능하다는 특성은 치명적인데 역전파 backpropagation 가 불가능해 가중치를 업데이트 할 수 없으므로 학습읋 할 수 없기 때문이다.  
따라서 이를 미분 가능하게 완화한 함수를 사용하게 된다. 이 함수를 soft 함수라고 부른다.


### 참고
[Dying ReLU](https://brunch.co.kr/@kdh7575070/27)