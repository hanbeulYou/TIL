# Django

## Design Pattern

### MVC 소프트웨어 디자인 패턴

- Model - View - Controller
- 데이터 및 논리 제어를 구현하는데 널리 사용되는 소프트웨어 디자인 패턴
    - Model : 데이터와 관련된 로직 처리
    - View : 레이아웃과 화면 처리
    - Controller : 명령을 model과 view 부분으로 연결
- 목적 : 업무의 분리와 향상된 관리 제공
    - 각 부분을 독립적으로 개발 가능
    - 효율성 및 유지 보수의 편리성
    - 다수의 멤버로 개발하기 용이

### MTV 패턴

- MVC 패턴을 기반으로 함
- Model - Template - View
    - Model : MVC 패턴에서 Model의 역할
    - Template : 레이아웃과 화면 처리, 사용자 인터페이스 구조와 레이아웃 정의. MVC 패턴에서 View의 역할
    - View : Model & Template과 관련한 로직을 처리해서 응답 반환. 클라의 요청에 대해 처리를 분기. MVC 패턴에서 Contrioller의 역할에 해당
        - 동작 예시 : 데이터가 필요하다면 mode에 접근 → 데이터를 가져와 → template로 보내 화면 구성 → 응답으로 만들어 클라에게 반환

## 프로젝트 실행

### python 가상환경 설정

```bash
$ python -m venv venv
$ source venv/Scripts/activate
$ pip install django==3.2.13
# 확장팩?
$ pip install django-extensions

$ pip freeze > requirements.txt
# 여기까지 가상환경 생성 및 장고 설치 방법
$ deactivate
# 가상환경 종료

# venv 삭제 후에도 이거만 있으면 됨
$ pip install -r requirements.txt

# 프로젝트 생성
$ django-admin startproject firstpjt .

# 서버 실행(manage.py 파일이 있는 위치)
$ python manage.py runserver

# 이건 뭐지
$ python manage.py createsuperuser

# 앱 만들기
$ python manage.py startapp articles
```

### PJT 틀 만들어 보기

pjt/settings.py에서

```python
INSTALLED_APPS = [
    'articles',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
```

pjt/urls.py에서 include 해주기

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('articles/', include('articles.urls')),
]
```

articles/urls.py 만들고

```python
from django.urls import path
from . import views

app_name = 'articles'
urlpatterns = [
    path('', views.index, name='index'),
]
```

articles/views.py 에서

```python
from django.shortcuts import render

# Create your views here.
def index(request):
    pass
    return render(request, 'articles/index.html')
```

articles/templates/articles에 index.html 만들기

Variable : [views.py](http://views.py) 에서 뭔가 작업해서 보낼거임

```python
from django.shortcuts import render

# Create your views here.
def home(request):
    movie = ['reflection on you', 'harry potter', 'spider man',]

    context = {
        'movie':movie,
    }
    return render(request, "movies/home.html", context)
```

home.html 파일에서

```html
<h1>Welcome Home!</h1>

{{ movie }}
```

for문을 사용해보자(for문 : for + tab, 주석 : comment + tab)

```html
<h1>Welcome Home!</h1>

{{ movie }}

{% comment "for문 사용해보기" %}{% endcomment %}
{% for m in movie %}
  <h3>{{ m }}</h3>
{% endfor %}
```

틀 만들기(base.html)

최상위 dir에 templates/base.html 만들어주기

이후 [settings.py](http://settings.py)에서

```python
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [BASE_DIR / 'templates',],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
```

이후 각 html 파일에서 상속 넣어주기

```html
{% extends 'base.html' %}

{% block content %}
<h1>Welcome Home!</h1>
{{ movie }}

{% comment "for문 사용해보기" %}{% endcomment %}
{% for m in movie %}
  <h3>{{ m }}</h3>
{% endfor %}
{% endblock content %}
```

다시 base.html에서

```html
<div class="container">
    <div class="row">
      {% block content %}
      {% endblock content %}
    </div>
  </div>
```

데이터 보내고 가져오기

articles/urls.py

```python
from django.urls import path
from . import views

app_name = 'articles'
urlpatterns = [
    path('', views.index, name='index'),
    path('throw/', views.throw, name='throw'),
]
```

articles/view.py

```python
from django.shortcuts import render

# Create your views here.
def index(request):
    pass
    return render(request, 'articles/index.html')

def throw(request):
    pass
    return render(request, 'articles/throw.html')
```

articles/templates/articles/throw.html

```python
{% extends 'base.html' %}

{% block content %}
  <h1>Throw</h1>
  <!--GET은 정보 요청해서 가져올때만 사용 <-> POST(인증 등)-->
  <form action="/articles/catch/" method="GET">
    <!--for이랑 id랑 짝꿍-->
    <label for="throw message">message : </label>
    <!--name이라는 곳(key)에 값(value)이 들어갈거임-->
    <input type="text" id="throw message" name="message" placeholder="message">
    <!--받은 값 보내기-->
    <input type="submit">
  </form>
{% endblock content %}
```

catch도 throw처럼 만들어주기

```html
{% extends 'base.html' %}

{% block content %}
  <h1>catch<h1>
  <h2>여기서 데이터를 받았습니다.</h2>
  {{ my_message }}
  <a href="../throw/">go back to throw</a>
{% endblock content %}
```

[view.py](http://view.py) 바꿔주기

```python
from django.shortcuts import render

# Create your views here.
def index(request):
    pass
    return render(request, 'articles/index.html')

def throw(request):
    pass
    return render(request, 'articles/throw.html')

def catch(request):
    # throw에서 받아올 메시지
    my_message = request.GET.get('message')
    context = {
        'my_message':my_message,
    }
    return render(request, 'articles/catch.html', context)
```

variable routing

2가지 지원 : string(default, <str:str1>), int(<int:num1>)

articles/urls.py

```python
from django.urls import path
from . import views

app_name = 'articles'
urlpatterns = [
    path('', views.index, name='index'),
    path('throw/', views.throw, name='throw'),
    path('catch/', views.catch, name='catch'),
    path('catchword/<name>/', views.catchword, name="catchword"),
]
```

articles/views.py

```python
from django.shortcuts import render

# Create your views here.
def index(request):
    pass
    return render(request, 'articles/index.html')

def throw(request):
    pass
    return render(request, 'articles/throw.html')

def catch(request):
    # throw에서 받아올 메시지
    my_message = request.GET.get('message')
    context = {
        'my_message':my_message,
    }
    return render(request, 'articles/catch.html', context)

def catchword(request, name):
    context = {
        'name':name,
    }
    return render(request, 'articles/catchword.html', context)
```

templates/articles/catchword.html

```html
{% extends 'base.html' %}

{% block content %}
<h1>받았다!</h1>
  <a>{{ name }}</a>
{% endblock content %}
```

html에 url로 하이퍼링크 넣어주기

```python
{% extends 'base.html' %}

{% block content %}
  <h1>만나서 반갑습니다!!</h1>
  <a href="{% url 'greeting' %}">greeting</a>
  <a href="{% url 'dinner' %}">dinner</a>
  <a href="{% url 'throw' %}">throw</a>
  <a href="{% url 'index' %}">두번째 앱</a>
{% endblock content %}
```

서로 다른 app에서 같은 이름을 호출했을 때 : app_name을 붙여줌

- app_name 하나라도 붙여줬으면 싹 다 붙여줘야함 → 안그러면 error
- no reversmatch → url 태그만 확인

```python
{% extends 'base.html' %}

{% block content %}
  <h1>만나서 반갑습니다!!</h1>
  <a href="{% url 'articles:greeting' %}">greeting</a>
  <a href="{% url 'articles:dinner' %}">dinner</a>
  <a href="{% url 'articles:throw' %}">throw</a>
  <a href="{% url 'pages:index' %}">두번째 앱</a>
{% endblock content %}
```

앱의 등록 순서(settings.py)에 따라 html을 찾음 → 같은 index.html을 가져오게 됨 → app이름을 넣은 폴더를 templates 디렉토리 안에 만들어주자

## Database

### Database 기초

- 스키마(Schema)
    - 뼈대
    - 자료의 구조, 표현 방법, 관계 등을 정의한 구조
- 테이블(Table)
    - 필드와 레코드를 사용해 조직된 데이터 요소들의 집합
    - 관계(Relation)라고도 함
    - 필드 : 속성, 컬럼(Col)
    - 레코드 : 튜플, 행(Row)
- 필드(Field)
    - 속성 혹은 컬럼
    - 각 필드에는 고유한 데이터 형식이 지정됨(INT, TEXT 등)
- 레코드(Record)
    - 튜플 혹은 행
    - 테이블의 데이터는 레코드에 저장됨
- Primary Key(PK)
    - 기본 키
    - 각 레코드의 고유한 값(식별자)
    - 다른 항목과 절대 중복 X → 단일값(Unique)
    - DB 관리 및 테이블 간 관계 설정 시 주요하게 활용됨
    - 예) 주민등록번호 등
- 쿼리(Query)
    - 데이터를 조회하기 위한 명령어
    - 조건에 맞는 데이터를 추출하거나 조작
    - ‘Query를 날린다’ == ‘DB를 조작한다’
    

## Model

### 개요

- Django는 Model을 통해 데이터에 접근 및 조작
- 사용하는 데이터들의 필수적인 필드들과 동작들을 포함
- 저장된 DB의 구조(layout)
- 일반적으로 각각의 모델은 하나의 DB table에 매핑
    - 매핑 : 하나의 값을 다른 값으로 대응 시키는 것

### Model 작성

articles/model.py

```python
from django.db import models

# Create your models here.
# models.Model로 상속 받아오기
class Article(models.Model):
    # 필드 이름 = 타입 -> 스키마
    # Char : 길이 제한(max 255)
    # Text : 길이가 길어짐(SQLite 2^31)
    title = models.CharField(max_length=10)
    content = models.TextField()
    # id col은 table 생성시 앙꼬가 자동으로 생성해줌
```

### Migrations

Django가 모델에 생긴 변화(필드 추가, 수정 등)를 실제 DB에 반영

```bash
$ python manage.py makemigrations
```

명령어 실행 → migrations/0001_initial.py 파일 생성

- 장고가 만들어 놓은 최종 설계도 혹은 청사진(Blueprint)
- 아직 DB 테이블 생성 X
- migrations 파일 특) nnnn_name.py 꼴

migrate : makemigrations로 만든 설계도를 실제 DB에 반영(db.sqlite3 파일에 반영)

```bash
$ python manage.py migrate
```

- 이상한 애들이 잔뜩 나오는 이유 == 세팅에 기존에 있던 앱들
- 확인 방법 : SQLite 설치 → db.sqlite3 → 오른쪽 마우스 클릭 → Open DB → 왼쪽 아래에 SQLITE EXPLORE 확인 → articles_article에서 스키마 정보 확인 가능

Model 변경사항 반영

```python
from django.db import models

# Create your models here.
class Article(models.Model):
    # 필드 이름 = 타입 -> 스키마
    # Char : 길이 제한
    # Text : 길이가 길어짐
    title = models.CharField(max_length=10)
    content = models.TextField()
    # id col은 table 생성시 앙꼬가 자동으로 생성해줌
    
    # 작성 시간을 추가해주고 싶을 때
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)
    # 변경 사항을 토대로 다시 migration 해줘야함
```

![Untitled](Django%2045e54da733de45d184928f27dda833ba/Untitled.png)

- auto_now_add : 최초 생성일자
- auto_now : 최종 수정 일자
- 그대로 실행하면 기존에 만들어진 애들에 대한 새로운 빈 값 X -> 디폴트값 뭐로 넣을래
1) 여기서 키보드 입력
2) 코드에서 넣고 올래?
- 0002번이 만들어졌다. 뭐가 다를까?

```python
class Migration(migrations.Migration):

    dependencies = [
        ('articles', '0001_initial'),
    ]

    operations = [
        migrations.AddField(
            model_name='article',
            name='created_at',
            field=models.DateTimeField(auto_now_add=True, default=django.utils.timezone.now),
            preserve_default=False,
        ),
        migrations.AddField(
            model_name='article',
            name='updated_at',
            field=models.DateTimeField(auto_now=True),
        ),
    ]
```

dependencies : 1번에 대한 의존성

### ORM(Object-Relational-Mapping)

python ↔ migrate ↔ SQL 번역은 누가? ORM

Django 내장 ORM을 사용

SQL을 사용하지 않고 DB 접근 가능

ORM을 사용하는 이유 : 생산성

django_extensions와 ipython 설치

```bash
$ pip install ipython django-extensions
```

- ipython : 더 강력한 파이썬 쉘
- django-extensions : 장고 확장 프로그램 모음(shell plus 등)
    - setting.py에 추가해줘야함
    
    ```python
    INSTALLED_APPS = [
        'articles',
        'django_extensions',
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
    ]
    ```
    

django shell 실행

```bash
$ python manage.py shell_plus
```

`Article.objects.all()` : 작성된 내용 모두 출력(QuerySet 이라는 객체로 출력)

→ ModelClass.Manager.QuerysetAPI

### QuerySet API

Queryset 

- DB에게서 전달받은 객체 목록
- 순회 가능한 데이터 → 1개 이상의 데이터 불러와 활용 가능
- Django ORM을 통해 만들어진 자료형
- 필터, 정렬 등 가능
- 단일 객체일 경우 Queyset이 아닌 모델의 인스턴스로 반환됨

Queryset 익히기

CRUD : Create(생성) / Read(조회) / Update(수정) / Delete(삭제)

Create

```bash
# 방법1
$ article = Article()
$ article.title = 'first'
$ article.content = 'django!'
$ article.save()

# 방법2
$ article = Article(title='second', content='django!!')
$ article.save()

# 방법3
$ Article.objects.create(title='third', content='django!!!')

# 확인
$ article
$ Article.objects.all()

# article.id와 같음. django의 권장은 pk.
$ article.pk
```

Read

all() : 전부

```bash
$ articles = Article.objects.all()

$ for article in articles:
    ...:     print(article)
```

get() : 객체 X or 2개 이상 → error, 즉 pk등에 대해 사용

```bash
$ Article.objects.get(pk=1)
```

filter() : 조회 매개 변수와 일치하는 객체를 포함하는 새 QuerySet 반환 (있든 없든)

```bash
$ Article.objects.filter(title='first')
# <QuerySet [<Article: Article object (1)>]>

$ Article.objects.filter(title='firstt')
# <QuerySet []>
```

field lookups(공식문서 참고) : 특정 레코드에 대한 조건 설정

```bash
Article.objects.filter(content__contains='dj')
```

Update

수정을 하기 위해서는 먼저 조회(Read)를 해야함

```bash
$ article = Article.objects.get(pk=1)
$ article.title = 'byebye'
$ article.save()
```

Delete

조회 → 삭제 메서드 활용

```bash
article = Article.objects.get(pk=1)
article.delete()
```

보기 좋게 만들려면 models.py에 str 메서드 추가

```python
def __str__(self):
        return self.title
```

- 이런 애들은 다시 마이그레이션 안해줘도 됨(table을 만지는거 아님)

실전! Data 받아오기

urls 수정

```python
from django.urls import path
from . import views

app_name = 'articles'
urlpatterns = [
    path('', views.index, name='index'),
    path('new/', views.new, name='new'),
    path('create/', views.create, name='create'),
]
```

view 추가

```python
def create(request):
    # 사용자 DATA 받아서 DB에 저장
    title = request.GET.get('title')
    content = request.GET.get('content')
    
    # DB에 저장
    """
    # 1
    article = Article()
    article.title = title
    article.content = content
    article.save()
    """
    
    # 2 (추천)
    article = Article(title=title, content=content)
    article.save()

    """
    # 3
    Article.objects.creat(title=title, content=content)    
    """
    return render(request, 'articles/create.html')
```

데이터를 입력할 new.html 만들기

```html
{% extends 'base.html' %}

{% block content %}
  <h1>NEW</h1>
  <form action="{% url 'articles:create' %}" method="GET">
    <label for="title">Title : </label>
    <input type="text" name="title" id="title"><br><br>
    <label for="content">Content : </label>
    <input type="text" name="content" id="content"><br><br>
    <input type="submit">
  </form>
  <a href="{% url 'articles:index' %}">뒤로가기</a>
{% endblock content %}
```

데이터 받았다는 page create.html 만들기

```html
{% extends 'base.html' %}

{% block content %}
  <h1>Create</h1>
  <p>게시글이 작성되었습니다</p>
  <a href="{% url 'articles:index' %}">뒤로가기</a>
{% endblock content %}
```

- 고쳐야할 사항
    - Create를 랜더링 X
    - GET 메서드 X