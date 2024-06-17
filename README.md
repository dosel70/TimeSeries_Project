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
🍎 애플 ARIMA 예 시각화    
<img src="https://github.com/dosel70/TimeSeries_Project/assets/143694489/ae3872f8-c5b9-4202-ba2c-2a8e65a06b81" width="800">  

**손실율(MSLE) : 0.03**

🏆 금 ARIMA 예 시각화  
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
  
> 기존 사전 훈련 데이터 csv를 Django Database에 insert 하였습니다.

- `get_index_from_member_tag`
  
- ✨ 해당 메서드는 회원의 관심사 태그 에 관하여 가장 유사한 원랩을 찾아내는 역할을 합니다.
- `CountVectorizer()`를 통해 , 코사인 유사도를 계산하고, 가장 높은 평균 유사도를 가진 원랩을 추출하여 MainView(메인페이지)에 전달합니다.
  - <details><summary>👉 코드 보기</summary>
      <img width="800" alt="html1" src="https://github.com/dosel70/django-ai/assets/143694489/f6bf6d5a-b662-4c67-b5a7-35a10967206a">
    </details>  

- `get_index_from_member_tag`
    
- 다시 AIView로 돌아와서 클래스 내에서 회원의 관심사 태그를 기반으로 가장 유사한 OneLab의 객체들을 데이터베이스에서 가져오는 메서드를 정의 하였습니다.
- 해당 코드는 주어진 회원 관심사 태그에 대해 데이터베이스에서 OneLab 객체를 가져와 해당 원랩의 데이터를 벡터화하여 유사도를 계산합니다. 그리고 각 OneLab 객체의 평균 유사도를 계산하고, 가장 높은 유사도를 가진 OneLab 객체의 인덱스와 벡터를 반환합니다.
  - <details><summary>👉 코드 보기</summary>
      <img width="800" alt="html1" src="https://github.com/dosel70/django-ai/assets/143694489/4ec0bf7a-6c13-422e-8fcc-4a63bcdeb4c7">
    </details>

- `recommend_similar_onelabs(self, member_tag, content_vectors, num_recommendations=3)`

-  recommend_similar_onelabs 메서드를 통해 실제 메인화면에서 회원의 관심사와 유사한 OneLab 목록을 추천해주는 기능을 수행합니다.
-  기본적으로 주어진 회원의 관심사 태그에 가장 유사한 원랩 목록 들을 우선적으로 추천하지만 만약 유사한 객체가 부족하면 무작위로 추가하여 추천 목록을 채우는 방식으로 동작하게 하였습니다.
 
  - <details><summary>👉 코드 보기</summary>
      <img width="800" alt="html1" src="https://github.com/dosel70/django-ai/assets/143694489/7c57293c-e660-49e8-b5bc-ffafc7fff3c1">  

      <img width="800" alt="html1" src="https://github.com/dosel70/django-ai/assets/143694489/86ec6391-2815-4d76-827b-a0dee6ce4ede">
    </details>



<h3>📌 서버 배포 및 화면 시연</h3>

- 로컬에서 구현한 기능이 정상적으로 작동이 되는 것을 확인하고 이를 ubuntu를 이용하여 서버에 배포하였습니다.

---

<h3>📌 Trouble-Shooting</h3>

- MainView에서 RestAPI를 이용하여 기존 AIView에서 정의된 함수들을 불러오지 못하여 메인 페이지에서 오류가 나는 에러
  
- 메인페이지에서 추천 원랩 목록이 나타나지 않은 에러 
  
- 위 오류를 수정하고 원랩 목록들이 출력이 되었지만, 회원의 관심사와 맞지 않은 원랩 목록들이 출력 
 

 
<h4>✨ MainView에서 RestAPI를 이용하여 기존 AIView에서 정의된 메서드 들을 불러오지 못하여 메인 페이지에서 오류가 나는 에러</h4>

- url 경로를 제대로 설정해 주었는데도 불구하고 Not Found 에러가 나타났습니다.
- 경로를 다시 추적을 해보니, Main url 파일에 새로이 만든 ai url을 추가하지 않아 못 찾는 것을 파악하고 추가해주었습니다.
- 수정한 다음 다시 확인하니 View로 넘어가는 것을 파악했으나, 메인페이지에서 아예 원랩 목록이 출력이 되지 않는 문제가 발생하였습니다.

<h4>✨ 메인페이지에서 추천 원랩 목록이 나타나지 않은 에러 </h4>

- View로 넘어간 것을 확인하였지만, 실제 원랩 목록들이 나오지 않는 것을 확인 하였습니다.
- AI View 내에 recommend_similar_onelabs 라는 메서드 내에 `recommended_onelabs.append(OneLab.objects.get(id=idx + 1))` 라고 코드를 작성한 부분이 있었습니다.
- id = idx + 1이라고 명시한부분에서 + 1 을 더한 것 때문에 인덱스 오류가 발생하여서 전체적인 로직 구성에 오류가 발생하였던 문제 였습니다.
- 그래서 `recommended_onelabs.append(OneLab.objects.get(id=idx))`로 수정하여서 추천 원랩목록들이 나왔지만, 회원의 관심사와는 맞지 않은 원랩 목록들이 추천되는 이슈가 발생하였습니다.
- <details><summary>👉 코드 보기</summary>
    <img width="800" alt="html1" src="https://github.com/dosel70/django-ai/assets/143694489/f00945fc-3ba1-4b22-9d35-853e005d3f7b">
  </details>

<h4>✨ 회원의 관심사와 맞지 않은 원랩 목록들이 출력되는 에러</h4>

- 원랩목록들이 나오지 않았던 문제를 해결한 다음 다시 확인했으나, View를 통해 받아온 추천 원랩 목록 기능 로직이 잘못 구성되어있다는 것을 알게 되었습니다.
- 기존 코사인 유사도 분석 기능이 있는 메서드 내에서  원랩의 유사도 점수가 낮게 나와서 `onelabs_list = [f"{onelab.onelab_main_title[:10]} {onelab.onelab_content[:20]} {onelab.onelab_detail_content[:10]}" for onelab in onelabs]` 슬라이싱을 통해서 각 원랩의 제목,내용,한줄소개 부분이 축소되어 데이터가 줄어들게 되어 연산 속도를 높이고, 모델이 핵심 정보에 더 집중할 수 있게 되었습니다.
- 최종적으로 사용자의 태그와 일치하는 원랩 객체를 우선적으로 추천하도록 로직을 수정했습니다.
- 이를 확인하여 다시 메인 화면을 확인한 결과 정상적으로 회원의 관심사와 유사한 원랩 목록들이 출력 되는 것을 확인 할 수 있었습니다.
  
- <details><summary>👉 코드 보기</summary>
    <img width="800" alt="html1" src="https://github.com/dosel70/django-ai/assets/143694489/8cb8bc6d-999f-4b47-a50a-2dc615b1cdac">
  </details> 


<h3>📌 느낀점</h3>

- 이번 프로젝트를 통해 AI와 Django를 같이 활용해보면서, 많은 시행착오 과정들이 있었지만, 오류를 하나씩 해결해나가고 직접 AI 시스템을 구현해보니 정말 재밌었고 값진 경험이였습니다.
- 데이터 수집부터 유사도 분석, 그리고 실제 서버 배포까지 전 과정을 직접 경험하며, 다양한 시행착오를 겪으면서 많은 것을 배웠습니다.
- Cosine Similarity, Naybe Bayse 등 다양한 텍스트 분류 기법을 직접 서버에 적용을 해보고, 유사한 원랩 콘텐츠를 찾아내는 과정에서 높은 유사도 점수를 얻을 때마다 큰 만족감을 느꼈습니다.
- 특히 Trouble-Shooting 과정에서 사용자 관심사 기반 원랩 목록을 완전 정확하지는 않지만, 오류를 해결하여 유사하게 추천하는 기능을 구현하며, 이러한 AI 시스템이 실제 시중에서 어떤 흐름으로 사용되는지 알 수 있게 되었습니다!

<h3>📌 개선 사항</h3>

- 처음 비회원으로 메인화면에 접속 했을 경우, 원랩 목록들의 이미지가 나오지 않는 점이 아쉬웠습니다. 추후에 이 부분은 수정하도록 하겠습니다. 
- 추가로 추천된 원랩 목록들을 클릭하면 그 경로로 이동해야 하는데, 구현이 되지 않았습니다. 이 부분 역시 추가로 수정하도록 하겠습니다.
