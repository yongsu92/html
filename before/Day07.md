## **CSS 기초**

1. CSS(Cascading Style Sheets) : CSS는 HTML과 함께 웹 표준의 기본 개념으로 웹 문서의 디자인 요소를 담당한다. 여기서 Style Sheet는 한 문서에서 반복해 쓰이는 style들을 모아 놓은 것으로, 웹 문서에서 style이란 HTML 문서에서 겉모습을 결정짓는 내용들을 가르킨다. HTML에서 style을 지정하지 않고 CSS를 따로 생성하는 이유는 개별적인 두 요소를 만들어서 내용이 바뀌어도 디자인 요소는 영향을 받지 않고, 다양한 기기에 맞게 탄력적인 문서를 생성할 수 있기 때문이다.

2. Style 형식

   > p {test-align: center;}

   - p(selector) : 선택자
   - test-align : 스타일 속성
   - center : 속성 값
     > p {test-align: center; font-size:16px}
   - 복수의 속성은 ; 으로 구분한다.

3. 내부 스타일 시트와 외부 스타일 시트

   - 내부 스타일 시트는 head 태그 안에서 지정할 수 있다. 하지만 여러 문서에 같은 스타일을 지정해 주기 위해서는 각 문서에 같은 스타일 형식을 지정해 주어야 하므로 서버공간과 다운로드등의 시간을 낭비할 수 있다.
   - 외부 스타일 시트는 내부 스타일 시트의 단점을 보안한 것으로 같은 스타일을 하나의 시트에 저장하고 link태그를 이용해 불러와서 문서에 스타일을 적용한다.

   > link rel="stylesheet" href="외부 스타일 파일 경로"

4. 인라인 스타일 : 스타일을 적용하고 싶은 태그 안에서 style = "스타일 속성:속성값;"을 적용해 주면 해당 태그만 스타일이 적용된다.

5. 주요 선택자

   1. 전체 선택자(universal selector) : 전체 선택자는 \*로 표시하고 스타일을 모든 요소에 적용할 때 사용한다. 주로 모든 하위 요소에 한꺼번에 스타일을 적용할 때 사용하여 문서의 여백이나 글꼴 크기 등 기본 스타일을 초기화 할때 사용한다.

   2. 태그 선택자(tag selector) : 태그 선택자는 특정 태그가 쓰인 모든 요소에 스타일을 적용한다.

   3. 클래스 선택자(class selector) : 클래스 선택자는 특정 부분에만 다른 스타일을 적용할 때 사용한다. 여러 스타일을 적용할 때는 클래스 선택자를 나란히 지정하면 된다.

   4. id 선택자(id selector) : id 선택자도 class 선택자와 마찬가지로 특정 부분에 스타일을 지정할 때 사용한다. 클래스 선택자와 다르게 .이 아닌 #을 사용한다. 클래스 선택자와의 차이점은 클래스 선택자는 문서 안에서 여러번 사용할 수 있지만, id 선택자는 한번만 사용할 수 있다.

   5. 그룹 선택자 : 여러 선택자에 같은 스타일을 적용할 경우 ,를 이용해서 나열하고 하나의
      스타일만 지정해 주면 된다.

6. CSS와 스타일 시트 : '스타일 시트'라는 용어 앞에 Cascading용어를 합친 것으로 위에서 아래로 흐르는 스타일 시트라는 뜻을 가진다. 만약 p 선택자에 스타일을 적용할 때 글자 색은 문서 전체의 글자 색 또는 p 선택자의 지정 글자 색 등 여러 스타일이 동시에 적용될 수 있다. 이때 스타일 간의 충돌을 막이 위한 방법이 '위에서 아래로 흐르며 적용되는 방법'이다.

   1. 스타일 우선순위 : 스타일 우선순위는 캐스케이딩에서 가장 중요한다. 여기서 우선순위란 어떤 스타일을 먼저 적용할 것인지 결정하는 규칙을 말한다.

      - importance (우선순위가 높은 순서)
        1. 사용자 스타일 시트 - 저시력자나 색약자 등과 같이 특별한 조건이 필요한 사용자에 맞게 구성해 놓은 스타일 시트이다. 이 시트는 시스템을 통해 만들어진 것으로 제작자가 제어할 수 없다.
        2. 제작자가 만든 스타일 중 !important가 붙은 스타일 - 제작자 스타일 시트는 사이트를 제작하면서 만든 스타일 시트를 말한다. 시트를 만들때 최우선으로 적용해야 할 스타일에는 !important를 붙일 수 있다.
        3. 제작자가 만든 일반 스타일
        4. 기본적인 브아우저 스타일 시트
      - Specificity (우선순위가 높은 순서)
        1. 인라인 스타일
        2. id 스타일
        3. 클래스 스타일
        4. 태그 스타일
      - Source Order
        1. 스타일 시트에서 중요도와 적용 범위가 같다면 스타일 우선순위를 정하는 것은 소스의 순서이다.

   2. 스타일 상속 : 태그들의 포함 관계에 따라 부모 묘소의 스타일을 자식 요소로 위에서 아래로 전달한다.
      - 웹 문서에서 사용하는 여러 태그들은 서로 포함관계가 있는데 포함하는 태그를 부모요소, 포함된 태그를 자식 요소라고 한다. 자식 요소에 특정 스타일을 지정하지 않으면 부모의 스타일이 적용되는데 이를 상속이라고 한다.(객체 지향언어에서 클래스 상속과 같은 개념) 하지만 부모요소의 배경색과 이미지는 스타일이 상속되지 않는다.

7. CSS3 : CSS3는 작은 CSS module로 이루어져 있다.

   1. CSS3와 브라우저 접두사(prefix) - 브라우저 접두사를 붙여 사용할 때는 각 브라우저 접두사를 붙인 속성을 먼저 쓰고 표준이 정해진 후 사용할 속성을 맨 마지막에 사용한다.
      1. -webkit- : 웹키트 방식 브라우저용(사파리,크롬 등)
      2. -moz- : 게코 방식 브라우저용(모질라,파이어폭스 등)
      3. -o- : 오페라 브라우저
      4. -ms- : 마이크로소프트 인터넷 익스플로러
   2. 브라우저 접두사 자동으로 붙이기 - 'prefix-free'라는 자바스크립트 파일을 이용하면 매번 접두사를 붙이이 않아도 된다.

8. 글꼴 관련 스타일 : 텍스트가 아닌 글자의 모양새를 살펴본다.
   1. font-family : 글꼴을 지정한다. 글꼴의 경우 지정한 글꼴이 없을 수 있기 때문에 한 가지 이상의 글꼴을 지정해 준다.
   2. @font-face : 웹 폰트를 사용한다. 웹 폰트란 웹 문서 안에 글꼴 정보도 함께 저장했다가 사용자가 웹 문서에 접속하면 글꼴을 사용자 시스템으로 다운로드시키는 방식입니다.
      1. 구글 웹 폰트 사용하기
      2. 직접 웹 폰트 업로드해 사용하기
   3. font-size : 글자의 크기를 조절한다.
      1. 속성
         - <절대크기> : 브라우저에서 지정한 글자 크기이다. 사용할 수 있는 값은 xx-small/x-small/small/medium/large/x-large/xx-large 이다.
         - <상대크기> : 부모 요소의 글자 크기(font-size)를 기준으로 더 크게 표시하거나 작게 표시한다. 사용할 수 있는 값은 larger/smaller 이다.
         - <크기> : 브라우저와 상관없이 글자 크기를 직접 지정한다. 사용할 수 있는 단위는 em,ex,px,pt 이다. 크기를 따로 지정하지 않으면 텍스트 문단의 크기는 16px로 표시한다.
           - em : 해당 글꼴의 대문자 M의 너비를 기준으로 크기를 조정한다.
           - ex : x-height. 해당 글꼴의 소문자 x의 높이를 기준으로 크기를 조정한다.
           - px : 픽셀. 모니터에 따라 상대적 크기가 된다. 주로 px단위를 많이 사용하지만 모니터의 크기에 상대적이기 때문에 모바일에서는 em 단위를 사용한다.
           - pt : 포인트. 일반 문서에서 많이 사용하는 단위이다.
         - <백분율> : 부모 요소의 글자 키기를 기준으로 해당하는 %를 계산해 표시한다.
   4. font-weight : 글자의 굵기를 조절한다.
      1. 속성값은 다음과 같다.
         - normal : 일반적인 형태로 기본값이다.
         - bold/lighter/bolder : 굵게/원래 굵기 보다 더 가늘게/원래 굵기 보다 더 굵게 나타낸다.
         - 100 ~ 900 : 400은 normal, 700 bold에 해당하며 숫자 값을 조절해 좀 더 세밀히 글꼴 두께를 조정할 수 있다.
   5. font-variant : 영어 글꼴에는 '작은 대문자'라는 독특한 설정이 있다. font-variant는 대문자를 소문자 크기에 맞추어서 작게 표시해 준다. 사용할 수 있는 값은 normal/small-caps이고 small-caps가 작은 대문자를 나타내는 속성이다.
   6. font-style : 글자 스타일 지정한다. 속성 값으로는 normal과 italic,oblique(이탤릭체)가 있다.
   7. font 속성 : 글꼴 속성을 한꺼번에 묶어 표현한다. 위의 속성들을 한꺼번에 묶어서 표현할 수 있다.(font-style/font-variant/font-weight/font-size&line_height/font-family)
      1. 속성
         - font-\* : font-로 시작하는 글꼴 관련 속성을 한꺼번에 나열한다.
         - caption : caption에 어울리는 글꼴 스타일을 표시해준다.
         - icon : icon에 어울리는 글꼴 스타일을 표시해준다.
         - menu : Dropdown 에 어울리는 글꼴 스타일을 표시해준다.
         - message-box : 대화상자에 어울리는 글꼴 스타일을 표시해준다.
         - small-caption : 작은 캡션에 어울리는 글꼴 스타일을 표시해준다.
         - status-bar : 상태 표시줄에 어울리는 글꼴 스타일을 표시해준다.
9. 텍스트 관련 스타일 : 글꼴이 폰트와 관련 있다면 텍스트는 글자와 단어들, 그리고 글자들로 이루어진 문단에서 사용되는 스타일이다.
   1.  color : 글자의 색을 지정한다. 색상 값은 16진수, rgb, hsl 또는 색상 이름으로 표기할 수 있다.
   2.  text-decoration : 텍스트에 줄을 표시하거나 제거해 준다.
       1.  속성
         - none : 밑줄을 표시하지 않는다.
         - underline : 밑줄을 표시한ㄷ.
         - overline : 영역 위로 선을 그린다.
         - line-through : 영역을 가로지르는 취소선을 그린다.
   3.  text-transform : 텍스트 대/소문자를 원하는 대로 바꿔준다.
       1.  속성
         - none : 변환하지 않는다.
         - capitalize : 시작하는 <u>첫 번째 글자</u>를 대문자로 변환한다.
         - uppercase : 모든 글자를 대문자로 변환한다.
         - lowercase : 모든 글자를 소문자로 변환한다.
         - full-width : 가능한 모든 문자를 전각 문자로 변환한다.
   4.  text-shadow : 텍스트에 그림자 효과 추가한다.
   5.  white-space : 입력된 여러 개의 공백을 처리한다.
      1.  속성   
         - nomarl : 여러 개의 공백을 하나로 표시한다.
         - nowrap : 여러 개의 공백을 하나로 표시하고 영역 너비를 넘어가는 내용은 줄을 바꾸지 않고 계속 한 줄로 표시한다.
         - pre : 여러 개의 공백을 그대로 표시하고 영역 너비를 넘어가는 내용은 줄을 바꾸지 않고 ㄱ{속 한 줄로 표시한다.
         - pre-line : 여러 개의 공백을 하나로 표시하고 영역 너비를 넘어가는 내용은 자동으로 줄을 바꿔 표시한다.
         - pre-wrap : 여러 개의 공백을 그대로 표시하고 영역 너비를 넘어가는 내용은 자동으로 줄을 바꿔 표시한다.
   6.  letter-spacing, word-spacing : 텍스트의 자간을 조절할 수 있다. 자간의 크기는 em 단위로 지정하는 것이 글꼴의 변화에 쉽게 대응할 수 있다.

10. 문단 관련 스타일
   1. direction : 글자 쓰기 방향을 지정한다.
      1. 속성 
         - ltr : 왼쪽에서 오른쪽(left-to-right)으로 텍스트를 표시한다.
         - rtl : 오른쪽에서 왼쪽(right-to-left)으로 텍스트를 표시한다.
   2. text-align : 텍스트를 지정한다.
      1. 속성
         - start : 현재 텍스트 중의 시작 위치를 맞추러 문단을 정렬한다.
         - end : 현재 텍스트 줄의 끝 위치에 맞추어 문단을 정렬한다.
         - left : 왼쪽에 맞춘다.
         - right : 오른쪽에 맞춘다.
         - center : 가운데에 맞춘다.
         - justify : 양쪽에 맞춘다.
         - match-parent : 부모 요소를 따라 문단을 정렬한다. 하지만 부모의 요소가 start,end일 경우 ltr,rtl에 맞춰서 left,right속성을 가진다.
   3. text-justify : 정렬 시 공백 조절한다.
      1. 속성
         - auto : 웹 브라우저에서 자동으로 지정한다.
         - none : 정렬하지 않습니다.
         - inter-word : 단어 사이의 공백을 조절해 정렬합니다.
         - distribute : 인접한 글자 사이의 공백을 똑같이 맞추어 정렬한다.
   4. text-indent : 텍스트를 들여씁니다.

- 궁금한 점 : 전체 선택자로 마진을 주게 되면 span태그에서 공백이 발생하게 된다. 이유와 해결방법은?