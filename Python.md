# Python

- 기초 문법
    - 코드 스타일 가이드
        - PEP8 ([https://peps.python.org/pep-0008/](https://peps.python.org/pep-0008/))
    - 들여쓰기
        - Space Sensitive
        - 문장을 구분할 때 들여쓰기 사용 (space 4번 or tabe 1번)
        - 한 코드 안에서는 반드시 한 종류의 들여쓰기 사용 (혼용 X)
    - 주석
        - 코드에 대한 설명
        - 한 줄 주석 : #
        - 여러 줄 주석 : “”” 또는 ‘’’
    - 변수(Variable)
        - 데이터를 저장하기 위해 사용
        - 추상화 : 복잡한 값들을 쉽게 사용할 수 있음
        - 코드의 가독성 증가, 의미 단위로 작성 가능, 코드 수정이 용이해짐
        - 동일 변수에 다른 데이터를 언제든 할당할 수 있음
        - 변수의 할당
        - 할당 연산자(=)를 통해 값을 할당(assginment)
        - 같은 값을 동시에 할당할 수 있음 ( a = b = 100 )
        - 다른 값을 동시에 할당할 수 있음 ( a, b = 10, 20 )
        - x, y = y, x : 각 변수의 값을 바꿔 저장할 수 있음
        - 식별자
        - 식별자의 이름은 영문 알파벳, 언더스코어(_), 숫자로 구성
        - 첫 글자에 숫자가 올 수 없음
        - 길이 제한이 없고, 대소문자 구별
        - keywords는 예약어(reserved words)로 사용할 수 없음 : `keyword.kwlist`로 확인 가능
        - 내장 함수나 모듈 등의 이름도 사용 X
    - 연산자
        - 산술연산자 : 기본적인 사칙연산 및 수식 계산
        +, -, *, /, //, **
        - 연산자 우선순위 : 수학에서의 우선순위와 같음
        
- 자료형
    - Numeric Type
        - int : 정수, integer
        - 진수표현 : 2진수(0b), 8진수(0o), 16진수(0x)
        - float : 부동소수점, 실수, floating point number
        - 컴퓨터는 2진수를 사용하기 때문에 10진법의 소수점 값을 변환시 계산이 무한대로 반복됨
        - 근사값만 표시
        - 계산시 예상치 못한 결과가 나타남 : Floating Point Rounding Error → Math 모듈 사용
        - complex : 복소수, complex number
    - String Type
        - 모든 문자는 str 타입
        - ‘ 또는 “ 를 활용하여 표기
        - 중첩 따옴표
        - 작은 따옴표가 들어 있는 경우 큰 따옴표로 문자열 생성
        - 큰 따옴표가 들어 있는 경우 작은 따옴표로 문자열 생성
        - Escape sequence : 역슬래시 뒤에 특정 문자가 와서 특수한 기능을 하는 문자 조합
        - \n : 줄바꿈
        - \t : 탭
        - \r : 캐리지 리턴
        - \0 : Null
        - \\ : \
        - /’ : 단일인용부호(’)
        - /” : 이중인용부호(”)
        - 문자열 연산
        - 덧셈 : 문자열 연결
        - 곱셈 : str을 n번 반복
        - String Interpolation : 문자열을 변수로 활용하여 만드는 법
        - % : formatting (%d, %s, %f 등)
        - str.format()
        - f-strings : python 3.6 이후 가능
    - None
        - 값이 없음을 표현
        - 반환 값이 없는 함수에서 사용하기도 함
    - Boolean
        - True / False 를 값으로 갖는 논리 자료형
        - 비교 연산자 : True / False 값을 return
            
            <. ≤, >, ≥, ==, ≠, is, is not
            
        - 논리 연산자
        - 여러 조건이 있을 때
        - A and B : A와 B 모두 True 시, True
        - A or B : A와 B 중 하나라도 True 시, True
        - Not : True를 False로, False를 True로
        - 논리 연산자의 주의할 점
        - falsy : flase는 아니지만 false로 취급 ( 0, 0.0, (). [], {}, None. “” )
        - 우선 순위 존재 : not > and > or
        - 논리 연산자의 단축 평가
        - 결과가 확실한 경우 두번째 값은 확인하지 않고 첫번째 값 반환
        - and 연산에서 첫 번째 값이 False → 첫 번째 값 반환
        - or 연산에서 첫 번째 값이 True → 첫 번째 값 반환
        
- 컨테이너
    
    여러개의 값 (데이터)를 담을 수 있는 것(객체)으로, 서로 다른 자료형을 저장할 수 있음
    
    - 컨테이너의 분류
        - 순서가 있는 데이터(Ordered)
        - 리스트 (가변형)
        - 튜플 (불변형)
        - 레인지 (불변형)
        - 순서가 없는 데이터(Unordered)
        - 세트 (가변형)
        - 딕셔너리 (가변형)
        
        ---
        
    - List
        - 여러 개의 값을 순서가 있는 구조로 저장
        - 대괄호 [] 또는 list()를 통해 생성
        - 어떤 자료형도 저장할 수 있음
        - 생성된 이후 내용 변경이 가능
        - Index를 통해 접근 가능 : list[i]
    - Tuple
        - 단일 항목의 경우 생성 시 값 뒤에 쉼표를 붙여야 함 : tuple_a = (1,)
        - 복수 항목의 경우 마지막 항목에 붙은 쉼표는 없어도 되지만, 넣는 것을 권장(Trailing comma) : tuple_b = (1, 2, 3,)
        - 튜플 대입 : 우변의 값을 좌변의 변수에 한번에 할당( x,y = (1, 2) )
    - Range
        - 숫자의 시퀀스를 나타내기 위해 사용
        - 주로 반복문과 함께 사용
        - 기본형 : range(n), 0부터 n-1까지 숫자의 시퀀스
        - 범위 지정 : range(n, m), n부터 m-1까지 숫자의 시퀀스
        - 범위 및 스텝 지정 : range(n, m, s) n부터 m-1까지 s만큼 증가시키며 숫자의 시퀀스
    - Slicing 연산자
        - 인덱스와 콜론을 이용해 문자열의 특정 부분만 잘라낼 수 있음
        - 콜론을 기준으로 앞 인덱스에 해당하는 문자는 포함되지만 뒤 인덱스에 해당 문자는 미포함
        print([1, 2, 3, 5][1:4]) → [2, ,3, 5]
        
        ---
        
    - Set (집합)
        - 중복되는 요소 없이, 순서에 상관 없는 데이터들의 묶음
        - 중복되는 원소가 있다면 하나만 저장
        - 인덱스를 이용한 접근 불가능
        - 집합 연산이 가능 : 합집합, 차집합, 교집합
        - 담고 있는 요소를 삽입, 변경, 삭제 가능(가변 자료형)
        - 중괄호 {} 혹은 set()을 통해 생성
        - 빈 set을 만들기 위해서는 set()을 반드시 활용
        - blank = {} → dict 자료형
        - set 연산자
        - ‘ | ’ (pipel ine) : 합집합
        - ‘ & ’ : 교집합
        - ‘ - ‘ : 차집합
        - ‘ ^’ : 대창차집합
        - 여집합은 존재 X
    - Dictionary
        - key-value(키-값) 쌍으로 이루어진 자료형 (python 3.7부터 ordered)
        - key는 변경 불가능한 데이터(immputable)만 활용 가능
        - string, integer, float, boolean, tuple, range
        - values는 어떠한 형태든 관계 없음
        - 중괄호 {} 혹은 dict()을 통해 생성
        - key를 통해 value에 접근
    
- 형 변환
    
    파이썬에서 데이터 형태는 서로 변환할 수 있음
    
    - 암시적 형 변환 (Implicit) : 사용자가 의도하지 않고 파이썬 내부적으로 자료형을 변환
        - bool : True + 3 → 4
        - numeric type (int, float) : 3 + 5.0 → 8.0
    - 명시적 형 변환 (Explicit) : 사용자가 특정 함수를 활용하여 의도적으로 자료형을 변환
        - int : str(형식에 맞는), float → int
        - float : str(형식에 맞는), int → float
        - str : int, float, list, tuple, dict → str
        
- 파이썬 프로그램 구성 단위
    - 식별자 (Identifier)
        - 변수, 함수, 클래스 등 프로그램이 실행되는 동안 다양한 값을 가질 수 있는 이름
        - 예약어 : 파이썬 키워드(명령어)
    - 리터럴 (Literal)
        - 읽혀지는 대로 쓰여있는 값 그 자체
    - 표현식 (Expression)
        - 새로운 데이터 값을 생성하거나 계산하는 코드 조각
    - 문장 (Statement)
        - 특정한 작업을 수행하는 코드 전체
        - 파이썬이 실행 가능한 최소한의 코드 단위
        - 표현식은 값을 생성하는 일부분이고, 문장은 특정 작업을 수행하는 코드 전체
    - 함수 (Function)
        - 특정 명령을 수행하는 묶음
    - 모듈 (Module)
        - 함수/클래스의 모음 또는 하나의 프로그램을 구성하는 단위
    - 패키지 (Package)
        - 프로그램과 모듈 묶음
        - 프로그램 : 실행하기 위한 것
        - 모듈 : 다른 프로그램에서 불러와 사용하기 위한 것
    - 라이브러리 (Library)
        - 패키지 모음
    
- 제어문
    - 조건문 : 조건문은 참/거짓을 판단할 수 있는 조건식과 함께 사용
        - 조건이 참인 경우 이후 들여쓰기 되어있는 코드 블록을 실행
        if 조건 == True :
            # Run this Code block
        - 이외의 경우 else 이후 들여쓰기 되어있는 코드 블록을 실행
        else : 
            # Run this Code block
        - 콜론 (:) 빼먹지 말기
        - 복수 조건문 : 복수의 조건식을 활용할 경우 elif를 활용하여 표현
        - 중첩 조건문 : 다른 조건문에 중첩되어 사용될 수 있음
        - 들여쓰기에 유의
    - 조건 표현식 (Conditional Expression)
        - 조건 표현식을 일반적으로 조건에 따라 값을 정할 때 활용
        - 삼항 연산자(Ternary Opeator)로 부르기도 함
        - true인 경우 값 if 조건 else false인 경우 값
    - 반복문 : 특정 조건을 만족할 때까지 같은 동작을 계속 반복
        - while 문 : 종료 조건에 해당하는 코드를 통해 반복문을 종료
        - 조건이 참인 경우 들여쓰기 되어있는 코드 블록이 실행
        - 코드 블록이 모두 실행되고, 다시 조건식을 검사하며 반복적으로 실행
        - 무한 루프를 하지 않도록 종료 조건이 반드시 필요
        - 복합  연산자 (In-Place Operator) : 연산과 할당을 합쳐 놓음. ex : +=
        - for 문 : 반복 가능한 객체를 모두 순회하면 종료 (별도의 종료 조건 X)
        - 시퀀스(string, tuple, list, range)를 포함한 순회 가능한 객체(iterable)의 요소를 모두 순회
        - 별도의 종료 조건 필요 
        - Iterable : 순회할 수 있는 자료형(string, list, dict, tuple, range, set 등) 및 순회형 함수(range, enumerate)
        - dictionary 순회  : 기본적으로 key를 순회, key를 통해 값을 활용
        - 추가 메서드를 활용한 dictionary 순회 : keys(), values(). items()
        - items() : (key, value)의 튜플로 구성된 결과
        - enumerate 순회 : 인덱스와 객체를 쌍으로 담은 열거형(enumerate) 객체 반환
        - (index, value) 형태의 tuple로 구성된 열거 객체를 반환
        - List Comprehension : 표현식과 제어문을 통해 특정한 값을 가진 리스트를 간결하게 생성
        - [code for 변수 in iterable]
        - [code for 변수 in iterable if 조건식]
        - Dictionary Comprehension
        - {key : value for 변수 in iterable}
        - {key : value for 변수 in iterable if 조건식}
        - 반복 제어 : break, continue, for-else
        - break : 반복문 종료
        - continue : continue 이후 코드 블록을 수행하지 않고, 다음 반복을 수행
        - for-else : 끝까지 반복문을 실행한 이후에 else 문 실행 (break를 통해 중간에 종료되는 경우 else문은 실행 X)
        - pass : 아무것도 하지 않음
        
- 함수
    - 함수를 사용하는 이유
        - 분해 (Decomposition) : 기능을 분해하고 재사용 가능하게 만듦
        - 추상화 (Abstraction) : 복잡한 내용을 모르더라도 사용할 수 있도록 만듦
    - 함수의 종류
        - 내장 함수 : 파이썬에 기본적으로 포함된 함수
        - 외장 함수 : import 문을 통해 사용, 외부 라이브러리에서 제공
        - 사용자 정의 함수
    - 함수의 정의
        - 특정한 기능을 하는 코드의 조각(묶음)
        - 특정 코드를 매번 다시 작성하지 않고, 필요시에만 호출하여 간편히 사용
    - 함수 기본 구조
        
        ```python
        def func_name(parameters) :
        	#Docstring
        	function body
        	return
        ```
        
        - 선언과 호출  (Define & Call)
        - def 키워드 활용
        - 들여쓰기를 통해 Function Body (실행될 코드 블록) 작성
        - parameter를 넘겨줄 수 있음
        - 함수는 동작 후에 return을 통해 결괏값을 전달함
        - 입력 (Input)
        - 문서화 (Docstring)
        - 범위(Scope)
    - 함수의 결과값
        - 값에 따른 함수의 종류
        - Void function : 명시적인 return 값이 없는 경우, None을 반환하고 종료
        - Value returnging function : 함수 실행 후 return 문을 통해 값 반환 (반환 후 함수 바로 종료)
        - 튜플(혹은 리스트와 같은 컨테이너)을 활용하여 두 개 이상의 값 반환
    - 함수의 입력
        - Parameter : 함수를 정의할 때, 함수 내부에서 사용되는 변수
        - Argument : 함수를 호출할 때, 넣어주는 값
        - 필수 Argument : 반드시 전달되어야 하는 argument (없으면 에러)
        - 선택 Argument : 값을 전달하지 않아도 되는 경우 기본값이 전달
        - Positional Arguments : 기본적으로 함수 호출 시 Argument는 위치에 따라 함수 내에 전달됨
        - Keyword Arguments : 직접 변수의 이름으로 특정 Argument를 전달할 수 있음
        - Keyword Argument 다음에 Postional Argument를 활용할 수 없음
        
        ```python
        def add (x, y) :
        	return x + y
        
        add (x = 2, y = 5)
        # add (2, y = 5)는 가능
        # add (x = 2, 5)는 불가능
        ```
        
        - Default Arguments Values : 기본값을 지정하여 함수 호출 시 argument 값을 설정하지 않도록 함
        
        ```python
        def add (x, y = 0) :
        	return x + y
        
        add (2)
        ```
        
        - 정해지지 않은 여러 개의 Arguments 처리
        - Asterisk 혹은 언패킹 연산자라고 불리는 * 덕분
        - 가변 인자(*args) : 여러 개의 Positional Argument를 하나의 필수 parameter로 받아서 사용
        
        ```python
        def add (*args) :
        	for arg in args :
        		print(arg)
        ```
        
        - 패킹 / 언패킹
        - 패킹 : 여러 개의 데이터를 묶어서 변수에 할당
        - 언패킹 : 시퀀스 속의 요소들을 여러 개의 변수에 나누어 할당
        - 언패킹시 변수의 개수와 할당하고자 하는 요소의 개수가 동일해야함
        - 언패킹시 왼쪽의 변수에 asterisk를 붙이면, 할당하고 남은 요소를 리스트에 담을 수 있음
        
        ```python
        numbers = (1, 2, 3, 4, 5)
        a, b, *rest = numbers
        print(a, b, rest) # 1 2 [3, 4, 5]
        
        a, *rest, b = numbers
        print(a, rest, b) # 1 [2, 3, 4] 5
        ```
        
        - 가변 키워드 인자(**kwargs)
        - 몇 개의 키워드 인자를 받을지 모르는 함수를 정의할 때 유용
        - 딕셔너리로 묶여 처리되며, parameter에 **를 붙여 표현
        
- 범위 (Scope)
    
    함수는 코드 내부에 local scope를 생성하며, 그 외의 공간인 global scope로 구분
    
    - Scope
        - Global Scope : 코드 어디에서든 참조할 수 있는 공간
        - Local Scope : 함수가 만든 Scope. 함수 내부에서만 참조 가능
    - Variable
        - Global Variable : Global Scope에 정의된 변수
        - Local Variable : Local Scope에 정의된 변수
    - 변수 수명 주기 (Lifecycle)
        - built-in scope : 파이썬이 실행된 이후부터 영원히 유지
        - global scope : 모듈이 호출된 시점 이후 혹은 인터프리터가 끝날 때까지 유지
        - local scope : 함수가 호출될 때 생성되고, 함수가 종료될 때까지 유지
    - 이름 검색 규칙 (Name Resolution)
        - 파이썬에서 사용되는 이름(식별자)들은 이름공간(namespace)에 저장되어 있음
        - 아래와 같은 순서로 이름을 찾아나가며, LEGB Rule 이라고 부름
        - Local Scope : 지역 범위 (현재 작업 중인 범위)
        - Enclosed Scope : 지역 범위 한 단계 위 범위
        - Global Scope : 최상단에 위치한 범위
        - Built-in Scope : 모든 것을 담고 있는 범위
        - 함수 내에서는 바깥 Scope의 변수에 접근 가능하나, 수정은 할 수 없음
    - global 문
        - 현재 코드 블록 전체에 적용되며, 나열된 식별자(이름)이 global variable임을 나타냄
        - global에 나열된 이름은 같은 코드 블록에서 global 앞에 등장할 수 없음
        - global에 나열된 이름은 parameter, for 루프 대상, 클래스/함수 정의 등으로 정의되지 않아야 함
    - nonlocal
        - global을 제외하고 가장 가까운 scope의 변수를 연결하도록 함
        - nonlocal에 나열된 같은 코드 블록에서 nonlocal 앞에 등장할 수 없음
        - nonlocall에 나열된 이름은 parameter, for 루프 대상, 클래스/함수 정의 등으로 정의되지 않아야 함
        - global과는 달리 이미 존재하는 이름과의 연결만 가능함
    - 함수의 범위 주의
        - 기본적으로 함수에서 선언된 변수는 Local scope에 생성되며, 함수 종료 시 사라짐
        - 해당 scope에 변수가 없는 경우 LEGB rule에 의해 이름을 검색
        - 변수에 접근은 가능하지만, 해당 변수를 수정할 수는 없음
        - 값을 할당하는 경우 해당 scope의 이름 공간에 새롭게 생성되기 때문
        - 단, 함수 내에서 필요한 상위 scope 변수는 argument로 넘겨서 활용
        - 상위 scope에 있는 변수를 수정하고 싶다면 global, nonlocal 키워드 활용
        - 가급적 사용 X, 함수로 값을 바꾸려면 argument로 return 값을 사용
        
- 함수의 응용
    - 내장 함수(Built-in Functions) : 파이썬 인터프리터에는 항상 사용할 수 있는 많은 함수와 형(type)이 내장되어 있음
    - map(function, iterable) 함수
        - 순회 가능한 데이터 구조(iterable)의 모든 요소에 함수(function) 적용하고 그 결과를 map object로 반환
    - filter(function, iterable) 함수
        - 순회 가능한 데이터 구조(iterable)의 모든 요소에 함수(function) 적용하고 그 결과가 True인 것들을 filter object로 반환
    - zip(*iterables) 함수
        - 복수의 iterable을 모아 튜플을 원소로 하는 zip object 반환
    - lambda 함수
        
        ```python
        # by def
        def triangle_area(b, h) :
        	return 0.5 * b * h
        
        # by lambda
        triangle_area = lambda b, h : 0.5 * b * h
        ```
        
    - 재귀 함수(recursive function)
        - 자기 자신을 호출하는 함수
        - 1개 이상의 base case(종료되는 상황)가 존재하고, 수렴하도록 작성
        - 주의 사항
        - 메모리 스택이 넘치게 되면(stack overflow) 프로그램이 동작하지 않게 도
        - 파이썬에서는 최대 재귀 깊이(maximum recursion depth)가 1,000번이므로, 호출 횟수가 이를 넘어가게 되면 recursion error 발생
        
- 모듈과 패키지
    
    다양한 기능을 하나의 파일로 → 모듈 (modul)
    
    다양한 파일을 하나의 폴더로 → 패키지 (package)
    
    다양한 패키지를 하나의 묶음으로 → 라이브러리 (library)
    
    이것을 관리하는 관리자 → pip
    
    패키지 활용 공간 : 가상환경
    
    - 모듈
        - 특정 기능을 하는 코드를 파이썬 파일(.py) 단위로 작성한 것
        ex : math.py
    - 패키지
        - 특정 기능과 관련된 여러 모듈의 집합
        - 패키지 안에는 또 다른 서브 패키지를 포함
    - 모듈과 패키지 불러오기
        
        ```python
        import module
        from module import var, function
        from module import *
        
        from package import module
        from package.module import var, function
        ```
        
    - 파이썬 패키지 관리자(pip)
        - PyPI(Python Package Index)에 저장된 외부 패키지들을 설치하도록 도와주는 패키지 관리 시스템
        - 최신 버전 / 특정 버전 / 최소 버전을 명시하여 설치 가능
        - 이미 설치되어 있는 경우 이미 설치되어 있음을 알리고 아무것도 하지 않음
        
        ```bash
        $ pip install SomePackage
        $ pip install SomePackage==1.0.5
        $ pip install 'SomePackage>=1.0.4'
        ```
        
    - 파이썬 패키지 관리자(pip) 명령어
        - 패키지 삭제
        
        ```bash
        $ pip uninstall SomepPackage
        ```
        
        - 패키지 목록 및 특정 패키지 정보
        
        ```bash
        $ pip list
        $ pip show SomePackage
        ```
        
        - 패키지 관리하기
        - 아래의 명령어들을 통해 패키지 목록을 관리하고 설치할 수 있음
        - 일반적으로 패키지를 기록하는 파일의 이름은 requirements.txt 로 정의함
        
        ```bash
        $ pip freeze > requirements.txt
        $ pip install -r requirements.txt
        ```
        
    - 사용자 모듈과 패키지
        - 패키지 만들기
    - 가상환경
        - 파이썬 표준 라이브러리가 아닌 외부 패키지와 모듈을 사용하는 경우
        - 모두 pip을 통해 설치해야 함
        - 복수의 프로젝트를 하는 경우 버전이 상이할 수 있음
        - 이러한 경우 가상 환경을 만들어 프로젝트별로 독립적인 패키지를 관리할 수 있음
        - 가상 환경을 만들고 관리하는데 사용되는 모듈 (Python 버전 3.5부터)
        - 특정 디렉토리에 가상 환경을 만들고, 고유한 파이썬 패키지 집합을 가질 수 있음
        - 특정 폴더에 가상 환경(패키지 집합 폴더 등)이 있고
        - 실행 환경(예 : bash)에서 가상환경을 활성화 시켜
        - 해당 폴더에 있는 패키지를 관리/사용함
        - 가상환경 생성
        
        ```bash
        $ python -m venv <폴더명>
        ```
        
        - 가상환경 활성화/비활성화
        
- 데이터 구조
    - 데이터 구조 활용
        - 데이터 구조를 활용하기 위해서는 메서드(method)를 활용
        - 메서드는 클래스 내부에 정의한 함수, 사실상 함수와 동일
        - 객체의 기능
        - data_structuer.method() 형태로 활용
        - 파이썬 공식 문서의 표기법
        - str.replace(old, new[,count])
        - old, new는 필수 / [,count]는 선택적 인자([, ~])
        
        ---
        
    - 문자열 (String Type)
        - 문자들의 나열 (sequence of characters)
        - 모든 문자는 str타입 (변경 불가능한 immutable)
        - 변수는 주소만 가지고 있음 (pointer 개념)
        - 문자열을 묶을 때 동일한 문장 부호를 활용(’ ’, “ ”)
        - 문자열 조회/탐색 및 검증 메서드
        - str.find(x) : x의 첫 번째 idx 반환, 없으면 -1 반환
        - str.index(x) : x의 첫 번째 idx 반환, 없으면 오류 발생
        - str.isalpha() : 알파벳 문자 여부(유니코드 상 letter, 한국어 포함)
        - str.isupper() : 모두 대문자 여부
        - str.islower() : 모두 소문자 여부
        - str.istitle() : 타이틀 형식(첫 번째 대문자) 여부
        - 문자열 검증 메서드
        - .isdecimal() ⊆ .isdigit() ⊆ .isnumeric() : 숫자 확인
        - 문자열 변경 메서드
        - str.replace(old, new[,count]) : 대상 글자를 새로운 글자로 변경 / count만큼만 시행
        - str.strip([chars]) : 구분자 제거 (+ lstirp, rstrip 등)
        - str.split(sep=None, maxsplit=-1) : 구분자 기준으로 분리
        - ‘separator’.join([iterable]) : 구분자로 iterable을 합치
        - str.capitalize() : 첫 번째 글자를 대문자로 변경 + 나머지는 소문자로
        - str.title() : 띄어쓰기 기준으로 각 단어의 첫 글자를 대문자로 변경 
        - str.upper() : 모두 대문자로 변경
        - str.lower() : 모두 소문자로 변경
        - str.swapcase() : 대소문자 변경
    - 리스트
        - 여러 개의 값을 순서가 있는 구조로 저장
        - 대괄호 []  혹은 list()를 통해 생성
        - 순서가 있는 시퀀스로 인덱스를 통해 저장 가능
        - 리스트 메서드
        - list.append(x) : 마지막에 x를 추가
        - list.insert(i, x) : 인덱스 i에 x를 삽입
        - list.remove(x) : 첫 번째 x를 제거 (항목이 없을 시 value error)
        - list.pop() : 가장 오른쪽(마지막)의 항목 반환 후 제거
        - list.pop(i) : 인덱스 i에 있는 항목을 반환 후 제거
        - list.extend(m) : m이란 리스트를 더함
        - list.index(x, start, end) : x 찾아 인덱스 반환
        - list.reverse() : 거꾸로 정렬
        - list.sort() : 리스트 정렬
        - list.count(x) : 리스트 내에 x가 몇 개 존재하는지 개수 반환
    - 튜플
        - 여러 개의 값을 순서가 있는 구조로 저장 (생성 후 변경 X)
        - 소괄호 () 형태로 사용
        - 튜플은 변경할 수 없기 때문에 값에 영향을 미치지 않는 메서드만을 지원
        - 확장 연산자 → 새로 만듦
    - 연산자
        - 멤버십 연산자 
        - in을 통해 특정 요소가 속해 있는지 확인(True, False return)
        - not in : 없나요?
        - 산술 연산자
        - ‘+’ : 시퀀스 간의 연결/연쇄
        - 반복 연산자
        - ‘*’ : 시퀀스를 반복
        
        ---
        
    
    - 셋 Set
        - 중복되는 요소 없이 순서와 상관 없는 데이터 묶음 (인덱스 접근 X)
        - 담고 있는 요소를 삽입, 변경, 삭제 가능 (mutable)
        - 셋 메서드
        - set.copy() : 셋의 얕은 복사본 반환
        - set.add(x) : x가 없다면 set에 추가
        - set.pop() : 랜덤하게 항목을 반환하고 해당 항목 제거 (비어있을 경우 KeyError)
        - set.remove(x) : x를 set에서 삭제 (존재하지 않을 경우 KeyError)
        - set.discard(x) : 에러 없이 삭제
        - set.update(t) : t에 있는 모든 항목 중 set에 없는 항목 추가
        - set.clear() : 모든 항목 제거
        - set.isdisjoint(t) : 교집합이 없을 경우 True 반환
        - set.issubset(t) : set이 t의 하위 셋일 경우 True 반환
        - set.issuperset(t) : set이 t의 상위 셋일 경우 True 반환
    - 딕셔너리
        - key-value 쌍으로 이뤄진 자료형 (3.7부터는 ordered)
        - key는 변경 불가능한 데이터(immutable)만 활용 가능
        - string, integer, float, boolean, tuple, range
        - value는 어떠한 형태든 관계 X
        - 딕셔너리 메서드
        - d.clear() : 모든 항목을 제거
        - d.copy() : 얕은 복사본을 반환
        - d.keys() : 모든 키를 담은 뷰를 반환
        - d.values() : 모든 값을 담은 뷰를 반환
        - d.items() : 모든 키-값의 쌍을 담은 뷰를 반환
        - d.get(k) : 키 k의 값을 반환 (없을 경우 None)
        - d.get(k, v) : 키 k의 값을 반환 (없을 경우 v)
        - d.pop(k) : 키 k의 값을 반환하고 항목 삭제 (없을 경우 KeyError)
        - d.pop(k, v) : 키 k의 값을 반환하고 항목 삭제 (없을 경우 v 반환)
        - d.update([other]) : d의 값을 매핑하여 업데이트
        
        ---
        
    - 복사 방법
        - 할당
        - 얕은 복사
        - 깊은 복사
    - 할당 (Assignment)
        - 대입 연산자 (=) : 해당 객체에 대한 객체 참조를 복사 
        (바로가기 복사, 같은 주소를 가리킴)
    - 얕은 복사 (Shallow copy)
        - Slice 연산자 활용하여 같은 원소를 가진 리스트지만 연산된 결과를 복사 (다른 주소값)
        - 주의사항 : 복사하는 리스트의 원소가 주소를 참조하는 경우
        2차원 리스트일 경우 안의 리스트는 주소를 복사해온 것 (안의 list는 할당)
    - 깊은 복사 (Deep copy)
        - 모든 내용이 싹 다 새로운 주소에 저장되어 복사
        - `import copy` 해서 사용
        - `dest = copy.deepcopy(str)`
        
- 객체 지향 프로그래밍 (OOP)
    - 객체 지향 프로그래밍이란?
        - 컴퓨터 프로그래밍의 패러다임(방법론) 중 하나
        - 명령어의 목록으로 보는 시각에서 벗어나 여러 개의 독립된 단위(= 객체)들의 모임으로 파악
        - 각각의 객체는 메시지를 주고 받고 데이터를 처리할 수 있음(상호작용)
        - 객체 = 정보(변수) + 행동(함수)
        - VS 절차 지향 프로그래밍
        - 중간 과정을 고치면 연달아서 바꿔야 됨
        - 데이터와 기능을 분리, 추상화된 구조(인터페이스)
    - 객체 지향의 장점/단점
        - 장점 : 
        - 클래스 단위로 모듈화 시켜 개발할 수 있으므로 많은 인원이 참여하는 대규모 소프투웨어 개발에 적합
        -  필요한 부분만 수정하기 쉽기 때문에 프로그램의 유지보수가 쉬움
        - 단점 : 
        - 설계 시 많은 노력과 시간 필요
        - 실행 속도가 상대적으로 느림
    
    ---
    
    - OOP 기초
        - 객체 : 컴퓨터 과학에서 객체 또는 오브젝트(object)는 클래스에서 정의한 것을 토대로 메모리(실제 저장공간)에 할당된 것으로 프로그램에서 사용되는 데이터 또는 식별자에 의해 참조되는 공간을 의미하며, 변수, 자료구조, 함수 또는 메서드가 될 수 있음
    - 객체 / 인스턴스 / 클래스
        - 클래스로 만든 객체 = 인스턴스 (객체 ≠ 인스턴스)
        - 이찬혁은 객체다 (O)
        - 이찬혁은 인스턴스다 (X)
        - 이찬혁은 가수(클래스)의 인스턴스다 (O)
        - 클래스 == 타입
        - 파이썬은 모든 것이 객체 : 속성과 행동이 존재
        - 객체.행동()
        - 객체는 특정 타입의 인스턴스이다.
        - 123, 500, 0은 모두 int의 인스턴스
        - ‘hello’, ‘world’는 모두 string의 인스턴스
        - [123, 4, 56], []은 모두 list의 인스턴스
        - 객체의 특징
        - 타입(type) : 어떤 연산자(operator)와 조작(method) 가능한가?
        - 속성(attribute) : 어떤 상태(data)를 가지는가?
        - 조작법(method) : 어떤 행위(function)를 할 수 있는가?
    - 기본 문법
        - 클래스 정의 `class MyClass :`
        - 인스턴스 생성 `my_instance = MyClass()`
        - 메서드 호출 `my_instance.my_method()`
        - 속성 `my_instance.my_attribute`
    - 객체 비교하기
        - == : 동등한, 변수가 참조하는 객체가 동등한 경우 True, 같아 보이지만 실제로 동일한 대상을 가리키고 있다고 확인해 준 것은 아님
        - is : 동일한, 두 변수가 동일한 객체를 가리키는 경우 True
    - 속성(데이터, 정보, 상태) → 변수
        - 특정 데이터 타입/클래스의 객체들이 가지게 될 상태/데이터를 의미
        - 클래스 변수(같은 클래스는 모두 같은 변수) / 인스턴스 변수(각각의 인스턴스마다 다른 변수)가 존재
        - 인스턴스 변수
        - 인스턴스가 개인적으로 가지고 있는 속성(attribute)
        - 각 인스턴스의 고유한 변수
        - 생성자 메서드(**init**)에서 `self.<name>` 으로 정의
        - 인스턴스가 생성된 이후 `<instance>.<name>` 으로 접근 및 할당
        - 클래스 변수
        - 클래스 선언 내부에서 정의
        - `<classname>.<name>` 으로 접근 및 할당
        - `<instance>.<클래스변수>` 로도 접근 가능 → 이 값을 바꾸면 다른 클래스들도 변한 값을 가짐
        - 클래스 변수를 변경할 때는 항상 `클래스.클래스변수` 형식으로 변형
    - 메서드
        - 특정 데이터 타입 / 클래스의 객체에 공통적으로 적용 가능한 함수
        - 인스턴스 메서드 → 인스턴스 처리
        - 인스턴스 변수를 사용하거나 인스턴스 변수에 값을 설정
        - 클래스 내부에 정의되는 메서드의 기본
        - 호출시 첫번째 인자로 인스턴스 자기자신(self)이 전달됨(자동) 
        - `self` : 인스턴스 자기 자신
        - 매개변수 이름으로 self를 첫 번째 인자로 정의
        - 파이썬의 암묵적인 규칙(다른 단어로 써도 작동은 함)
            - 생성자 메서드(Constructor) : 인스턴스 객체가 생성될 때 자동으로 호출되는 메서드  
            - 인스턴스 변수들의 초기값을 설정
            - 인스턴스 생성
            - `__init__` 메서드 자동 호출
            - 매직 메서드 (Double Underscore, 던더) : 특수한 동작을 위해 만들어진 메서드
            - 페셜 메서드 혹은 매직 메서드라고 불림
            - 특정 상황에서 자동으로 불리는 메서드
            - 소멸자 (Destructor) 메서드 : 인스턴스 객체가 소멸(파괴)되기 직전에 호출되는 메서드
        - 클래스 메서드 → 클래스 처리
        - 클래스가 사용할 메서드
        - `@classmethod` 데코레이터를 사용하여 정의
        - 호출 시 첫 번째 인자로 클래스(cls)가 전달됨
        
        ```python
        class Person :
        	count = 0 # 클래스 변수
        	def __init__(self, name) : # 인스턴스 변수 설정
        		self.name = name
        		Person.count += 1
        
        	@classmethod
        	def number_of_population(cls) :
        		print(f'(인구수는 {cls.count}입니다.')
        
        person1 = Person('김김김')
        person2 = Person('이이이')
        print(Person.count)
        ```
        
        - 클래스 메서드와 인스턴스 메서드
        - 클래스 메서드 → 클래스 변수 사용
        - 인스턴스 메서드 → 인스턴스 변수 사용
        - 클래스는 인스턴스 변수 사용 X
        - 인스턴스 메서드는 클래스 변수, 인스턴스 변수 둘 다 사용 O
        - 정적 메서드 → 나머지..
        - 스태틱 메서드는 cls, self 사용 X
        - 인스턴스와 클래스 간의 이름 공간 (namespace)
        - 클래스를 정의하면 클래스와 해당하는 이름 공간 생성
        - 인스턴스를 만들면 인스턴스 객체가 생성되고 이름 공간 생성
        - 인스턴스에서 특정 속성에 접근하면 인스턴스-클래스 순으로 탐색
        
        ```python
        class MyClass :
        	def method(self) :
        		return 'instance method', self
        
        	@classmethod
        	def classmethod(cls) :
        		return 'class method', cls
        
        	@staticmethod
        	def staticmethod() :
        		return 'static method'
        ```
        
    
    ---
    
    - 객체 지향의 핵심 개념
    - 추상화 : 현실 세계를 프로그램 설계에 반영
        - 복잡한 것은 숨기고 필요한 것만 들어내기
    - 상속 : 두 클래스 사이 부모 - 자식 관계를 정립하는 것
        - 클래스는 상속이 가능함 (부모의 object를 상속 받음)
        - `class ChildClass(ParentClass) :`
        - 하위 클래스는 상위 클래스에 정의된 속성, 행동, 관계 및 제약 조건을 모두 상속 받음
        - 부모 클래스의 속성, 메서드가 자식 클래스에 상속되므로 코드 재사용성이 높아짐
        - `isinstance(object, classinfo)` : classinfo의 instance 거나 subclass인 경우 True
        - `super()` : 자식 클래스에서 부모 클래스를 사용하고 싶은 경우
        
        ```python
        class Person :
        	def __init__(self, name, age, number, email) :
        		self.name = name
        		(...)
        		self.email = email
        
        class Student(Person) :
        	def __init__(self, name, age, number, email, student_id) :
        		super().__init__(name, age, number, email)
        		self.student_id = student_id
        ```
        
        - 메서드 오버라이딩을 통해 자식 클래스에서 재정의 가능
        - 상속관계에서의 이름 공간은 인스턴스, 자식 클래스, 부모 클래스 순으로 탐색
        - 다중 상속 : 두 개 이상의 클래스를 상속 받는 경우
        - 상속 받은 모든 클래스의 요소를 활용 가능
        - 중복된 속성이나 메서드가 있는 경우 상속 순서에 의해 결정
        
        ```python
        class Person :
        	def __init__(self, name) :
        		self.name = name
        
        	def greeting(self) :
        		return f'안녕, {self.name}'
        
        class Mom(Person) :
        	gene = 'XX'
        
        	def swin(self) :
        		return '엄마가 수영'
        
        class Dad(Person) :
        	gene = 'XY' 
        
        	def walk(self) :
        		return '아빠가 걷기'
        
        ## 다중 상속 받은 Baby
        class FirstChild(Dad, Mom) :
        	def swim(self) :
        		return '첫째가 수영'
        	
        	def cry(self) :
        		return '첫째가 응애'
        
        baby1 = FirstChild('아가')
        print(baby1.cry()) # 첫째가 응애
        print(baby1.swim()) # 첫째가 수영
        print(baby1.walk()) # 아빠가 걷기
        print(baby1.gene) # XY
        ```
        
        - mro 메서드 (Method Resolution Order) : `FirstChild.mro()`
        - 해당 인스턴스의 클래스가 어떤 부모 클래스를 가지는지 확인하는 메서드
        - 기존의 인스턴스 → 클래스 순으로 이름 공간을 탐색하는 과정에서 상속 관계에 있으면 인스턴스 → 자식 클래스 → 부모 클래스로 확장
    - 다형성 (Polymorphism)
        - 동일한 메서드가 클래스에 따라 다르게 행동할 수 있음을 의미
        - 서로 다른 클래스에 속해있는 객체들이 동일한 메시지에 대해 다른 방식으로 응답할 수 있음
        - 메서드 오버라이딩(overriding) : 상속 받은 메서드를 재정의
        - class 상속 시 부모 class에서 정의한 메서드를 자식 클래스에서 변경
        - 이름과 기본 기능은 그대로 사용하지만, 특정 기능을 바꾸고 싶을 때 사용 (자식 class에서 다시 만들면 됨)
        - 오버로딩 : 같은 이름에 다른 인자 개수(파이썬엔 없음, *args가 있어서)
    - 캡슐화
        - 객체의 일부 구현 내용에 대해 외부로부터의 직접적인 액세스를 차단
        - 파이썬에서 암묵적으로 존재하지만, 언어적으로는 존재하지 않음
        - 접근제어자 종류 (파이썬 관계 X)
        - Public Access Modifier
        - Protected Access Modifier
        - Private Access Modifier
        - Public Member
        - 언더바 없이 시작하는 메서드나 속성
        - 어디서나 호출 가능, 하위 클래스 override 허용
        - 일반적으로 작성되는 메서드와 속성 대다수를 차지
        - Protected Member
        - 언더바 1개로 시작하는 메서드나 속성
        - 암묵적 규칙에 의해 부모 클래스 내부와 자식 클래스에서만 호출 가능
        - 하위 클래스 override 허용
        - Private Member
        - 언더바 2개로 시작하는 메서드나 속성
        - 본 클래스 내부에서만 사용이 가능
        - 하위 클래스 상속 및 호출 불가능(오류)
        - 외부 호출 불가능 (오류)
        - getter 메서드와 setter 메서드 : 변수에 접근할 수 있는 메서드를 별도로 생성
        - getter 메서드 : 변수의 값을 읽는 메서드 (@property 데코레이터 사용)
        - setter 메서드 : 변수의 값을 설정하는 성격의 메서드(@변수.setter 사용)
        
        ```python
        Class Person :
        	def __init__(self, age) :
        		self._age = age
        
        	@property
        	def age(self) :
        		return self._age
        
        	@age.setter
        	def age(self, new_age) :
        		if new_age <= 19 :
        			raise ValueError('Too Young For Drink')
        			return
        
        		self._age = new_age
        
        p1 = Person(20)
        print(p1.age)
        
        p1.age = 33
        print(p1.age)
        
        p1.age = 19 # def age 안의 if문이 실행
        print(p1.age)
        ```
        
    - 디버깅
        - 버그 : 소프트웨어에서 발생하는 문제
        - 1945년 프로그래밍 언어의 일종인 코볼 발명자 그레이스 호퍼가 발견
        - 컴퓨터 회로에 나방이 들어가 합선을 일으켜 비정상적으로 동작
        - 디버깅의 정의 : 잘못된 프로그램을 수정하는 것
        - 에러 메세지가 발생 : 해당 위치를 찾아 메세지 해결
        - 로직 에러가 발생하는 경우 : 화이팅!
    - 에러와 예외
        - 문법 에러(Syntax Error) : 프로그램 실행 X
        - 파일이름, 줄번호, ^ 문자를 통해 파이썬이 코드를 읽어 나갈 때 문제가 발생한 위치를 표현
        - EOL (End of Line)
        - EOF (End of File)
        - 예외 (Exception) : 실행 도중 예상치 못한 상황을 맞이하면 프로그램 실행 멈춤
        - 여러 타입으로 나타나고, 타입이 메세지의 일부로 출력됨
        - NameError, TypeError 등
        - 모든 내장 예외는 Exception Class를 상속받아 이뤄짐
        - 사용자 정의 예외를 만들어 관리할 수 있음
        - 각종 Errors
        - ZeroDivisonError
        - NameError (Not defined)
        - TypeError : 타입 불일치 / Argument 누락 / Argument Type 불일치
        - ValueError : 타입은 올바르나 값이 적절하지 X
        - IndexError : 인덱스 존재 X / 범위를 벗어남
        - KeyError : 해당 키 존재 X
        - ModuleNotFoundError 
        - ImportError : Module은 있으나 존재하지 않는 클래스 / 함수를 가져오는 경우
        - KeboardInterrupt - 임의로 프로그램 종료시
        - IndentationError : 들여쓰기 적절
    - 예외 처리
        
        try 문(statement) / except 절(clause)을 이용하여 예외 처리 가능
        
        - try 문 
        - 오류가 발생할 가능성이 있는 코드를 실행
        - 예외가 발생되지 않으면 except 없이 실행 종료
        - except 문
        - 예외가 발생하면 except 절이 실행
        - 예외 상황을 처리하는 코드를 받아서 적절한 조치
        
        ```python
        try :
        	num = input('숫자 입력 :')
        	print(int(num))
        except ValueError :
        	print('숫자가 입력되지 않았습니다.')
        ```
        
        - as 키워드를 활용하여 원본 에러 메세지를 사용 가능
        
        ```python
        except IndexError as err :
        	print(err)
        ```
