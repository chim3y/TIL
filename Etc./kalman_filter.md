## 칼만필터
* 물체의 측정값에 확률적 오차가 포함되고, 물체의 특정 시점에서의 상태는 이전 시점의 상태와 선형적인 관계를 가지고 있는 경우 적용 가능
* 과거 측정데이터(기존에 알고 있던 것)와 새로운 측정 데이터를 이용하여 노이즈 제거하여 새로운 결과 추정
* 예측(prediction) & 보정(correction) 반복수행
* 예측(prediction)
	* 이전 측정 업데이트에서 계산한 확률 분포와 모션 입력의 확률 분포를 이용 / 현재 상태의 분포를 예측
* 보정(correction)
	* 상태 예측 단계에서 예측된 현재 로봇위치에 대한 확률 분포, 현재 로봇 위치에서 측정한 관찰값의 확률 분포를 이용하여 사후 확률 분포를 업데이트