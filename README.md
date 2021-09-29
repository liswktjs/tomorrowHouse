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

🎠 2021.09.19 GNB layout markup

🎃 2021.09.20 hover,focus, active, disabled등 유저 활동에 대응하여 디자인 반영 

: 유저가 어떤 아이콘이나 링크를 클릭했을때 대상의 색이 변하는 애니메이션을 구현할 때에 범위를 넓혀주기 위해서 대상이 되는 것에 padding값을 줄 수 있다 이때에, padding값이 늘어난 만큼 예를 들어 width에 padding값 만큼을 뺸 것으로 업데이트를 해주어야 디자인이 변하지 않는다 -> 그리고 해당 padding값을 줄때에는 변수로 활용하면 후에 유지보수 할 때에 더 편하다 

🌕 2021.09.22 button 상태 디자인, 로그인/비로그인 사용자 등 

: border-radius에 50%를 주게 되면 원모양이 되는데 사실 적용하여도 원 모양이 아닐때가 있다 이럴때에는 border-radius에 50%보다는 width / 2 (단위px)로 주는 것이 좀 더 확실하게 원 모양을 만들 수 있다


🎢 2021.09.23 화살표 표시 하는 법 

: 사각형위에 > 와 같은 표시를 하고 싶다면 border를 사용하면 된다 

새롭게 div tag등을 새롭게 생성하여 사용할 수 있지만 가상요소를 사용해서 화살표 표시를 사용하는 방법이 있다 

이때 content는 비어있어야 하고 width와 height가 모두 0이여야 한다 

그리고 border-top,border-right 등 border의 사방을 설정해야 한다 어느 위치에 색깔을 줄 것인지에 따라서 화살표 방향이 달라진다 / 화살표의 크기를 정하기 위해서는 border의 크기로 설정을 해주면 된다 이때 주의 해야하는 것은 원하는 화살표 방향에 따라서 border-top, border-bottom 이나 border-left, border-right의 크기를 똑같이 설정을 해주어야 한다

```
    &::before,
    &::after {
      content: '';
      display: block;
      width: 0;
      height: 0;
      border-top: $tooltip-size solid transparent;
      border-right: 10px solid transparent;
      border-bottom: $tooltip-size solid $white;
      border-left: 10px solid transparent;
    }
```

🍜 2021.09.27 drop-down 메뉴(=collapse,drawer, accordian 이라고도 불림) + sidebar 메뉴 만들기 

- sidebar 메뉴의 경우 기본적인 화면에서는 보이지 않다가 보여지는 것이기 때문에 주로 <aside>라는 tag를 활용해서 만드는 편이다  

- a 요소에 display:block을 주게 되면 링크의 클릭 범위가 넓어지게된다 만약 클릭범위를 조정하고 싶다면 display:flex를 사용하여야 한다 a을 감싸고 있는 요소에 display:flex를, a 에는 기존과 같이 display:block을 적용하게 되면 링크의 크기 만큼만이 클릭범위가 된다
 
- flex배치를 활용하게 되면 만약 어느 한 요소의 크기가 커지게 된다면 (예를 들어 아이디의 길이가 긴 사람이라든지) 나머지 요소의 크기가 줄어들게 된다. 그런데 이때 나머지 요소의 크기를 고정시켜야 할 경우(프로필 사진이여서 비율과 크기가 일정해야하는 경우) flex-shirnk:0 을 설정하게 되면 크기가 변하지 않는다 (*0은 false를 의미)
  
- ... 생략 처리하기 (= truncate, truncation) 
  
: text가 일정 크기를 넘어가게 되면 해당 부분을 ...으로 처리할때 사용하는 방법 
  
  whitespace: nowrap -> inline요소의 경우 일정 부분을 넘어가게 되면 줄을 바꿔 표시를 하는데 해당 속성을 적용시 무조건 한줄로 표시가 되게 된다 
  
  flex-grow: 1 -> 만약 내용이 부족해서 기존에 기대했던 width값보다 작게 나온다 하더라도 해당 선언을 하게 되면 남은 빈자리를 모두 차지할 수 있게 해준다 (반대로 0값을 주게 되면 사이즈가 변하지 않는다)
  
  overflow:hidden 과 text-overflow:ellipsis 를 추가적으로 선언하게 되면 넘친 글자들이 화면상에서 사라지고 ...으로 대체 되게 된다
  
  -> 최종적으로는 whitespace:nowrap, overflow:hidden, text-overflow:ellipsis를 선언하게 되면 ...처리를 할 수 있게 된다 flex-grow의 경우는 상황에 따라서 다르게 적용
  
🍱 2021.09.28 drawer 반응형 애니메이션 추가하기 
  
  - 화살표가 돌아가는 애니메이션을 표현하고 싶다면 : transition: transform 200ms ease-in-out 사용 (물론 변한 상태에서 화살표가 변한 각도 표기 필수 예시: transform: rotate(180deg) (추가적으로 방향이 변했을때 수평이 맞지 않는다면 translateY 등을 적용해 볼것 )) 

  - 화살표 눌렀을 때 메뉴가 나오도록 하는 것 (drop-down 애니메이션 구현하는 법) 
  단순히 상태에 따라서 display block none으로 처리하게 된다면 애니메이션을 적용하기 힘들다 
  
  그래서 메뉴가 보이면 안될 때에는 max-height(경우에 따라서 width)을 0으로 설정하고 메뉴가 보일때에는 요소의 크기에 따라서 max-height의 크기를 다시 설정한다 
  그리고 해당 크기가 변할때에 transtition: max-height 200ms ease-int-out 과같이 설정하여 자연스럽게 메뉴가 접혔다 펴지는 것 처럼 보여지게된다 

  
  - 넘치는 요소 (화면에 내용이 다 들어오지 않아서) 스크롤을 해서 보여질때 
  :height: 100vh(선택사항) (우선 세로의 크기를 정해서 정해진 크기 안에 들어오는 요소들만 화면에 보이게 만든다)
  
  overflow:auto -> 앞서 넘친 것들을 스크롤을 통해서 보여질 수 있게 한다 
  
  -스크롤 요소 꾸미기 : 비표준이지만 webkit을 사용하면 쉽게 표현할 수 있다 
  
  ::webkit-scrollbar { display:none} 안에 다양한 선언을 할 수 있다 해당 예시는 scrollbar가 화면에 보여지지 않는다 
  
  ::webkit-scrollbar-thumb { } -> 현재 유저가 스크롤중 가리키고 있는 부분 스크롤을 내리거나 올리면 따라서 해당 부분이 움직인다 
  
  - 사이드바가 튀어나왔을 때 사이드 바의 내용을 불투명하게 blind처리를 해주고 싶을 때 
  
  : 우선 뒷부분 배경을 blind처리를 해줄 빈 태그를 하나 생성한다 
  
  그리곤 스타일 적용을 통해서 width:100% height: 100vh; 등의 설정을 통해서 화면을 꽉 채운뒤 배경을 불투명하게 설정을 한다 
  
  그후 z-index를 통해서 배경이 되는 tag의 z-index 값을 사이드 바 보다 작게 설정한다 
  
  + 추가적으로 상태에 따라 배경이 blind되거나 안되거나 처리를 해야할 때는 opacity값과 함께 visibility도 같이 설정해주는 것이 좋다 
  
  배경이 blind일때 opacity:0 / visibility:hidden => opacity:1 / visibility:visible    (*transition을 통해 애니메이션을  넣어주는 것도 잊지 말자)
  
  - 사이드 바의 스크롤을 내렸을때 배경 내용들이 따라 내려오지 않게 하는 방법 : overscroll-behavior: contain 으로 설정한다 (overflow:auto 를 적용한 곳에 똑같이)
  
  - 사이드 바가 사라질때 transform: translate3d(-content의 width요소,0,0) -> 다시 사이드 바가 활성화(나타나야 할때) transform: translate3d(0,0,0) 
  +transition을 통해서 애니메이션 적용하기 
  
🧶 2021.09.29 search 부분 
  
  - transition 의 작동이 스무스하게 되지 않는 요소들 
  width, height, padding, margin, border, top, right, bottom, left 해당 요소들은 애니메이션이 스무스하게 작동되지 않아서 이들을 대체해 transform3d, transform등을 사용한다
  
  - position:absolute를 적용한 element의 경우 width: 100%를 주게 되면 해당 값은 position:relative를 적용한 부모의 width값과 
