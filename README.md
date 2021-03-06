# tomorrowHouse

### 오늘의 집 클론 코딩 연습

📄📚using HTML, Sass, JS

팀플젝을 하면서 느꼈던 답답함 해소 하기 위한

웹페이지의 기본인 html, css(sass) 부터 다시 집고 넘어가면서 세세한 코드 짜기 도전기 👊

🔨 2021.08.20 Sass, prettier등 환경 세팅

🍱 2021.08.21 assets들 설정

- png 는 jpg와 달리 투명배경을 지원해준다
- vector이미지는 svg로 추출
- svg의 경우 코드를 html에 복붙해서 fill="currentColor"로 바꿔주면 색깔을 맘대로 변경이 가능하지만 복잡하기 때문에 font로 바꾸기를 권장
- font로 바꿀 때에는 icomoon이라는 사이트 활용

💄 2021.08.22 sass 활용한 기본 설정

- font 설정, color 값 설정 등 상수 값 선언

📝 2021.08.23 grid layout 설정

- unit(콘텐츠표기되는 공간) gutter(unit간의 거리) column(unit 양 옆으로 1/2 gutter 씩 있음)
- 부트스트랩에서 사용하는 grid 설정 방법
- .container (gird 적용되는 영역 설정) , .row (unit를 가로로 정렬할 때 활용 / unit들을 감싼다) , .col- (width 값 설정)

✨ 2021.08.24 mixin 설정

- mixin 적용시 적용하고 싶은 요소에 @include mixin변수명으로 적용 가능
- placeholder 선언 방법 %변수 이름 { style 관련 선언}
- 사용할 때에는 include가 아닌 @extend 활용

🎨 2021.08.25 img 설정

- 프로필 사진 등 규격이 정해져 있는 곳에 이미지를 넣어야 할 때에는 img tag를 div tag로 감싸 div tag에서 조절을 해주는 것이 좋다
- img에 object-fit: cover (규격이 다른 이미지라도 이미지 중심부를 기준으로 사진을 보여질 수 있게 도와준다)

🎉 2021.09.08 price component, button component들 style

- display flex와 inline-flex의 차이점

: flex의 경우 block 취급을 하여 요소들이 수직으로 쌓이도록 하고

inline-flex의 경우 inline block과 같은 취급을 하여 요소들이 수평적으로 쌓이게 된다

- button 스타일 설정시 tip!: 버튼은 textContent에 따라서 widht값이 달라질 수 있기 때문에 width보다는 통일된 height값을 button들에 적용하는 것이 더 효율적이다

🥪 2021.09.11 form style 설정

- option tag 간편하게 여러개 작성하기 : option[value="$"]\*5{선택 $} -> option이라는 tag는 자신의 순서를 value로 가지고 textContent로는 선택 자신의 순서 라고 된 tag를 5개를 생성하게 된다

- select tag의 경우 user style sheet에 의해서 기본으로 정해진 스타일의 틀이 있는데 만약 이걸 없애고 새롭게 디자인을 하고 싶다면 apperance:none을 적용시킨다

- input의 placeholder의 글자색을 바꾸고 싶은 경우 input::placeholder{ color: #원하는색 }식으로 표기를 한다 (\*::이 두개 이다)

- disabled의 상태일때를 제외하고 오직 hover일 때만 특정 효과를 적용하고 싶을 때 : (tag이름이나 class이름):not(:disabled):hover{ style 선언문}

- 이미지를 요소 안의 특정한 위치에 위치시키고 싶을때:

해당 이미지를 감싸고 있는 부모 요소에 position: relative를 적용시킨다 이로써, 해당 요소를 기준으로 top, left등의 오프셋이 결정된다

그리고 특정한 위치에 놓고 싶은 이미지요소에 position :absolute를 적용시킨다 이로써, 자신의 부모 요소(position:relative를 선언한 요소)를 기준으로 position을 결정한다

추가적으로 만약, 해당 요소를 y축의(세로축) 정가운데 위치시키고 싶다면 transform: translateY(-50%)을 적용 할 수 있다

- select의 위에 새롭게 올린 버튼 V 를 클릭했을때 기존과 같이 동일한 event가 발생하도록 하고 싶을 때

: position:absolute를 통해서 select 요소위에 V 를 새롭게 올린 것 이므로, V 버튼이 select 요소보다 위에 쌓인 것이 된다. 그러므로 select에 적용한 스타일들이 적용이 안된다 이중 가장 큰 문제는 V를 눌렀을 떄에 select 요소들이 나타나지 않는다는 것이다! 이를 해결하고 싶을 때에는 여러가지 방법이 있지만 가장 간단한 것은 V에 pointer-events:none을 적용하는 것이다
이를 적용함으로써 V요소의 클릭이벤트를 무시한다는 것이 되므로 V 영역을 클릭했을때에 select를 클릭한 것과 동일한 방식으로 작동될 수 있다

🍦 2021.09.12 uitility class 업데이트 , global navigation bar layout

- .visually-hidden : 부트스트랩에서 사용하는 방법, 특정 버튼(알림, 북마크 등 텍스트가 없이 그림으로만 웹상에서 존재하는 것)을 클릭할때 스크린 리더에 text로 어떤 것을 입력했는지 값을 전단해야 할 때 사용한다

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

- nav tag를 사용할 때에는 nav tag안에 h1~h3... 등의 tag를 활용해서 해당 nav가 무엇을 가리키는지 표기를 해주어야 한다

🎀 2021.09.13 layout 잡기

- grid layout을 적용할때 : .container > .row > .col > header, div 등등 순으로 소속이 되어있어야 된다

- inline요소는 width와 height을 적용할 수 없으므로 img를 사용할때 안전하게 display:block을 한번 더 선언해주는 것이 좋다

- scss에서 클래스명이 부모의 클래스 이름을 따라갈때 예시 (부모 : gnb 자식: gnb-button) 일때 .gnb { &-button{ } } 식으로 간단하게 표현할 수 있다

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

- flex배치를 활용하게 되면 만약 어느 한 요소의 크기가 커지게 된다면 (예를 들어 아이디의 길이가 긴 사람이라든지) 나머지 요소의 크기가 줄어들게 된다. 그런데 이때 나머지 요소의 크기를 고정시켜야 할 경우(프로필 사진이여서 비율과 크기가 일정해야하는 경우) flex-shirnk:0 을 설정하게 되면 크기가 변하지 않는다 (\*0은 false를 의미)
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

- 추가적으로 상태에 따라 배경이 blind되거나 안되거나 처리를 해야할 때는 opacity값과 함께 visibility도 같이 설정해주는 것이 좋다

배경이 blind일때 opacity:0 / visibility:hidden => opacity:1 / visibility:visible (\*transition을 통해 애니메이션을 넣어주는 것도 잊지 말자)

- 사이드 바의 스크롤을 내렸을때 배경 내용들이 따라 내려오지 않게 하는 방법 : overscroll-behavior: contain 으로 설정한다 (overflow:auto 를 적용한 곳에 똑같이)

- 사이드 바가 사라질때 transform: translate3d(-content의 width요소,0,0) -> 다시 사이드 바가 활성화(나타나야 할때) transform: translate3d(0,0,0)
  +transition을 통해서 애니메이션 적용하기

🧶 2021.09.29 search 부분

- transition 의 작동이 스무스하게 되지 않는 요소들
  width, height, padding, margin, border, top, right, bottom, left 해당 요소들은 애니메이션이 스무스하게 작동되지 않아서 이들을 대체해 transform3d, transform등을 사용한다

- position:absolute를 적용한 element의 경우 width: 100%를 주게 되면 해당 값은 position:relative를 적용한 부모의 width값과

🩹 2021.10.11 LNB(local navigation bar) 부분

- inline 요소들 경우 width 값을 설정하지 않으면 해당 요소들의 크기 만큼 witdh값을 가지게 된다 (->inline-flexbox의 경우 inline의 특징도 취할 수 있다)

- overflow를 적용할때 주의점 -> overflow의 기준점 설정이 중요하다 (width height를 어떻게 설정 할 것인지) 만약 width height값이 정해져 있다면 해당 값을 충족하는 요소에 overflow를 적용시킬 것!

- width: max-content -> 자신이 가지고 있는 자식 요소들의 width가 가장 길다고 가정하여서 계산하였을때의 길이
  min-content -> 자신의 자식 요소들의 width가 가장 짧다고 가정하여서 계산하였을 때의 길이

단점) 브라우저들 중 max-content가 호환이 되지 않는 곳이 많다

- display: inline-flex + white-space: nowrap
  : inline-flex -> inline-block 와 같은 특성을 가지고 있음 (block은 부모 요소의 width,height값을 기준으로 삶고 inline-block의 경우 자식 요소들의 width값에 맞춰 길이를 가지게 된다)

white-space:nowrap -> 적용이된 요소 안에 들어있는 inline-block속성을 가진 요소들에게 한 줄을 유지하라는 설정

=> 두 가지를 같이 적용하게 되면 자식요소에 있는 text가 2줄 변환 등의 변화 없이 한줄을 유지하면서 자신의 text길이에 따라서 width들을 가지게 되고 해당 width값들을 합친 만큼 inline-flex가 적용된 요소의 width값이 설정이 되게 된다 만약 해당 요소가 전체의 뷰포트보다 크다면 overflow:auto를 활용하여 스크롤로 보이게 할 수 있다

🎨 2021.10.12 footer 부분

- d' 설명이나 정의를 적는 tag
  해당 tag의 경우 dt, dd tag만을 자식요소로 가지고 추가적으로 해당 tag들을 감싸는 div tag를 가질 수 있다

dt의 경우 용어 dd의 경우 dt에서 입력한 용어에 대한 설명을 적는다

- zindex의 경우 부모요소들이 우선순위를 가지기 때문에 자식요소들에만 z-index를 적용해서 원하는 모양이 나오지 않을 수 있다 그럴 떄에는 부모요소의 z-index값을 다시 한번 살펴보자

- breadcrumb: 현재페이지 까지 거쳐온 페이지단계를 표시

💄 2021.10.13 breadcrumb 부분 / slider, carousel 부분 공부

- figure tag : img tag 단독으로 사용하는 것이 아닌 img tag를 figure tag로 감싸게 되면 좀 더 sematic 해진다
  figure는 figcaption과 함께 사용된다 figcaption에는 figure안에 들어간 content에 대한 설명을 입력한다 (참고로 figcaption은 figure tag안에 넣어준다)

- WAI-ARIA role: aira-label(마크업 상으로 텍스트를 제공하지 않지만 스크린 리더로 제공될 정보들에 관해서 입력할때 사용), aria-hidden(정보로써 사용하지 않아서 무시해도 되는 것을 입력할 때 사용) 등과 같이 브라우저를 더 시멘틱하게 입력하기 위해 사용되는 것이다

WAI-ARIA role에는 크게 3가지가 존재한다 ) role, property, state

1. role
   role은 tag가 브라우저 상에서 어떤 역할을 수행하는지 명시적으로 작성하는 것
   role에 적용할 수 있는 값들은 정해져 있으므로 해당 값들을 필요에 따라 선택하여 사용하여야 한다

2. proerty (속성)
   추가적인 의미나 속성을 부여하는데 사용할 수 있는 속성의 요소를 정의하는데 사용
   이미지 alt 대신에 사용이 가능하다
   ex) aria-required="true"

3. state (상태)
   aria-disabled="true" 과 같이 스크린리더에게 현재 상태를 알려주는 역할로 사용

- WAI-ARIA role 예시들 공부

region) 페이지 내에서 landmark content를 가지고 있는 tag에게 부여를 한다

tablist, tabpanel ) tab을 모아둔 리스트는 tablist이고 해당 tab을 클릭했을 때에 보여지는 content가 tabpanel
연결되는 tab과 tabpaenl끼리 명시적으로 표시를 하고 싶다면 tab에 id를 부여하고 (예시: id="product-1") tabpanel에는 aria-labelledby="product-1"에 해당 아이디 값을 입력한다

- carousel: transform, translate사용 0 -> -25% -> -50% -> -75% 식으로 이동을 하면서 carousel이 작동을 하게 된다

carousel js 중 대표적인 것 하나 tiny-slider.js

🍕 2021.10.14 product carousel 스타일 작업

- 그리드로 틀이 잡혀있는 화면에서 사진을 viewport에 꽉 차게 표현해주고 싶을때

:그리드로 작업을 하게 되면 그리드 내에 있는 콘텐츠들의 자리를 잡는 것은 편하지만 그리드 범위를 벗어나는 요소들의 경우 추가적인 작업을 해주어야 한다
div와 같은 block요소들은 부모의 width값을 상속받게 되는데 만일 해당 요소의 width값을 100%라는 식으로 width값을 명시 하지 않은 채로 margin-left: -15px (grid 적용 범위에 따라 값이 달라짐)
margin-left: -15px; 과 같은 작업을 해주게 되면 width값이 원하는 데로 늘어날 수 있다

😎 2021.10.22 product info 마크업 + 스타일 작업 + order form 마크업 + 스타일

- output tag : <output> select 그룹에서 무엇을 선택했는지 결과값을 보여줄 때 사용하는 tag , 어떤 select 그룹에 대한 결과값인 표기하기 위해 label과 똑같이 for로 select id 값을 명시해준다

- apperance:none -> 브라우저에 기본적으로 적용되어 있는 form style들 화살표 등이 보이지 않게 된다

- pointer-events:none -> 스타일링을 위해서 작업을 할때에 select 그룹에 새로운 이미지를 넣어줄 수 있는데 해당 이미지를 눌러도 select group의 후보들이 나오게 하기 위해서는 스타일링을 위해 넣어준 이미지에 pointer-events:none을 적용해야 select 그룹을 누른 효과가 동일하게 작동한다

🤗 2021.10.23 component 생성

- 애플이 권장하는 최소 버튼 크기는 44px \* 44px -> 유저가 터치를 할 때에 편하게 작동하기 위한 최소 크기

- table 스타일링 작업할 때 유용한 스타일 속성들

1.  table-layout : fixed -> table의 크기를 고정시키는 역할을 한다
2.  border-collapse: collapse -> table td th 간에 border를 기존 스타일링 그대로 적용하게 되면 element 사이에 간격이 존재하게 되는데 이러한 간격을 없애주는 역할을 한다
3.  vertical-align: top -> 테이블내 문자열들이 칸의 위쪽부터 채워지도록

🍞 2021.10.24 product-tab 마크업 디자인 작업

- a href에 element의 id를 넣게 되면 (예를 들어 "#test1") 링크 클릭시 해당 element로 화면이 이동하게 된다
  하지만 a tag의 기능을 활용하게 되면 브라우저 히스토리에 클릭마다 기록이 되기 때문에 유저의 사용경험을 떨어 뜨린다 -> 대신해서 button을 사용하자!

- fixed on scroll
  : position: sticky을 적용하게 되면 스크롤을 내리게 되어도 지정한 위치에 해당 element가 계속 위치하게 된다

🍟 2021.10.25 제품 상세설명 쪽 스타일링

- 그라데이션 만들기
  그라데이션 효과를 적용하고 싶은 이미지나 element 위에 새로운 div element를 생성한다 (+ 보통은 position: absolute을 활용하여 위치를 조정한다)
  해당 element에 background-img: linear-gradient() 를 적용해 그라데이션을 조절하여 효과를

🧈 2021.10.26 리뷰부분 마크업 + 스타일링

- flex box에서의 order 의 역할
  : 가상 요소를 활용해서 스타일링 작업을 하는 경우나
  markup한 순서와 다르게 배열을 해야하는 경우에는 flex에서 제공하는 order기능을 활용하자 사용방법은 간단하게 첫번째로 오길 바라는 요소에서 부터 차례대로 order: 1 식으로 순서를 부여하면 된다

🍔 2021.10.27 review card 경우의 수에 따른 스타일링 작업

🌼 2021.10.28 review card 리뷰가 하나도 없을 경우에 따른 스타일링 작업 + 애니메이션 작업 + 문의사항 답변 부분 마크업 스타일링 작업

- 막대그래프가 스르륵 채워지는 애니메이션 만들때의 팁
  : width값을 사용해서 애니메이션을 제작해도 되지만 translate3d를 사용하면 더 자연스러운 에니메이션 구현이 가능하다

예를들어 기본 상태에서 (가로로 누워있는 그래프라면) translateX(-100%)를 적용해 색깔이 채워진 부분 자체를 화면상에서 보이지 않게 처리한다 그리고 다시 translateX(0)으로 바뀌는 식으로 적용한다 (+자바스크립트로 스크롤을 사용해 애니메이션 시작 지점을 설정해주면 완성도가 높아질 수 있다)

```
@keyframes slide-active-bar {
  0% {
    transform: translate3d(-100%, 0, 0);
  }
  100% {
    transform: translate3d(0, 0, 0);
  }
}
```

🎭 2021.10.29 문의사항에 대해서 마크업 스타일링 작업 + 추전 제품 부분 마크업

🥼 2021.10.30 추천상품 반응형 에 따른 스타일 구현

- 100% - 20px와 같이 전체 width 값에서 특정 px값(예시 마진 값) 을 빼고 길이를 구하고 싶을때 calc() 함수 사용하기!

예시) width: calc(100% - 20px);

- 이미지 위에 마우스 올렸을 때에 이미지 크기 일시적으로 키우기를 하고 싶을 때에는 trasnform: scale(1.5) 식으로 transform을 활용한다

- height값이 명확하게 정해져 있지 않은 상태(예를들어 기기에 따라서 반응형으로 width, height값이 달라지거나 유저가 올리는 이미지가 정사각형 아닌 경우 등등)
  에서 1:1비율에 맞춰서 이미지 크기를 조정하고 싶다면 width:100%; height: 0;를 준 후 padding-bottom: 100%;를 주면 된다
  (\*width는 부모의 값을 기준으로 값이 정해지고 height는 자식 요소들의 크기에 따라서 값이 정해진다 즉 둘의 기준점이 다르기 때문에 height에 %를 적용해서 동일한 효과를 줄 수 없다 )

  참고로 img를 감싸고 있는 요소에게 width: 100 height 0 padding-bottom: 100%식으로 적용을 했다면, img에게는 position:absolute를 통해 가운데 정렬을 해서 크기를 맞출 수 있다 (참고로 img의 width와 height 값은 모두 100% 부모 요소에게는 position:relatvie)

  만약 2:1의 비율의 크기를 가지고 싶다면 padding-bottom: 50%를 준다

- truncate : 한줄로 된 text에서 일정 부분을 초과한 텍스트를 ...로 처리할 때 사용

- line-clamp: 두줄 이상으로 나누어진 text에서 일정 부분을 초과한 텍스트를 ...으로 처리할 때 사용

  ->사용방법: ...처리를 원하는 element에 적용하기

  ```
  display: -webkit-box;
  -webkit-line-clamp: 2; // text가 몇줄로 구성될 것인지에 따라 숫자 넣기
  -webkit-box-orient: vertical;
  overflow: hidden;
  ```

  🎃 2021.10.31 유저들의 스타일링샷 부분 마크업 + 스타일링 작업 + slider 효과 적용

✨ 2021.11.01 유저들의 스타일링샷 스타일링 작업 / orderCTA 마크업 + 스타일링 작업 완료

- tiny-slider.js 사용시 팁

1. link를 통해서 import 하는 형식
   (공식문서 : https://www.npmjs.com/package/tiny-slider )
2. 화살표의 경우 controlsContainer를 활용해서 새롭게 스타일링이 가능하다
3. 미리보기 thumbnail방식도 작업 가능
4. 반응형에 따른 대응도 가능
5. gutter와 edgePadding을 통해서 slider간의 간격 조정 가능

- CTA : Call To Action의 줄임말

- scroll이 활성화된 영역만 가능하도록 하는 방법 :
  overscroll-behavior: contain

- sticky 사용시 (스크롤을 내리다가 특정 위치부터 고정시키기 원할 때 사용) top을 통해서 위치를 조정해 주어야 한다

=> 현재 게시 되어 있는 곳 까지 강의 수강 완료 👊 후에 강의 업데이트 시 다시 시작 예정!
