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