## 샤방 프로젝트

![](https://images.velog.io/images/dongha1992/post/e9ec08c3-08a5-4d97-a58b-215dc1f0cf14/%E1%84%8E%E1%85%A5%E1%86%BA%20%E1%84%92%E1%85%AA%E1%84%86%E1%85%A7%E1%86%AB.gif)


# 프로젝트 영상

추후 업데이트 

# 프로젝트 요약

#### 1) 소개

- **'직방'** 이란 부동산 정보 중개 플랫폼을 모티브로 개발 프로젝트를 진행하였습니다.

- 카카오 맵 API를 다루며 데이터를 지도에 시각적으로 나타내어 방대한 데이터를 효율적으로 사용자 편의 맞게 구성하는 것을 목표로 하였습니다. 
 

#### 2) 기간

- 20.11.30 ~ 20.12.11 (12일간)


#### 3) 인원

- 프론트엔드 3명, 백엔드 3명

 

#### 4) 역할

- 프론트엔드

# 사용 스택


### 프론트 엔드

1) React.js(함수형)
2) JavaScript(ES6)
3) Styled-Component
4) KAKAO map API
5) Highchat.js

### 백엔드

1) Django / Python
2) Database Modeling (AQueryTool)
3) KAKAO map API, Naver cloud, postman


### 공통

1) Git / Github
2) Trello
3) Slack
4) Notion

# 프로젝트에서 수행한 역할

### 0) 필터 페이지

**1. 검색**

![](https://images.velog.io/images/dongha1992/post/9f5df9e9-33a1-450a-bd32-21eb645af34b/%E1%84%80%E1%85%A5%E1%86%B7%E1%84%89%E1%85%A2%E1%86%A8.gif)

- 사용자의 input을 받아 Query String을 활용하여 서버로 전송하고 서버에서 검색 결과에 맞는 리스트를 수신.

- 리스트에는 좌표값이 키값으로 있고 리스트를 클릭시 좌표값을 Map component로 보내 Kakao Map에서 제공하는 ```center_changed```를 통해 지도 위에 해당 좌표로 이동.


### 1) 아파트 메인 페이지 

![](https://images.velog.io/images/dongha1992/post/e9ec08c3-08a5-4d97-a58b-215dc1f0cf14/%E1%84%8E%E1%85%A5%E1%86%BA%20%E1%84%92%E1%85%AA%E1%84%86%E1%85%A7%E1%86%AB.gif)

 - Kakao Map에서 제공하는 ```CustomOverlay```와 ```Marker```를 이용하여 원하는 이미지와 텍스트를 지도에 렌더 
 
 - 서버에서 받은 가격 데이터를 삼항 연산자를 이용하여 다른 색으로 표시


![](https://images.velog.io/images/dongha1992/post/0a892501-4c10-44f8-88ce-fbb6b6a5b968/%E1%84%8C%E1%85%AE%E1%86%B7.gif)

- useEffect를 이용하여 Zoom Level에 따라 다른 ```Marker``` 표시

- 최초 View가 렌더될 때 데이터를 받아오는 ```getMap()```를 선언하고 이후 Zoom level에 따라 다른 데이터를 받기 위해 ```getZoomedMap()```를 선언하여 if문으로 분기처리하여 다른 데이터를 받아옴. 

- useEffect의 외존성 배열에 ```최초로 받아온 데이터```와 ```Zoom level```를 넣어 zoom에 따라 다른 데이터를 받아올 수 있게 한다. 

![](https://images.velog.io/images/dongha1992/post/907ca482-f487-4992-89bc-fb935200bf12/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-01-16%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%203.33.54.png)

### 2) 아파트 디테일 페이지

![](https://images.velog.io/images/dongha1992/post/455e8479-a5c0-47bf-8589-662acf643387/%E1%84%83%E1%85%B5%E1%84%90%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%AF.gif)

- marker를 클릭 시 해당 아파트의 상세 정보가 담긴 모달창이 on
- Kaoao MAP API에서 제공하는 클릭 이벤트를 이용하여 해당 Marker의 id를 가져와 Query String으로 서버로 전송
- ```tab```클릭에 따라 다른 데이터 렌더 
- 서버로 받은 데이터 Pagination 구현

**그래프**

 - Highchart.js를 이용하여 데이터 시각화.
 - Highchart.js에서 제공하는 ```options```를 이용하여 커스텀마이징
 - 막대 그래프와 실선 그래프에 데이터를 나눠 담아 한 View에 두 가지 그래프 UI 구성
 
 
### 🚑 Issue & Solve

추후 업데이트

### 🚧 Technical Debt

추후 업데이트

### 🚀 Learn

개발자라는 직업에 매력을 느끼게 된 계기가 몇 있는데 모두 지도와 관련이 있었다. PCT(Pacific Crest Trail)의 트레일 어플리케이션, 베를린의 에어컨 지도, 그리고 코로나 마스크 맵까지 사용자가 원하는 데이터를 지도에 띄우고 사용자는 필요한 정보를 빠르고 쉽게 얻을 수 있는 데에서 '지도'라는 것에, 그것을 가공하여 하나의 완성품을 만드는 개발자에 큰 매력을 느꼈다.

![](https://images.velog.io/images/dongha1992/post/f2651624-654c-425f-80b1-8d101b190f18/pct.jpg)

> https://www.pe.com/2016/03/10/hiking-pacific-crest-trail-app-helps-find-water-campsites/

특히 PCT(Pacific Crest Trail)에서 지도의 위대함을 느꼈는데 인터넷도 없는 미국 산맥을 걸어가며 오직 앱 하나에 의지하여 숙소 정보, 물 정보 등 생존에 필요한 정보들을 얻었다. 만약 개발이라는 것이 없다면, 지도를 사용하지 못했다면 10km 떨어진 마을에 물이 있는지 없는지도 모른 채 트래킹을 해야 했을 것이다.

그래서 "SHABANG" 프로젝트를 하며 즐거웠다. 내가 꿈꿔왔던 기능을 직접 만드는 것은 무척 무척 즐거운 일이다!!

### 1. 오픈 API

이번 프로젝트에서 가장 큰 비중을 차지한 것이 Kakao Map과 Highchart 라이브러리인데 12일의 프로젝트 기간 중 절반은 예제를 보거나 문서를 보는 데 할애한 것 같다. 단순히 메서드를 사용하고 함수를 짜는 것이 아니라 API가 제공하는 문법에 맞춰야 하기 때문에 익숙해지기 시간이 좀 걸렸다. 가령 자바스크립트에서 DOM이벤트를 만들 때 ```addEvenetListner```라는 메서드를 사용했다면 Kakao MAP는 비슷하지만 다른 이름의 메서드와 인자가 3개가 들어갔다. 

![](https://images.velog.io/images/dongha1992/post/2a35bad1-49d1-4c67-9ddc-5093913de383/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-01-16%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%204.59.11.png)

또한, 지도 위에 나타나는 Marker를 생성하는 생성자 함수의 경우 

![](https://images.velog.io/images/dongha1992/post/907f560f-45b2-412c-8c52-dc1a363c7a5b/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-01-16%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%205.00.02.png)

이렇게 Kakao Map에서 지정한 키가 있는데 ```position```에  ```
new kakao.maps.LatLng(lat, lng)```이라는 생성자 함수에 좌표를 넣어야 하는 것을 모르고 직접 정의했다가 에러가 나 한참을 고생했다. API의 세계에서 그들이 만든 룰을 정확히 지켜야함을 알게 된 좋은 경험이었다.

### 2. 라이브러리

**Highchart**와 **D3**가 데이터 시각화 라이브러리로 유명한데 둘 중 무엇을 선택할까를 두고 고민을 많이 했다. 찾아본 결과 **D3**는 러닝커브가 있지만 그만큼 커스텀마이징이 쉽고 한 번 배우면 확장성이 높다고 했다. 그리고 **Highchart**는 커스텀마이징에 제약이 많지만 러닝커브가 낮아 많이 쓰인다고 했다. **D3**를 선택해 이참에 데이터 시각화를 끝장내고 싶었지만 짧은 프로젝트 기간에 완성도에 집중하는 것이 낫다고 판단하여 **Highchart**를 선택했다. 

**Highchart**는 정말 정말 정말 어려웠다. 이런 강력한(?) 라이브러리를 다루는 것이 처음이었고 그 구조를 이해하는 데 1-2일이 걸린 것 같다. 이것 저것 해보면서 내가 원하는 구조가 나올 때까지 예제만 수도 없이 만들었다. 

![](https://images.velog.io/images/dongha1992/post/96e545dc-b1f3-4e93-9584-c51bd584ad24/%E1%84%80%E1%85%B3%E1%84%85%E1%85%A2%E1%84%91%E1%85%B3.png)

연도별 키에 담긴 배열 안에 또 1년치 데이터가 있는 데이터를 받아서 라이브러리에 쓸 수 있도록 가공하면서 배열/객체를 다루는 데 능숙해졌다.

가장 큰 **배움**은 라이브러리를 내가 원하는 모습으로 조작할 수 있는 용기를 얻었다는 것이다. 처음 문서를 봤을 때만 해도 이걸 할 수 있을까. 하는 생각에 하루종일 좌절감을 느꼈는데 한 번 해보니 원하는 UI를 생각해 놓고 거기에 맞춰서 예제를 계속 다루면 된다는 것을 알게 되었다. 더불어 향상된 검색 능력에 뿌듯하다.

### 3. 확장성

다중 선택 버튼 필터를 만들어야 했는데 input이 여러개에 output도 여러개라 삽질을 많이 했다. 


![](https://images.velog.io/images/dongha1992/post/54593c62-734d-4854-b5c5-21f972c3b89f/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-01-16%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%205.55.48.png)


```
  const onChangeUserSelectKeyword = (e) => {
    if (e.target.localName === 'input') {
      if (e.target.name === 'type') {
        userSelectSetType(e.target.value);
      }

      if (e.target.name === 'area') {
        userSelectSetArea(e.target.value);
      }

      if (e.target.name === 'foundation') {
        userSelectSetFoundation(e.target.value);
      }

      if (e.target.name === 'houseHolds') {
        userSelectSetUserSelectHouseHolds(e.target.value);
      }
    }
  };
```

이렇게 무식한 방법으로 하나씩 선택했는데 멘토님의 리뷰를 받고 

![](https://images.velog.io/images/dongha1992/post/ee270844-0a9e-434e-8515-74365c400677/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-01-16%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%205.54.59.png)

![](https://images.velog.io/images/dongha1992/post/46468d78-8cad-41e8-ad72-323f27f6047b/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-01-16%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%205.54.48.png)

```mapper```라는 함수를 통해 확장성 높은 함수를 구현했다. 
