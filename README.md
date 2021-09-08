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
