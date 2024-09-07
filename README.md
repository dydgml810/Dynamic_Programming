# Dynamic_Programming
Dynamic Programming 파이썬 구현 및 최적화 프로젝트

(본 자료는 경영과학2 팀프로젝트의 일환으로 구현 및 제작되었습니다.)

<hr/>

## 프로젝트 목적: <br> 정해진 예산 안에서 만족도를 최대로 얻을 수 있는 의류 구매 방식 찾기
### 프로젝트 과정:
  1. 각 제품의 CSAT(Customer SATisfaction score) 산출(예제1)
  2. Dynamic Programming 수행(예제1)
  3. DP 코드 구현
  4. 최종 사례 적용(예제2)

<hr/>

* CSAT(Customer SATisfaction score)란?<br>
  : 고객 만족도 점수의 줄임말로 모든 종류의 사업에서 고객 서비스와 제품 품질에 대한 핵심 성과 지표로 주로 사용되는 측정 기준<br>
  
  + 긍정 응답 수 = 4, 5 점 으로 평가된 응답 수
![image](https://github.com/user-attachments/assets/d887f946-5823-41f4-85ed-779fcc039f74)


* 점화식 정리
![image](https://github.com/user-attachments/assets/de4b03ae-8ae0-4d23-bc25-6285f733cf80)


<hr/>


#### 예제에 사용된 실제 상품 출처
* 예제1
  + 코듀로이 밴딩 팬츠: https://www.musinsa.com/app/goods/2861160
  + 무신사 스탠다드 맨투맨: https://www.musinsa.com/app/goods/947067
  + 스트리트 아트워크 후드티: https://www.musinsa.com/app/goods/3544148
  + 스파오 배이직 푸퍼: https://www.musinsa.com/app/goods/3566151
  + 아식스 맥시마이저25: https://www.musinsa.com/app/goods/3428602

<hr/>


* 예제2
  + 탑보이 남녀공용 컬러풀 꽈베기 라운드 니트:https://www.coupang.com/vp/products/6163980749?itemId=11981682918&vendorItemId=70348671512&q=%EA%BD%88%EB%B0%B0%EA%B8%B0+%EB%8B%88%ED%8A%B8&itemsCount=36&searchId=8be59f126d9a4db9bbc7440e457eb075&rank=2&isAddedCart=
  + 해리슨 14컬러 울 캐시 라이크 니트: https://www.coupang.com/vp/products/2145880725?itemId=3604544456&vendorItemId=73736936018&pickType=COU_PICK&q=%ED%95%B4%EB%A6%AC%EC%8A%A8+14%EC%BB%AC%EB%9F%AC+%EC%9A%B8+%EC%BA%90%EC%8B%9C+%EB%9D%BC%EC%9D%B4%ED%81%AC+%EB%8B%88%ED%8A%B8&itemsCount=36&searchId=7c5085adf66d4c84abf0ef44e7ff7069&rank=1&isAddedCart=
  + 코튼 빅사이즈 오버핏 니트 골지 반집업 포라 맨투맨: https://www.coupang.com/vp/products/6173361263?itemId=12065462883&vendorItemId=82546543071&q=%EC%BD%94%ED%8A%BC+%EB%B9%85%EC%82%AC%EC%9D%B4%EC%A6%88+%EC%98%A4%EB%B2%84%ED%95%8F+%EB%8B%88%ED%8A%B8+%EA%B3%A8%EC%A7%80+%EB%B0%98%EC%A7%91%EC%97%85+%ED%8F%AC%EB
  + 남녀공용 특양면 후드티 8컬러: https://www.coupang.com/vp/products/2198229971?itemId=3739822794&vendorItemId=71724988507&pickType=COU_PICK&q=%EB%82%A8%EB%85%80%EA%B3%B5%EC%9A%A9+%ED%8A%B9%EC%96%91%EB%A9%B4+%ED%9B%84%EB%93%9C%ED%8B%B0+8%EC%BB%AC%EB%9F%AC&itemsCount=36&searchId=cd6678c4b79f464696333da73bb7917f&rank=1&isAddedCart=
  + 남녀공용 쭈리면 오버핏 무지 맨투맨: https://www.coupang.com/vp/products/6300302207?itemId=13023173612&vendorItemId=82913443704&pickType=COU_PICK&q=%EB%82%A8%EB%85%80%EA%B3%B5%EC%9A%A9+%EC%AD%88%EB%A6%AC%EB%A9%B4+%EC%98%A4%EB%B2%84%ED%95%8F+%EB%AC%B4%EC%A7%80+%EB%A7%A8%ED%88%AC%EB%A7%A8+%EC%
  + 캐럿 남여공용 숏 패딩자켓: https://www.coupang.com/vp/products/2111547192?itemId=3586763337&vendorItemId=71572558426&pickType=COU_PICK&q=%EC%BA%90%EB%9F%BF+%EB%82%A8%EC%97%AC%EA%B3%B5%EC%9A%A9+%EC%88%8F+%ED%8C%A8%EB%94%A9%EC%9E%90%EC%BC%93&itemsCount=36&searchId=d085f0f829e24a91aa450184dc4f3009&rank=0&isAddedCart=
  + 씨쏘 남성용 히든밴딩 스판 슬림 기모슬랙스: https://www.coupang.com/vp/products/340803413?itemId=1084864124&vendorItemId=71679352530&q=%EC%94%A8%EC%8F%98+%EB%82%A8%EC%84%B1%EC%9A%A9+%ED%9E%88%EB%93%A0%EB%B0%B4%EB%94%A9+%EC%8A%A4%ED%8C%90+%EC%8A%AC%EB%A6%BC+%EA%B8%B0%EB%AA%A8%EC%8A%AC%EB%9E%99%EC%8A%A4&itemsCount=36&searchId=5ba2105dc2164695b16ebf9587130930&rank=0&isAddedCart=
  + 캐럿 남성용 경량 패딩자켓: https://www.coupang.com/vp/products/2111547303?itemId=3586763448&vendorItemId=71572558425&q=%EC%BA%90%EB%9F%BF+%EB%82%A8%EC%84%B1%EC%9A%A9+%EA%B2%BD%EB%9F%89+%ED%8C%A8%EB%94%A9%EC%9E%90%EC%BC%93&itemsCount=36&searchId=f9fc1f24a0464a1ba28bacbc75138212&rank=0&isAddedCart=
  + 나이키 남성용 REV5 운동화 런닝화: https://www.coupang.com/vp/products/4790782302?itemId=6138609885&vendorItemId=79370180433&q=%EB%82%98%EC%9D%B4%ED%82%A4+%EB%82%A8%EC%84%B1%EC%9A%A9+REV5+%EC%9A%B4%EB%8F%99%ED%99%94+%EB%9F%B0%EB%8B%9D%ED%99%94&itemsCount=36&searchId=bc6b3852c393459a948e7cbe3acb9224&rank=0&isAddedCart=
  + 테라우드 남성 퍼스트에디션 드로즈 팬티 10종세트: https://www.coupang.com/vp/products/2263879178?itemId=3880224670&vendorItemId=71864878272&q=%ED%85%8C%EB%9D%BC%EC%9A%B0%EB%93%9C+%EB%82%A8%EC%84%B1+%ED%8D%BC%EC%8A%A4%ED%8A%B8%EC%97%90%EB%94%94%EC%85%98+%EB%93%9C%EB%A1%9C%EC%A6%88+%ED%8C%AC%ED%8B%B0+10%EC
  + 두발로 남성용 자물쇠 페이크삭스 10켤레: https://www.coupang.com/vp/products/113166380?itemId=339960446&vendorItemId=3834380584&pickType=COU_PICK&q=%EB%91%90%EB%B0%9C%EB%A1%9C+%EB%82%A8%EC%84%B1%EC%9A%A9+%EC%9E%90%EB%AC%BC%EC%87%A0+%ED%8E%98%EC%9D%B4%ED%81%AC%EC%82%AD%EC%8A%A4+10%EC%BC%A4%EB%A0%88&itemsCount=36&searchId=c92240dd08be4df6afe42085e6c431f0&rank=1&isAddedCart=
  + 부들양털 뽀글이 후드자켓 MDJK124PP: https://www.coupang.com/vp/products/7154569388?itemId=16203758100&vendorItemId=85263880520&q=%EB%B6%80%EB%93%A4+%EC%96%91%ED%84%B8+%EB%BD%80%EA%B8%80%EC%9D%B4+%ED%9B%84%EB%93%9C%EC%9E%90%EC%BC%93&itemsCount=36&searchId=687b4d62328f4b4db42d0463a2957ce2&rank=0&isAddedCart=

<hr/>


* 파일:
  + Dynamic_Programming.ipynb
  + 최대 만족도를 위한 쇼핑 방법 최적화.pptx


