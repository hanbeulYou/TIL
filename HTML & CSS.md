# HTML & CSS

## Web이란?

- 웹 사이트의 구성 요소
    - 웹 사이트란 브라우저를 통해서 접속하는 웹 페이지(문서)들의 모음
    - 여러가지 정보를 담고 있으며, 마우스로 클릭하면 다른 웹 페이지로 이동하는 ‘링크’들이 있음.
    - HTML → 구조 (계산 X)
    CSS → 표현
    JavaScript → 동작
    - 웹 사이트와 브라우저
        - 웹 사이트는 브라우저를 통해 동작
        - 브라우저마다 동작이 약간씩 달라서 문제가 생기는 경우가 많음(파편화)
        - 해결책으로 웹 표준이 등장
    - 웹 표준
        - 웹에서 표준적으로 사용되는 기술이나 규칙
        - 어떤 브라우저든 웹 페이지가 동일하게 보이도록 함(크로스 브라우징)
        - 브라우저 호환성 검사 : Can I Use? 사이트 활용

## HTML

Hyper Text Markup Language

- Hyper Text
    - 참조(하이퍼링크)를 통해 사용자가 한 문서에서 다른 문서로 즉시 접근할 수 있는 텍스트
    - Markup Language
        - 태그 등을 이용하여 문서나 데이터의 구조를 명시하는 언어
        - 대표적인 예 : HTML, Markdown
- HTML
    
    웹 페이지를 작성(구조화)하기 위한 언어
    
    - HTML 스타일 가이드
        - 2 space
    - 기본 구조
        - html : 문서의 최상위(root) dyth
        - head : 문서 메타데이터 요소
        - 문서 제목, 인코딩, 스타일, 외부 파일 로딩 등
        - 일반적으로 브라우저에 나타나지 않는 내용
        - body : 문서 본문 요소
        - 실제 화면 구성과 관련된 내용
    - head 예시
        - <title> : 브라우저 상단 타이틀
        - <meta> : 문서 레벨 메타데이터 요소
        - <link> : 외부 리소스 연결 요소 (CSS파일, favicon 등)
        - <script> : 스크립트 요소 (JavaScript 파일/코드)
        - <style> : CSS 직접 작성
        - Open Graph Protocol : 메타 데이터를 표현하는 새로운 규약 (썸네일)
        - HTML 문서의 메타 데이터를 통해 문서의 정보 전달
        - 메타 정보에 해당하는 제목, 설명 등을 쓸 수 있도록 정의
    - 요소 (Element)
        - HTML의 요소는 태그와 내용으로 구성되어 있다.
        `<h1>contents</h1>`
        <시작태그>내용<종료태그>
        - 그 정보의 성격과 의미를 정의
        - 내용이 없는 태그들도 존재(닫는 태그 X)
        - br, hr, img, input, link, meta
        - 중첩될 수 있음
        - 오류를 반환하는 것이 아닌 레이아웃이 깨져서 출력되기 때문에 디버깅이 어려움
    - 속성 (Attribute)
        - `<a href=”https://google.com”></a>`
        - 속성명=속성값 형식 (공백 X, 쌍따옴표 사용)
        - 태그별로 사용할 수 있는 속성이 다름
        - 속성을 통해 태그의 부가적인 정보 설정 가능
        - 요소의 시작 태그에 작성, 보통 이름과 값이 하나의 쌍으로 존재
        - 태그와 상관없이 사용 가능한 속성들도 있음 (HTML Global Attribute)
        - HTML Global Atrribute 예시
        - id : 문서 전체에서 유일한 고유 식별자 지정
        - class : 공백으로 구분된 해당 요소의 클래스의 목록(CSS, JS에서 요소를 선택하거나 접근)
        - data-* : 페이지에 개인 사용자 정의 데이터를 저장하기 위해 사용
        - style : inline 스타일
        - title : 요소에 대한 추가 정보 지정
        - tabindex : 요소의 탭 순서
    - 시맨틱 태그
        - HTML 태그가 특정 목적, 역할 및 의미적(semantic value) 가치를 가지는 것
        - Non semantic 요소로는 div, span 등이 있으며, a, form, table 태그들도 시맨틱 태그로 볼 수 있음
        - HTML5에서는 div 태그를 대체하여 사용하기 위해 의미론적 요소를 담은 태그들이 추가됨
        - 대표적인 시맨틱 태그 목록
        - header : 문서 전체나 섹션의 헤더
        - nav : 내비게이션
        - aside : 사이드에 위치한 공간, 메인 콘텐츠와 관련성 적은 콘텐츠
        - section : 문서의 일반적인 구분, 컨텐츠의 그룹을 표현
        - article : 문서, 페이지, 사이트 안에서 독립적으로 구분되는 영역
        - footer : 문서 전체나 섹션 푸터(마지막 부분)
        - 의미론적 마크업
        - 의미 있는 정보의 그룹을 태그로 표현
        - 요소의 의미가 명확해지기 떄문에 코드의 가독성을 높이고 유지보수를 쉽게 함
        - 검색 엔진 최적화(SEO)를 위해서 메타 태그, 시맨틱 태그 등을 통한 마크업을 효과적으로 활용해야함
    - 렌더링 : 웹사이트 코드를 사용자가 보게 되는 웹 사이트로 바꾸는 과정
        - DOM (Document Object Model) 트리
        - 텍스트 파일인 HTML 문서를 브라우저에서 렌더링 하기 위한 구조
        - HTML 문서에 대한 모델을 구성
        - HTML 문서 내의 각 요소에 접근 / 수정에 필요한 프로퍼티와 메서드를 제공
    
- HTML 문서 구조화
    - 인라인 / 블록 요소
        - 인라인 요소 : 글자처럼 취급
        - 블록 요소 : 한 줄 모두 사용
    - 텍스트 요소
        - `<a></a>` : href 속성을 활용하여 다른 URL로 연결하는 하이퍼링크 생성
        - `<b></b>`, `<strong></strong>` : 굵은 글씨 요소(강조)
        - `<i></i>`, `<em></em>` : 기울임 글씨 요소(강조)
        - `<br>` 텍스트 내에 줄 바꿈 생성
        - `<img>` : src 속성을 활용하여 이미지 표현
        - `<span></span>` 의미 없는 인라인 컨테이너
    - 그룹 컨텐츠
        - `<p></p>` : 하나의 문단
        - <hr> : 문단 레벨 요소에서 주제의 분리를 의미, 수평선으로 표현 됨
        - `<ol></ol>` : 순서가 있는 리스트(ordered)
        - `<ul></ul>` : 순서가 없는 리스트(unordered)
        - `<pre></pre>` : HTML에서 작성한 내용을 그대로 표현, 보통 고정폭 글꼴이 사용되고 공백 문자를 유지
        - `<blockquote></blockquote>` : 텍스트가 긴 인용문, 주로 들여쓰기를 한 것으로 표현됨
        - `<div></div>` : 의미 없는 블록 레벨 컨테이너
    - form
        - <form>은 정보(데이터)를 서버에 제출하기 위해 사용하는 태그
        - action : form을 처리할 서버의 URL (데이터를 보낼 곳)
        - method : form을 제출할 때 사용할 HTTP 메서드 (GET or POST)
        - enctype : method가 post인 경우 데이터의 유형 
        - application/x-www-form-urlencoded : 기본값, 
        - multipart/form-data : 파일 전송시(input type이 file인 경우)
    - input
        - 다양한 타입을 가지는 입력 데이터 유형과 위젯이 제공됨
        - name : form control에 적용되는 이름 (이름/값 페어로 전송)
        - value : form control에 적용되는 값 (이름/값 페어로 전송)
        - required, readonly, autofocus, autocomplete, disabled 등
    - input label
        - label을 클릭하여 input 자체의 초점을 맞추거나 활성화 시킬 수 있음
        - 사용자는 선택할 수 있는 영역이 늘어나 웹/모바일(터치) 환경에서도 편하게 사용할 수 있음
        - label 과 input 입력의 관계까 시각적 뿐만 아니라 화면리더기에서도 label을 읽어 쉽게 내용을 확인할 수 있도록 함
        - `<input>`에 id 속성을, `<label>`에는 for 속성을 활용하여 상호 연관을 시킴(for-id는 붙어있지 않아도 괜찮음)
    
    ```html
    <label for="agreement">개인정보 수집에 동의합니다.</label>
    <input type="checkbox" name="agreement" id="agreement">
    ```
    
    - input 유형 - 일반
        - text : 일반 텍스트 입력
        - password : 입력 값 보이지 X, (*)로 표현
        - email : 이메일 형식이 아닌 경우 제출 불가
        - number : min, max, step 속성을 활용하여 숫자 범위 설정
        - file : accept 속성을 활용하여 파일 타입 지정 가능
    - input 유형 - 항목 중 선택
        - 일반적으로 label 태그와 함께 사용하여 선택 항목을 작성
        - 동일 항목에 대하여는 name을 지정하고 선택된 항목에 대한 value를 지정해야 함
        - checkbox : 다중선택
        - radio : 단일 선택

## CSS

Cascading Style Sheets

스타일을 지정하기 위한 언어 : 선택하고, 스타일을 지정

- CSS 구문
    
    ```css
    /* h1 : 선택자(h1 태그) */
    h1 {
    	color: blue; /* 선언 */ 
    	font-size: 15px; /* 속성: 값 */
    }
    ```
    
    - CSS
        - 선택자를 통해 스타일을 지정할 HTML 요소를 선택
        - 중괄호 안에서는 속성과 값, 하나의 쌍으로 이루어진 선언을 진행
        - 각 쌍은 선택한 요소의 속성, 속성에 부여할 값을 의미
        - 속성 (Property) : 어떤 스타일 기능을 변경할지 결정
        - 값 (Value) : 어떻게 스타일 기능을 변경할지 결정
    - CSS 정의 방법
        - 인라인 (inline)
        
        ```html
        <h1 style="color : blue; font-size: 100px;">내용</h1>
        ```
        
        - 내부 참조 (embedding) : <style>
        
        ```html
        <head>
          <style>
            h1 {
        			color: red;
        			font-size: 40px;
            }
        	</style>
        </head>
        ```
        
        - 외부 참조 (link file) : 분리된 CSS 파일
        
        ```html
        <link rel="stylesheet" href="CSS 경로">
        ```
        
        ```css
        .large-box {
            width: 400px;
            height: 400px;
            border: 2px black solid;
        }
        ```
        
- CSS 선택자 (Selector)
    - 기본 선택자
        - 전체 선택자 `*`
        - 요소 선택자 `h1` 
        - HTML 태그를 직접 선택
        - 클래스 선택자 `.green` 
        - 마침표 문자로 시작하며, 해당 클래스가 적용된 항목을 선택
        - 아이디 선택자 `#purple` 
        - # 문자로 시작하며, 해당 아이디가 적용된 항목을 선택
        - 일반적으로 하나의 문서에 1번만 사용
        - 여러 번 사용해도 동작하지만 단일 id 사용 권장
        - 속성 선택자
    - 결합자 (Combinators)
        - 자손 결합자 `.box p`, 자식 결합자
        - 일반 형제 결합자, 인접 형제 결합자
    - 의사 클래스/요소 (Pseudo Class)
        - 링크, 동적 의사 클래스
        - 구조적 의사 클래스, 기타 의사 클래스, 의사 엘리먼트, 속성 선택자
    - (꿀팁) Lorem : 랜덤 text 생성
    - **CSS 적용 우선순위 (Cascading Order)**
        - 범위가 좁을수록 강하다!
        - 중요도 (Importance) : 사용시 주의
        **- !important**
        - 우선 순위 (Specificity)
        - 인라인 > id > class, 속성, psuedo-class > 요소, pseudo-element
        - CSS 파일 로딩 순서
    - CSS 상속 : **MDN에서 확인**
        - 상속을 통해 부모 요소의 속성을 자식에게 상속함
        - 속성(프로퍼티) 중에는 상속이 되는 것과 되지 않는 것들이 있음
        - 상속 되는 것 예시
        - Text관련 요소 (font, color, text-align), opacity, visibility 등
        - 상속 되지 않는 것 예시
        - Box model 관련 요소 (width, height, margin, padding, border, box-sizing, display), position 관련 요소 (position, top/right/bottom/left, z-index) 등
        
- CSS 기본 스타일
    - 크기 단위
        - px (픽셀) : 고정적 단위
        - % : 백분율 단위, 가변적인 레이아웃에서 자주 사용
        - em : 바로 위 부모 요소에 대한 상속의 영향을 받음 + 배수 단위, 요소에 지정된 사이즈에 상대적인 사이즈를 가짐
        - rem : 상속의 영향을 받지 않음 + 최상위 요소(html)의 사이즈를 기준으로 배수 단위를 가짐
    - 크기 단위 (viewport)
        - 웹 페이지를 방문한 유저에게 바로 보이게 되는 웹 컨텐츠의 영역
        - 디바이스의 viewport를 기준으로 상대적인 사이즈가 결정
        - vw, vh, vmin, vmax
    - 색상 단위
        - 색상 키워드 (background-color : red;)
        - 대소문자 구분 X
        - red, blue, black과 같은 특정 색을 직접 글자로 나타냄
        - RGB 색상 (background-color : rgb(0, 255, 0);)
        - 16진수 표기법 혹은 함수형 표기법을 사용해서 특정 색을 표현
        - HSL 색상 (background-color : hsl(0, 100%, 50%);)
        - 색상, 채도, 명도를 통해 특정 색을 표현하는 방식
        - a는 alpha (투명도)
    - CSS 문서 표현
        - 텍스트
        - 서체(font-family), 서체 스타일(font-style, font-weight 등)
        - 자간(letter-spacing), 단어 간격(word-spacing), 행간(line-height) 등
        - 컬러(color), 배경(background-image, background-color)
        - 기타 HTML 태그별 스타일링
        - 목록(li), 표(table)
- 결합자 (Combinators)
    - 자손 결합자 (공백)
        - selectorA 하위의 모든 selectorB 요소
    - 자식 결합자 (>)
        - selectorA 바로 아래의 selectorB 요소
    - 일반 형제 결합자 (~)
        - selectorA의 형제 요소 중 뒤에 위치하는 selectorB 요소를 모두 선택
    - 인접 형제 결합자 (+)
        - selectorA의 형제 요소 중 바로 뒤에 위치하는 selectorB 요소를 선택
    
- Box model
    - CSS원칙 I : 모든 요소는 네모(박스 모델)이고 위에서부터 아래로, 왼쪽에서 오른쪽으로 쌓인다.
    - 하나의 박스는 네 부분(영역)으로 이루어짐
        - Margin : 테두리 바깥의 외부 여백. 배경색 지정 X, shorthand를 통해 표현 가능
        
        ```css
        .margin {
        	margin-top: 10px;
        	margin-right: 20px;
        	margin-bottom: 30px;
        	margin-left: 40px;
        }
        ```
        
        - Border : 테두리 영역
        
        ```css
        .border {
        	border-width: 2px;
        	border-style: dashed;
        	border-color: black;
        }
        ```
        
        - Padding : 테두리 안쪽의 내부 여백.
        - Content : 글이나 이미지 등 요소의 실제 내용
    - box-sizing
        - 기본적으로 모든 요소의 box-sizing은 content box
        - Padding을 제외한 순수 contents 영역만을 box로 지정
        - 일반적으로 우리가 영역을 볼 때는 border까지의 너비를 100px 보는 것을 원함
        - 그 경우 box-sizing을 border-box로 설정
    
    ---
    
    CSS 원칙 II : Display에 따라 크기와 배치가 달라진다.
    
    - 대표적으로 활용되는 display
    - display: block
        - 줄 바꿈이 일어나는 요소
        - 화면 크기 전체의 가로 폭을 차지
        - 블록 레벨 요소 안에 인라인 레벨 요소가 들어갈 수 있음
    - display: inline
        - 줄 바꿈이 일어나지 않는 행의 일부 요소
        - content 너비만큼 가로 폭을 차지함
        - width, height, margin-top, margin-bottom을 지정할 수 없음
        - 상하 여백은 line-height로 지정
    - 블록 레벨 요소와 인라인 레벨 요소
        - 대표적인 블록 레벨 요소 : div / ul, ol, li / p / hr / form 등
        - block의 기본 너비는 가질 수 있는 너비의 100%
        - 너비를 가질 수 없다면 자동으로 부여되는 margin
        - 대표적인 인라인 레벨 요소 : span / a / img / input, label / b, em, i, strong 등
        - inline의 기본 너비는 컨텐츠 영역만큼
    - 속성에 따른 수평 정렬
        - 왼쪽 정렬 : `margin-right: auto;` `text-align: left;`
        - 오른쪽 정렬 : `margin-left: auto;` `text-align: right;`
        - 가운데 정렬 : `margin-right: auto; margin-left: auto;` `text-align: center;`
    - display: inline-block
        - block과 inline 레벨 요소의 특징을 모두 가짐
        - inline처럼 한 줄에 표시할 수 있고, block처럼 width, height, margin 속성을 모두 지정할 수 있음
    - display: none
        - 해당 요소를 화면에 표시 X, 공간 부여 X
        - 이와 비슷한 `visibility: hidden` 은 해당 요소가 공간은 차지하나 화면에 표시만 X
        
- CSS Position
    
    문서 상에서 요소의 위치를 지정
    
    - static : 모든 태그의 기본 값 (기준 위치)
        - 일반적인 요소의 배치 순서에 따름 (좌측 상단)
        - 부모 요소 내에서 배치될 때는 부모 요소의 위치를 기준으로 배치 됨
    - 좌표 프로퍼티(top, bottom, left, right)를 사용하여 이동 가능
        - relative : 상대 위치
        - 자기 자신의 static 위치를 기준으로 이동(normal flow 유지)
        - 레이아웃에서 요소가 차지하는 공간은 static일 때와 같음(normal position 대비 offset)
        - absolute : 절대 위치
        - 요소를 일반적인 문서 흐름에서 제거 후 레이아웃에 공간을 차지 X (normal flow에서 벗어남)
        - static이 아닌 가장 가까이 있는 부모/조상 요소를 기준으로 이동(없는 경우 브라우저 화면 기준)
        - fixed : 고정 위치
        - 요소를 일반적인 문서 흐름에서 제거 후 공간을 차지 X (normal flow에서 벗어남)
        - 부모 요소와 관계없이 viewport를 기준으로 이동
        - sticky : 스크롤에 따라 static → fixed로 변경
        - 속성을 적용한 박스는 평소 문서 안에서 `position: static` 상태와 같이 일반적인 흐름에 따르지만, 스크롤 위치가 임계점에 이르면 `position: fixed`와 같이 박스를 화면에 고정할 수 있는 속성
    - CSS 원칙 III : position으로 위치의 기준을 변경
        - relative : 본인의 원래 위치
        - absolute : 특정 부모의 위치
        - fixed : 화면의 위치
        - sticky : 기본적으로 static이나 스크롤 이동에 따라 fixed로 변경