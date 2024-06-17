<h1>🚩 TimeSeries_Project </h1> 


**애플 주식 & 금 주식 주가 예측 프로젝트**  

<img src='https://github.com/dosel70/TimeSeries_Project/assets/143694489/f9b0a342-d637-498b-b5f2-6abe13dd74de' width="800px">    

<h1> Apple & Gold Time Series Project</h1>

---

<h2>📃 시계열데이터 프로젝트 목차</h2>

- 데이터분석을 통한 애플(AAPL)과 금(GLD) 주가 분석 시각화
- ACF, PACF를 통한 전처리 진행
- ARIMA , auto_arima 을 사용한 모델 평가 진행
- DeepLearning Propet을 사용하여 미래 주가 예측
- 느낀점
> 이번 프로젝트는 시계열데이터분석을 활용하여 애플 주가 전망을 분석하고, 금 주가와 비교분석하는 프로젝트 입니다.

---

<h3>📌 yfinance 라이브러리(금융데이터 제공 라이브러리) 에서 종목 선택 : AAPL(애플), GLD(금)</h3>

<details><summary>👉 코드 확인</summary>
<br>  
  - 📌 yfinace 라이브러리에서 2010년 1월 1일경부터 기록된 애플과 금 주식 데이터를 불러옵니다.  
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/7b672a07-5a21-442e-8e78-612aba8ffc54" width="650px">  
</details>


---

<h3>📌 주식 현황 그래프 & 차분 그래프 시각화</h3>

<details><summary>👉 주식 데이터 시각화 확인</summary>
<br>
  - matplotlib에서 pyplot을 사용하여 시각화를 진행하였습니다.    
  
  #### 주식 현황 그래프 (애플(Blue), 금(Orange))  
  
   <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/75171c7e-43ad-4087-867e-061c715a1615" width="650px">
    
  #### 차분 그래프 시각화
   <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/75894a6b-a3b0-4f70-871a-16c855fc66a8" width="650px">  

  ### 주식현황그래프 & 차분 그래프 시각화 분석 결과
- 분석 결과 금, 애플 모두 우연변동 형태의 그래프를 보이지만, 시간이 지날수록 두 그래프 모두 상승세를 보일 것으로 판단됩니다.
- 분산 그래프의 경우 애플과 같은 대기업은 제품의 출시 시기와 같은 변수에 의해 분산이 일정하지 않아서, 안정성이 떨어지는 모습을 보입니다. 그에 반해 금의 경우, 애플에 비해 분산의 차이가 크지 않기때문에, 이 부분을 참고하여 안정성이 애플보다는 높다는 것을 알 수 있습니다.

</details>


<h3>📌 주가 변화율 & 금융시장의 수익률 시각화</h3>

<details><summary>👉 데이터 시각화 확인</summary>
<br>
  - 'pct_change()' 함수를 사용하여 주가 데이터에 대한 일간 변화율(수익률)을 계산하고, 그 변화율의 평균값을 막대 그래프로 시각화합니다.  

  #### 변화율 그래프 시각화
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/18a1ca10-cc78-42ed-8a24-d9bc786e3d15" width="700px">  

  #### 시각화 결과  
- 변화율 그래프를 시각화한 결과 역시 APPLE 기업의 분산의 변화폭이 높은 것을 알 수 있으며, 금은 그에 비해 안정적임을 확인 할 수 있습니다.

  #### 로그치환을 사용한 shift 연산 기능 수행
  
  - 수익률 계산에 있어서, 편의성을 위해 로그 치환을 실시하고, 과거 데이터와 현재 데이터를 비교하기 위해 shift(1)을 사용합니다. 이 과정을 통해 주식의 로그 수익률을 계산할 수 있습니다. 로그 수익률은 주식의 가격 변동을 분석하는 데 있어 여러 가지 장점이 있으며, 이를 통해 더 정교한 분석이 가능합니다.
    
  #### 코드 이미지
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/3cbe6f9e-a6e0-4c4c-9f55-a21c2c2f2792" width="600px">  

  #### Apple, Gold 수익률 분산폭 시각화
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/3e5fad8d-d878-4c5c-a6c3-7706ec66b918" width="600px">  

  #### ✨ 위 시각화 그래프를 통해 금과 애플 간의 수익률 분산 차이를 더 뚜렷하게 볼 수 있었습니다.
</details>

<h3>📌 애플, 금 주식데이터의 일간,월간 수익률 시각화 </h3>

<details><summary>👉 데이터 시각화 확인</summary>  

#### Histogram 시각화
<br>
<img width="600"  src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/9f928ab8-6f73-48ba-8c4a-93977210d5f0">  

#### 애플과 금 금융데이터 모두 정규분포화된 형태를 띄고 있는 것을 확인하였습니다.  

#### 일간 수익률 & 월간 수익률 시각화  
일간 수익률
<br>  

<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/27755e72-1625-4105-b910-d30f97c206e7" width="650px">  

월간 수익률
<br>

<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/e2a6a774-f0fe-4a59-9ba0-39d027fa3573" width="650px">  

#### 분석 내용  
- 애플과 금에 대한 금융 데이터를 일간 수익률과 월간 수익률로 나눠서 시각화한 결과, 애플 같은 경우 시간이 지날수록 계속 상승하는 추세를 보이지만,
- 금의 경우, 애플에 비해 큰 변화폭이 없고, 수익률이 애플에 비해서 많이 낮은 것을 확인 할 수 있었습니다.

 
  <details> <summary> <h3>💡금이 애플에 비해서 수익률과 변화폭이 적은 이유? <h3> </summary>
  금과 애플 주식의 수익률 차이는 그들의 본질적 특성, 변동성, 그리고 시장의 반응 차이에 의해 설명될 수 있습니다.  
  금은 안정적인 자산으로서의 역할을 하지만, 높은 수익률을 제공하지 않습니다.   
  반면에 애플 주식은 높은 변동성과 함께 높은 수익률을 제공할 수 있습니다. 투자자는 이러한 차이를 이해하고, 자신의 투자 목적과 리스크 허용 범위에 따라 자산을 선택하는 것이 중요합니다.
  </details>
</details>

---

<h3>📌 전처리 진행 (ACF , PACF)</h3>  

- 데이터 시각화를 어느정도 진행 후에 ACF 분석과 PACF 분석을 통해 각기 다른 방식으로 자기 상관(autocorrelation)을 분석하였습니다.

- **AAPL(애플)**
  
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/6e1e417e-8d97-484c-bd3c-b501ca7f06da" width="600px">

- ACF 그래프를 보면, 시차가 증가함에 따라 천천히 감소합니다. 이러한 결과를 볼 때, 시차가 증가함에 따라 천천히 감소하는 패턴은 데이터가 불안정데이터임을  나타냅니다. 이는 평균이나 분산이 시간에 따라 일정하지 않음을 의미합니다.
    
- 1차 차분을 한 뒤 PACF를 확인한 결과, 첫 번째 시차에서만 높은 값을 보이고 이후에는 값이 급격히 감소하는 패턴으로, 1차 차분이 데이터의 안정화에 도움이 되었음을 알 수 있습니다.

- **GLD(금)**

  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/b26850e6-c9ce-4994-95ac-8e5b0738580d" width="600px">
    
- 금에 대한 ACF 그래프의 경우도 마찬가지로 시차가 증가함에 따라 천천히 감소하는 패턴을 볼 수 있으며, 마찬가지로 불안정 데이터임을 나타내고 있습니다.
    
- 1차 차분을 한 뒤 PACF 결과를 확인한 결과도 마찬가지로 1차 차분이 데이터의 안정화에 도움이 되었음을 알 수 있습니다.
    
- 그 다음 데이터의 패턴을 쉽게 파악할 수 있도록 Moving Average(이동평균)을 사용하여, 데이터의 변동성을 안정화 시키며, 이에 대한 최소값,최대값,중앙값,평균값을 같이 구하도록 하겠습니다.
      
<details><summary>👉 코드 확인</summary>

<br>

- 애플(AAPL) 주가 데이터에 대해 20일의 이동평균을 사용하여 최소,표준편차,최대,중앙값 과 같은 여러 통계적 값을 계산하였고, 금(GDL)의 경우에도 이와 동일한 방법으로 사용하였습니다.

<img width="700" src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/677c37ec-7211-46e4-9cd5-34c0d528c625">

- 위에서 계산한 통계 값을 기반으로 실제 주가 데이터와 비교하기 위해 시각화를 진행하였습니다.

- **애플 이동평균 시각화**
<img width="700" src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/185f5691-8e4b-4d96-947f-f2bd6c115e4d">

- **금 이동평균 시각화**
<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/8e3b30f5-d17c-4f9f-b00b-b2586ad5e124" width="700">

### 20일간 기준 애플 평균 주가 변동 추이 분석(2023.06 ~ 2024.06)  
> 애플과 금의 이동평균 그래프를 보면 대체적으로 통계값 범위에 맞게 실제 각 데이터의 주가가 잘 안착된 것을 볼 수 있습니다.
> 애플의 경우, 24년 06월 구간에 애플 주식이 큰 상승폭을 보이는 것을 알 수 있는데, 실제 애플 주식도 마찬가지로 24년 06월 12일 03시 이후를 기점으로 높은 상승폭을 보이는 것을 알 수 있습니다. (밑에 이미지 참고) **마지막 결론 부분에서 실제 애플 시장의 현황과 같이 이러한 추세의 이유를 분석하도록 하겠습니다.**
>
<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/2d7ab935-851e-4b3c-9de6-d2d78546a4e0" width="700">
</details>

#### 영업일(1달 & 1년)을 기준으로 이동평균 시각화   
<details><summary>👉 코드 확인</summary>  
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/5e5972cc-209f-4ef6-bec0-b2bce5d0bb6b" width="600px">  
</details>    

<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/afcab968-9557-46a7-906e-e3a79d7bc97c" width="850px">  

#### 시각화 분석 결과  
> 애플(AAPL), 금(GLD) 주가 데이터의 영업일을 한달 영업일과 일년 영업일로 구분하여, 시각화 한 결과 1달 영업일 변화폭과 실제 데이터의 변화폭은 거의 일치하는것을 볼 수 있으며, 1년 영업일 또한, 위 두개의 그래프 선과 비슷한 패턴을 보이고 있음을 알 수 있습니다.
>
> 다음으로는 애플과 금의 주가에 대한 매수 및 매도 전략을 수립하기 위해 Golden Cross, Dead Cross를 구축하여 시각화 하도록 하겠습니다.

---

<h3>📌 매수 매도 (Golden Cross & Dead Cross)전략 수립(애플 & 금)</h3>    

**애플(AAPL)**  

<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/6d923115-48c1-4076-8500-f756b7a54225" width="700">

- 애플의 경우 전체적인 추세로 보았을 때, 상승폭을 보이고 있습니다. 위 이미지를 보았을 때, 초록색 선(장기 이동평균선)과 주황색 선(단기 이동평균선)이 교차하는 지점을 중심으로 포지션을 나타내는 빨간색 선이 오르고 내려가는 모습을 볼 수 있으실 것입니다.
- 빨간 선이 내려 가는 지점에서 매도를 권장 하고, 올라가는 지점에서 매수를 권장하지만, 학습을 목적으로 만든 결과이기 때문에, 너무 신뢰하면 안됩니다.
- 빨간 선이 올라가는 지점인 즉 매수를 권장하는 구간의 시기는 아마 애플에서 신제품을 출시하였거나 그 외의 요인으로 인해, 주가가 상승한 것으로 보입니다. 

**금(GDL)**    

<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/e75c09fa-f0af-49cf-80aa-92b2dab12e8a" width="700">  

- 금의 경우, 애플 매수,매도 분석에서 다뤘던 내용과 동일하지만, 금 같은 경우, 글로벌 경제 상황이나 인플레이션, 통화가치 변화 등의 거시적인 요인에 민감하게 반응하는 것이 특징입니다.
- 위 그래프를 보면, 2011 ~ 2012년 구간에서 큰 상승폭을 보이다가 2013년이 지나면서, 점점 하락세를 보이는 것을 볼 수 있습니다. 이러한 이유에는 3가지 이유를 추론할 수 있습니다. 이에 대한 내용은 밑에 상세설명 summary에서 확인 할 수 있습니다.
  
<details><summary>👉 상세 설명</summary>  
  
> 2011 ~ 2012년에 금 값이 상승한 주요 이유에는 3가지로 추론할 수 있습니다.
1. **금융 불안 요소** : 2008년 금융 위기 이후 세계 경제가 여전히 불안정한 시기였습니다. 특히 유럽 채무 위기와 관련된 금융 불안이 있었고, 이는 안전 자산으로서의 금 수요를 높였습니다.
   
2. **저금리정책** : 많은 국가들이 경기 부양을 위해 저금리 정책을 채택했습니다. 이는 금리 수익률이 낮아진 대안 투자 수단으로서 금의 인기를 높였습니다.
   
3. **수요증가** : 전 세계적으로 중국과 인도를 포함한 신흥 시장에서 금 수요가 증가했습니다. 이는 경제 성장과 함께 고소득층의 금 소비가 증가했기 때문입니다.
</details>  
<h3>💡 전체 시각화 분석 결론</h3>  
> 전체적으로 애플 주식과 금 주식에 관한 시각화 분석내용을 통해 알 수 있는 점은 다음과 같습니다.

>**금(Gold, GLD)**
> 
> 금의 경우 애플에 비해, 수익률 측면에서 큰 변화폭은 없으며, 적은 수익률 그래프인것을 알 수 있지만, 금 자체만으로 보았을 때는, 미래로 갈 수록, 꾸준히 상승하는 추세를 보일 것으로 예상됩니다.
>
> 또한 금의 경우 애플에 비해 분산폭이 일정하기 때문에, 애플 주식 투자에 비해서는 안정적이라고 판단할 수 있습니다.
>

>**애플(Apple, AAPL)**
>
> 애플의 경우, 차분 그래프를 분석한 결과, 분산이 위아래로 큰 폭으로 차이가 나는 부분이 있었습니다.
>
> 안정성 측면에서 금에 비해 불안정한 것을 알 수 있습니다.
>
> 애플의 수익률 변동은 아이폰, 애플워치, 맥북, iOS와 같은 주요 제품들의 출시에 따라 크게 영향을 받는 것으로 추론할 수 있습니다.

이와 같은 분석 결과를 바탕으로, 금과 애플 주식의 투자 특성과 리스크를 이해할 수 있습니다. 금은 비교적 안정적인 투자처로, 애플 주식은 높은 변동성을 가지며 제품 출시와 같은 외부 요인에 크게 영향을 받는다는 점에서 차이가 있습니다. **그러나 금과 애플 주가데이터간의 큰 상관관계는 없는 것으로 판단하였습니다.**  

💡 우선 금의 경우, 글로벌 경제시장, 인플레이션 등과 같은 요인에 의해 영향을 받지만, 애플의 경우 경제시장에 영향을 받을 수는 있어도, 이러한 요인 보다 주가에 더 영향을 주는 요인은 출시하는 제품의 판매 수익에 큰 영향을 미치기 때문입니다.
  

---
### **📌 ARIMA 모델을 사용한 모델 평가 진행**  

<details><summary>👉 코드 & 결과 시각화 보기</summary>    

- 불안정 시계열인 ARIMA 모델을 불러온 뒤, order 값에 AR,D(difference),MA(Mooving Average)를 설정한 뒤,
  시작 인덱스와 종료 인덱스 기간을 22년2월1일부터, 24년 6월 12일 까지 설정하여, 훈련과 평가를 진행 후 시각화를 진행하였습니다.
  (금과 애플 주가데이터는 이와 동일한 방식으로 훈련과 평가를 진행하였습니다.)

<img width="650" alt="html1" src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/7686445f-c78c-4bee-9aa5-a7f3a7d994ec">  

### ARIMA 모델 예측 결과 시각화  
🍎 애플 ARIMA 예측 시각화    
<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/ae3872f8-c5b9-4202-ba2c-2a8e65a06b81" width="800">  

**손실율(MSLE) : 0.03**

🏆 금 ARIMA 예측 시각화  
<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/2c5fe23c-60da-480f-9262-8ef0795a1455" width="800">  

**손실율(MSLE) : 0.0001**  


### 💡 ARIMA 모델 평가 결과
- **애플(AAPL)**
- > 애플의 경우, 손실율이 약 0.03%로 매우 낮고, MSE 값이 7 정도로 손실값 차이가 크지 않기 때문에, 예측에 있어서 매우 훌륭한 성능을 보여주었습니다. 이는 ARIMA 모델이 애플 주식의 변동성을 효과적으로 예측할 수 있음을 나타냅니다.

- **금(GLD)**
- > 금의 경우에도 손실율이 매우 낮습니다. MSLE 값이 0.0001%로 금의 예측에서도 ARIMA 모델이 안정적이고 신뢰할 수 있는 성능을 보여주었습니다. MSE 값 또한 2.73으로 예측 오차가 비교적 작아, 금의 가격 변동을 예측하는 데 있어서 ARIMA 모델의 유효성을 확인할 수 있었습니다.

#### 결론 
> ARIMA 모델을 사용하여 애플과 금의 주가를 예측한 결과, 두 자산 모두에서 낮은 손실율과 예측 오차를 보였습니다. 이는 ARIMA 모델이 두 자산의 시계열 데이터를 효과적으로 예측할 수 있음을 의미합니다. 특히, 애플 주식의 변동성을 잘 포착했으며, 금의 경우에도 안정적인 예측 결과를 나타냈습니다. 따라서, ARIMA 모델은 애플과 금과 같은 금융 자산의 시계열 예측에 유용한 도구임을 확인할 수 있었습니다.
  
</details>

-----
  
### 📌 AutoArima 모델 사용하여 훈련 및 예측 시행

<details><summary>👉 데이터셋 분리 진행(Train Data & Test Data) 코드 보기</summary>  

- 애플(AAPL) 데이터셋 분리 및 시각화   
<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/06cff0f7-28b8-4b01-9b87-58e0e2a1e637" width="600">  

- 금(GLD) 데이터셋 분리 및 시각화
<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/e4ba5712-335f-4560-80fc-37fcebaf6c43" width="600">

- 📈 훈련 데이터과 테스트 데이터를 분리하기위해, 각각 80%, 20% 비중으로 나눠야하기 때문에, 슬라이싱을 통해 0.8을 곱한 즉 80%의 데이터를 훈련 데이터에, 나머지 20%의 데이터를 테스트 데이터에 적용시킴으로써, 훈련 데이터와 테스트 데이터의 시각화를 통해 확인 할 수 있습니다.

</details>
  
#### ✏️ KPSS, ADF, PP 정상성 검정 진행
- 차분을 진행하는 것이 필요할 지 결정하기 위해 사용되는 세가지의 검정 방법을 진행하였습니다. (KPSS,ADF,PP)
  - <details><summary>👉 코드 보기</summary>
      <img width="600" alt="html1" src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/4a43f9fa-cefe-45e3-a237-5c663427b4f8">  
- 위 이미지 내에 있는 코드를 통해 애플과 금의 금융 데이터에서의 적정 차분값은 1로 나왔습니다.
    </details>    

  - ✨ - 위 Summary 내에 있는 코드를 통해 애플과 금의 금융 데이터에서의 적정 차분값은 1로 나왔습니다.
 
  - 다음으로 해당 auto_arima 모델을 훈련한 뒤 각 훈련모델의 Summary를 통해 검정 통계량을 분석하겠습니다.
    
     <details><summary>👉 애플(AAPL) 검정통계량 분석 결과 확인</summary>
      <img width="800" alt="html1" src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/65901791-312e-4cfc-a3e3-ae549ac3bbc6">  
 
      #### 애플 주식 데이터 검정 통계량 분석 결과  
      - 애플 주식의 경우, 융박스 검정 통계량(Prob(q))을 따져보았을 때, 0.4로, 어느정도 서로 독립적이고, 동일한 분포를 따르는 것을 알 수 있습니다.
      - 이분산성 검정 통계량(Prob(H))을 보았을 때는, 0으로 잔차의 분산이 일정하지 않은 것을 볼 수 있었습니다.
      - 자크-베라 검정 통계량(Prob (JB))과 같은 경우에도 0의 값이 나왔기 때문에, 해당 애플 주식 데이터가 일정한 평균과 분산을 따르지 않은 것을 알 수 있었습니다.
      - Skew를 보았을 때는, -0.05로 0과 어느정도 가깝다 판단하였기 때문에, 왜도가 심하지 않은 것을 알 수 있었습니다.
      - Kurtosis를 보았을 때는 4.61로 3과 어느정도 가깝기 때문에, 첨도 또한 심하진 않을 것으로 예상됩니다.
 
      <img width="800" src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/33eb7d4c-ace6-4103-b18e-5a65baf35857">    
 
      #### 위 네번째 Correlogram을 보면, 1차 차분한 데이터에서의 상관관계들이 모두 적정값에 안착되어있으며, 정상적인 시계열 데이터 형태를 보입니다.
      
    </details>  

    <details><summary>👉 금(GDL) 검정통계량 분석 결과 확인</summary>
      <img width="800" alt="html1" src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/eb054888-a05d-4a2a-9665-777fdd924885">  
 
      ####  주식 데이터 검정 통계량 분석 결과  
     - 금 주식의 경우, 융박스 검정 통계량(Prob(q))을 따져보았을 때, 0.65로, 서로 독립적이고, 동일한 분포를 따르는 것을 알 수 있습니다.
     - 이분산성 검정 통계량(Prob(H))을 보았을 때는, 0.04로 잔차의 분산이 일정하지 않을 것으로 예상됩니다.
     - 자크-베라 검정 통계량(Prob (JB))과 같은 경우에는 0의 값이 나왔기 때문에, 해당 금 주식 데이터가 일정한 평균과 분산을 따르지 않은 것을 알 수 있었습니다.
     - Skew를 보았을 때는, 0.16으로 0과 어느정도 가깝다 판단하였기 때문에, 왜도가 심하지 않은 것을 알 수 있었습니다.
     - Kurtosis를 보았을 때는 3.93으로 3과 어느정도 가깝기 때문에, 첨도 또한 심하진 않을 것으로 예상됩니다.
 
      <img width="800" src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/d3dbb8cd-321d-4838-8083-0cf5225e6063">    
 
      #### 위 네번째 Correlogram을 보면, 1차 차분한 데이터에서의 2번 상관관계 에서 적정값을 살짝 벗어나는 모습을 보이고 있으며,  
      #### 이를 미루어보았을 때, 모델의 성능에 대한 추가적인 검토가 필요한 부분이지만, 전체적으로 시계열 데이터를 예측하는 데 있어서   
      #### 매우 유효한 성능을 보이고 있으므로 일부 개선이 필요할 수 있지만, 전반적으로 신뢰할 수 있는 결과를 제공합니다.
       
    </details>
- ✏️ 모델 평가 시행 (신뢰구간 확인)
 - <details><summary>👉 코드 보기</summary>
      <img width="600" alt="html1" src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/88879c99-388f-4a7a-9620-8246e335a9e5">   
   
   - 두번 예측을 수행하여, 각각 신뢰구간의 평균값으로 예측을 수행합니다. (금(GLD)도 동일한 방식으로 진행)
   </details>  
    
  - <details><summary>👉 위 코드를 함수로 만들어 모듈화 코드 보기</summary>
       <img width="600" src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/cacab99b-075c-4a6b-a4e2-147760296bc3">  

       <img width="400" src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/6835bdb9-4ae4-44d1-98a0-b83357d86099">
    </details>    

#### 📈 AutoArima 모델 예측 시각화  

🍎 애플 Auto_ARIMA 예측 시각화  
<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/61c55b9c-858c-4751-bc9d-67de1f9f6b12" width="700">  

🏆 금 Auto_ARIMA 예측 시각화   
<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/f3f5b1d7-6ced-40ce-b622-f027de7b0b7f" width="700">

### 📌 DeepLearning - Propet 모델 사용하여 훈련 및 예측 시행  

#### ✨ Custom Propet 모델로 훈련 및 예측 수행    

📌 1단계 - 기본 Propet 모델로 훈련 및 예측 진행  
<details><summary>👉 코드 보기 </summary>    
  
  - Propet 예측 진행을 위해 컬럼명을 변경해준다.
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/4d478112-36bc-4e32-83ed-80d37b6636e6" width="440">

  - `make_future_dataframe' 함수에서 periods를 270으로 설정해주어 예측 기간을 설정해준다.
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/95b7687e-9d70-4aa4-8698-c6ea1f2e2d33" width="500">

  - 애플(AAPL) 예측 결과 시각화 (예측 값과 훈련 데이터 값 비교)
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/893e96af-4ba9-45bb-aac8-e5a615ada258" width="600">

  - 애플(AAPL) 실제 값 & 예측 값 시각화
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/d3065f9b-9d30-4a0d-a5c1-828a418dd98e" width="600">

  **금의 경우에도 위와 동일한 방법으로 예측하였습니다.**     
  
  - 금(GDL) 예측 결과 시각화 (예측 값과 훈련 데이터 값 비교)
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/4c7e81a8-b238-4093-9889-c8e036b67515" width="600">

  - 금(GDL) 실제 값 & 예측 값 시각화
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/7a957bff-7b81-4499-ba66-31c65687d0b8" width="600">

  #### ✨ 결론  
  ##### 애플(AAPL)
  > Propet으로 하이퍼파라미터 튜닝 없이, 훈련을 진행하였을 때 예측 결과를 보면, 애플의 경우 가장 최신 데이터인 6월 14일 이후로 계속 올라가는 상승세를 보일 것으로 예측하였습니다.
  > 실제 데이터 값이 담긴 forcast를 함께 시각화 한 결과 역시, 예측값에 잘 안착되어 있는 것을 볼 수 있었습니다. 이를 보았을 때, 애플의 경우 좋은 성능으로 예측하는 것을 볼 수 있습니다.
  > 애플 특성상 아이폰, 맥북, 애플워치, 아이패드와 같은 전자기기를 판매하는 제품인 만큼 이 제품들의 출시일에 따라 수익률에 큰 변화폭이 있을 것입니다. 이러한 점을 고려하여, 월간 주가 수익률 
    시각화 그래프와 요일별 시각화 그래프 분석 후 실제 조사한 내용과 비교하여 분석해보겠습니다.
   <details><summary>👉 분석 내용 보기 </summary>
    <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/a29f7475-ff69-419e-95f9-d88609840ed4" width="740">    
     
     위 그래프에서 맨 밑 시각화 그래프는 월별 주가 상승 그래프이며, 월별 주가 상승 패턴을 볼 수 있습니다. 그 결과 5월에 가장 주가가 낮고, 이 이후로 9월까지 가장 높게 올라갔다가 살짝 하락하는 부분이 있지만 다시 11월 부터 올라가는 추세를 볼 수 있습니다. 이는 애플의 제품 출시와 연관이 깊습니다.   

     💡 애플은 일반적으로 9월에 새로운 아이폰을 발표하고, 11월에는 블랙 프라이데이와 같은 대형 쇼핑 시즌이 시작되면서 매출이 급증합니다. 이러한 이벤트는 애플의 매출과 주가에 큰 영향을 미치며, 주가가 5월에 상대적으로 낮고 9월과 11월에 상승하는 패턴을 설명할 수 있습니다. 이 패턴은 애플 제품에 대한 소비자들의 기대와 쇼핑 시즌의 효과가 주가에 반영된 결과입니다.   
  </details>  
     <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/4f9d0780-1b03-4a5a-bd36-583e8dacc015" width="700">  

     <출처 : https://iphone-release-date.com/>  

  #### 금(GDL)  
  > 금의 경우, 하이퍼파라미터 튜닝없이 Propet 함수로 훈련 및 예측을 하였을 때, 성능이 안좋은 것은 아니지만, 애플에 비해 조금 부정확한 부분이 보여서 하이퍼파라미터 튜닝을 통한 Propet으로 다시 훈련과 예측을 하도록 하겠습니다.
  
</details>


📌 2단계 - 트렌드, 계절성과 같은 특성을 활용한 Hyperparameter Tuning을 위해 다양한 파라미터 조합을 생성   
<details><summary>👉 코드 보기 </summary>
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/b9d6168c-f24e-4795-928a-5c5cf17c027a" width="740">  

 - 위 코드에서는 트렌드 변화의 민감도를 조절하거나, 계절성의 강도를 조절 또는 계절성을 더할지, 곱할지 결정하는 파라미터 조합을 설정하였으며, 해당 데이터에서는 계절성을 더하기위해서 additive로 설정하였습니다.
 - 또한 모델학습에 이어 교차검증도 수행하도록 하여서 최적의 파라미터를 찾는 과정을 자동화 하였습니다.
 - 최종적으로 각 파라미터들과, 해당 파라미터들의 MAPE 값을 데이터프레임으로 저장하였습니다.

   최적의 파라미터 출력
    <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/d699511e-8186-4f7d-812a-cd9f9347afdb" width="740">

   Predict 진행
   <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/d699511e-8186-4f7d-812a-cd9f9347afdb" width="740">

   - 애플(AAPL) 예측 결과 시각화 (예측 값과 훈련 데이터 값 비교)
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/893e96af-4ba9-45bb-aac8-e5a615ada258" width="600">

  - 애플(AAPL) 실제 값 & 예측 값 시각화
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/d3065f9b-9d30-4a0d-a5c1-828a418dd98e" width="600">

  **금의 경우에도 위와 동일한 방법으로 예측하였습니다.**     
  
  - 금(GDL) 예측 결과 시각화 (예측 값과 훈련 데이터 값 비교)
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/73bb36ea-8d9d-4d69-adcd-c1d2de484d05" width="600">

  - 금(GDL) 실제 값 & 예측 값 시각화
  <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/56413e1b-b67e-4039-8e49-9b46a340a4cc" width="600">

  > 파라미터 튜닝을 통한 Propet 모델 훈련 진행 후 금 금융 데이터의 경우, 예측 결과가 7월 이후로 급격한 하강세를 보이고 있습니다. 물론 이 결과가 정확하지는 않겠지만,
> 이러한 결과를 참고하여, 7월 이후로 금 주식을 사는것은 좋지 않은 판단일 것으로 예상됩니다.
> 추가로 예측한 금 주식 데이터의 경우 실제 값이 예측값에 잘 안착된것을 볼 수 있으며, 성능적으로는 나쁘지 않은 것을 알 수 있습니다.
> 
> 애플의 경우 기존 Propet 훈련결과와 비슷한 양상을 보이고 있는 것을 확인 하였습니다.

</details>  

### ✨ 최종 결론 (투자 전략 제시)  
> #### 애플(AAPL)
> 애플의 경우, 월별로 주식 흐름을 분석해보았을 때, 5월에 가장 낮고, 9월과 12월 경에 가장 높은 패턴을 확인 하였습니다.
>
> <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/2d7ab935-851e-4b3c-9de6-d2d78546a4e0" width="640">  
>
> 위에 시각화 내용에서 분석한 내용 중에, 6월 12일을 기점으로 애플 주식이 상승세를 보이는 것을 확인 하였는데, 월별 애플 주식시장의 주가 상승 패턴을 참고하여 분석해보면 6월의 경우 주가가 쭉 상승하는 패턴임을 알 수 있었습니다.  
> 
> <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/a29f7475-ff69-419e-95f9-d88609840ed4" width="640">  
> 
> 추가적으로 애플의 경우 이번에 아이폰 등에 AI 기능을 본격 탑재하는 애플 인텔리전스를 발표하였다는 뉴스도 있었으며, 이에 따라 6월 12일 오전 10시 40분경 사상 최고가인 202달러를 넘어섰다는 분석이 나왔습니다.  

#### Total Result  
> 위와 같은 분석 결과를 종합하면, 애플 주식의 경우 특정 시기에 주가가 상승하는 경향이 뚜렷하게 나타나는 것을 알 수 있습니다. 특히, 5월에 매수하여 9월이나 12월에 매도하는 전략이 유효할 수 있습니다.
>
> 요일별로 분석해보자면, 목요일날 가장 낮고, 금요일날 가장 주가가 높으므로 목요일에 매수를 하고, 금요일날 매도하는 전략도 유효할 수 있습니다.
> 
> 또한, 중요한 제품 발표나 기술 혁신 뉴스가 있을 때 주가가 급등하는 경향도 파악되었습니다. 이러한 정보를 바탕으로 투자 시기를 조정하여 더 높은 수익을 기대할 수 있을 것입니다.
>
> <img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/e15d040e-6199-49b8-af05-2e8b6cd2396c" width="580">  
>
> <출처 : [https://www.hankyung.com/article/202406119480i]>   

> 금(GDL)의 경우, 24년 7월 이후 급격히 하락세를 보이는 예측 결과가 나오긴 하였지만, 많은 인터넷 자료에서는, 대다수 전문가들의 의견이 2024년에는 금의 상승세가 지속될 것으로 예상하고 있다는 분석 결과가 나왔기 때문에, 해당 예측 결과만을 보고 판단할 수는 없습니다.

<h3>📌 느낀점</h3>

이번 애플 주식과 금 주식 분석을 통해, 주식 시장에는 아무리 우연변동 형태일지라도, 기간을 넓게 보면 어느정도의 흐름과 주기가 존재한다는 사실을 확인할 수 있었습니다. 특히 애플과 같은 대형 주식의 경우, 월별 및 요일별로 나름의 패턴을 보이며, 이러한 패턴을 잘 활용하면 효과적인 투자 전략을 세울 수 있습니다. 월별로는 5월에 매수하여 9월이나 12월에 매도하는 전략, 요일별로는 목요일에 매수하고 금요일에 매도하는 전략이 유효할 수 있다는 점이 인상적이었습니다. 또한, 중요한 제품 발표나 기술 혁신 뉴스가 있을 때 주가가 급등하는 경향을 활용하면, 단기적인 시장 변동성에 흔들리지 않고 장기적인 수익을 추구할 수 있을 것입니다. 이와 같은 분석을 통해, 시장의 흐름을 정확히 파악하고 이를 바탕으로 한 전략적 투자가 중요함을 다시 한번 느낄 수 있었습니다


