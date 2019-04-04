## Activation function / Optimization function
### activation function
* linearity 를 제거
1. sigmoid : 
	* sigmoid 함수(=로지스틱 함수)
		* 뉴런이 뱉어주는 값을 s 자 커브로 자연스럽게 활성화해줌
	![sigmoid](images/2_1.png "sigmoid")
		* exp 연산이라 무거움 --> 학습이 느려짐
	* sigmoid 의 그래프
	![sigmoid](images/2_2.png "sigmoid")
		* 값의 범위가 [0,1] --> 수렴 속도가 느려짐
	* sigmoid 1차미분 그래프
	![sigmoid](images/2_3.png "sigmoid")
		* x 값이 크거나 작을 때에 gradient 값이 지나치게 작아짐 --> 학습이 잘 안됨
2. hyperbolic tangent(tanh)
	* sigmoid 의 크기와 위치를 조절한 함수
	![tanh](images/2_4.png "tanh")
		* [-1, 1]
	* tanh 그래프
	![tanh](images/2_5.png "tanh")
	* tanh 1차 미분 그래프
	![tanh](images/2_6.png "tanh")
		* sigmoid 처럼 x 가 크거나 작아지면 gradient 가 0으로 작아짐
3. relu : 
	* f(x)=max(0,x)
	* 계산 복잡성이 낮음 --> sigmoid 나 tanh 대비 속도가 6배 빠름
	* 근데 0이하에서는 죽어버려서 이걸 써서 돌리면 10~20% 는 못쓰게 돼 버리는 것
3. leaky relu
	* f(x)=max(0.01x,x)
	* 죽지는 않아
4. parametric alpha - 이마저 학습하는 것


### optimization function
1. sgd - gradient 가 0이 되는 구간에서 멈출 것(왔다갔다가 심해져)
2. sgd+momentum - rho (관행적으로 0.1)
3. nestrove momentum
	실수할 가능성을 줄이기 위해
	velocity 방향으로 진행한 후 그 지점에서 gradient 를 구해서 그만큼을 더 가게 돼
	nestrove momentum 계산 복잡해져서 꼼수써 —> 즉석에서 계산하기 보다는 그 전 step 의 gradient 에 velocity 값을 넣어서 구해
4. adagrad - 무한대로 더해나가니깐 멈춰버릴 수가 있어
5. rms prob - adagrad 에 decay rate 적용
6. adam
	momentum + rms prob
	초기 값에 문제가 있을 거란ㄹ 데서 시작(초기 값이 분모가 너무 작아서 값이 뛰어버리는 일을 예방하기 위해 beta 사용


참고 : https://ratsgo.github.io/deep%20learning/2017/04/22/NNtricks/