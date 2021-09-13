# tomorrowHouse

### 오늘의 집 클론 코딩 연습 
📄📚using HTML, Sass, JS

팀플젝을 하면서 느꼈던 답답함 해소 하기 위한 

웹페이지의 기본인 html, css(sass) 부터 다시 집고 넘어가면서 세세한 코드 짜기 도전기 👊

🔨  2021.08.20 Sass, prettier등 환경 세팅

🍱  2021.08.21 assets들 설정 

+ png 는 jpg와 달리 투명배경을 지원해준다 
+ vector이미지는 svg로 추출
+ svg의 경우 코드를 html에 복붙해서 fill="currentColor"로 바꿔주면 색깔을 맘대로 변경이 가능하지만 복잡하기 때문에 font로 바꾸기를 권장
+ font로 바꿀 때에는 icomoon이라는 사이트 활용 

💄  2021.08.22 sass 활용한 기본 설정 

+ font 설정, color 값 설정 등 상수 값 선언  

📝 2021.08.23 grid layout 설정 

+ unit(콘텐츠표기되는 공간) gutter(unit간의 거리) column(unit 양 옆으로 1/2 gutter 씩 있음)
+ 부트스트랩에서 사용하는 grid 설정 방법 
+ .container (gird 적용되는 영역 설정) , .row (unit를 가로로 정렬할 때 활용 / unit들을 감싼다) , .col- (width 값 설정) 

✨ 2021.08.24 mixin 설정

+ mixin 적용시 적용하고 싶은 요소에 @include mixin변수명으로 적용 가능
+ placeholder 선언 방법 %변수 이름 { style 관련 선언}
+ 사용할 때에는 include가 아닌 @extend 활용 

🎨 2021.08.25 img 설정 

+ 프로필 사진 등 규격이 정해져 있는 곳에 이미지를 넣어야 할 때에는 img tag를 div tag로 감싸 div tag에서 조절을 해주는 것이 좋다 
+ img에 object-fit: cover (규격이 다른 이미지라도 이미지 중심부를 기준으로 사진을 보여질 수 있게 도와준다)

🎉 2021.09.08 price component, button component들 style 

+ display flex와 inline-flex의 차이점

: flex의 경우 block 취급을 하여 요소들이 수직으로 쌓이도록 하고 

inline-flex의 경우 inline block과 같은 취급을 하여 요소들이 수평적으로 쌓이게 된다 

+ button 스타일 설정시 tip!: 버튼은 textContent에 따라서 widht값이 달라질 수 있기 때문에 width보다는 통일된 height값을 button들에 적용하는 것이 더 효율적이다 

🥪 2021.09.11 form style 설정 

+ option tag 간편하게 여러개 작성하기 : option[value="$"]*5{선택 $}   -> option이라는 tag는 자신의 순서를 value로 가지고 textContent로는 선택 자신의 순서 라고 된 tag를 5개를 생성하게 된다 

+ select tag의 경우 user style sheet에 의해서 기본으로 정해진 스타일의 틀이 있는데 만약 이걸 없애고 새롭게 디자인을 하고 싶다면 apperance:none을 적용시킨다 

+ input의 placeholder의 글자색을 바꾸고 싶은 경우 input::placeholder{ color: #원하는색 }식으로 표기를 한다 (*::이 두개 이다) 

+ disabled의 상태일때를 제외하고 오직 hover일 때만 특정 효과를 적용하고 싶을 때 : (tag이름이나 class이름):not(:disabled):hover{ style 선언문} 

+ 이미지를 요소 안의 특정한 위치에 위치시키고 싶을때: 

해당 이미지를 감싸고 있는 부모 요소에 position: relative를 적용시킨다 이로써, 해당 요소를 기준으로 top, left등의 오프셋이 결정된다 

그리고 특정한 위치에 놓고 싶은 이미지요소에 position :absolute를 적용시킨다 이로써, 자신의 부모 요소(position:relative를 선언한 요소)를 기준으로 position을 결정한다 

추가적으로 만약, 해당 요소를 y축의(세로축) 정가운데 위치시키고 싶다면 transform: translateY(-50%)을 적용 할 수 있다

+ select의 위에 새롭게 올린 버튼 V 를 클릭했을때 기존과 같이 동일한 event가 발생하도록 하고 싶을 때 

: position:absolute를 통해서 select 요소위에 V 를 새롭게 올린 것 이므로, V 버튼이 select 요소보다 위에 쌓인 것이 된다. 그러므로 select에 적용한 스타일들이 적용이 안된다 이중 가장 큰 문제는 V를 눌렀을 떄에 select 요소들이 나타나지 않는다는 것이다! 이를 해결하고 싶을 때에는 여러가지 방법이 있지만 가장 간단한 것은 V에 pointer-events:none을 적용하는 것이다 
이를 적용함으로써 V요소의 클릭이벤트를 무시한다는 것이 되므로 V 영역을 클릭했을때에 select를 클릭한 것과 동일한 방식으로 작동될 수 있다

🍦 2021.09.12 uitility class 업데이트 , global navigation bar layout

+ .visually-hidden : 부트스트랩에서 사용하는 방법, 특정 버튼(알림, 북마크 등 텍스트가 없이 그림으로만 웹상에서 존재하는 것)을 클릭할때 스크린 리더에 text로 어떤 것을 입력했는지 값을 전단해야 할 때 사용한다 

.visually-hidden {
  position: absolute;
  width: 1px !important;
  height: 1px !important;
  padding: 0 !important;
  margin: -1px !important;
  overflow: hidden !important;
  clip: rect(0, 0, 0, 0) !important;
  white-space: nowrap !important;
  border: 0 !important;
} 

+ nav tag를 사용할 때에는 nav tag안에 h1~h3... 등의 tag를 활용해서 해당 nav가 무엇을 가리키는지 표기를 해주어야 한다

🎀 2021.09.13 layout 잡기 

+ grid layout을 적용할때 : .container > .row > .col > header, div 등등 순으로 소속이 되어있어야 된다 

+ inline요소는 width와 height을 적용할 수 없으므로 img를 사용할때 안전하게 display:block을 한번 더 선언해주는 것이 좋다

+ scss에서 클래스명이 부모의 클래스 이름을 따라갈때 예시 (부모 : gnb  자식: gnb-button) 일때 .gnb { &-button{ } } 식으로 간단하게 표현할 수 있다
