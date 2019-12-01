---
layout: post
title: "Connect React to Django"
date: 2019-11-19
description:
image: /assets/images/django-logo.png
author: Jeong geonwoo
tags:
  - django
  - react
---

### React Proxy Setting

django 에서 만든 api 를 react 에서 호출하기 위해서는 react 에서 proxy 설정을 해주어야 한다. django 는 :8000 번에 위치하고 react 는 :3000 번에 위치하기 때문이다.
예로

```
localhost:3000/users/chagepassword
```

라는 url 이 있으면 react 는 :3000번 이기 때문에 해당 url 을 찾지 못한다. 하지만 이때 proxy 를 :8000 으로 설정을 해두면 우선적으로 localhost:3000/users/chagepassword 을 찾고 존재하지 않으면 localhost:8000/users/chagepassword 에서 찾는다.

package.json

```javascript
{
  ...,
  "proxy": "http://localhost:8000",
  ...
}
```

위와 같이 설정

### Connecting django to React

#### 1. proxy the request from 3000 to 8000

&nbsp; - proxy 를 :3000 에서 :8000으로 보냄 (react)

#### 2. install django-cors-headers

&nbsp; - 보안상의 문제 없이 Ajax등의 통신을 하기 위해 사용되는 메커니즘이 CORS임

&nbsp; - Django 는 기본적으로 외부에서의 요청을 막음

&nbsp; - CORS 표준은 웹 브라우저가 사용하는 정보를 읽을 수 있도록 허가된 출처 집합를 서버에게 알려주도록 허용하는 HTTP 헤더를 추가함으로써 동작

```
pip install django-cors-headers
```

&nbsp; [참조](http://recordingbetter.com/2017/08/07/Django-CORS)

#### 3. Add 'corsheaders' to INSTALL_APPS

&nbsp; [참조](https://pypi.org/project/django-cors-headers/)

```python
INSTALLED_APPS = [
    ...,
    INSTALLED_APPS,
    ...
]
```

#### 4. Add 'corsheaders.middleware.CoreMiddleware' before 'CommonnMiddleware'

```python
MIDDLEWARE = [
    ...,
    "corsheaders.middleware.CorsMiddleware",
    "django.middleware.common.CommonMiddleware",
    ...
]
```

#### 5. Add CORS_ORIGIN_ALLOW_ALL = True on base settings

`base.py or settings.py`

```python
...
CORS_ORIGIN_ALLOW_ALL을 = True
```

#### 6. Make Djagno load the bunndles as static files with 'str(ROOT_DIR.path('fronted','build','static'))'

django 가 번들을 static file (js, css...) 을 로딩하게 해야한다.

`base.py or settings.py`

```python
STATICFILES_DIRS = [
    str(APPS_DIR.path("static")),
    str("/Users/user/Documents/git_repo/cafeteria_front/build/static"),
]
```

#### 7. Create a views.py file on [root] folder

`views.py`

#### 8. Create ReactAppView that read the file.

`views.py`

```python
import os
from django.views.generic import View
from django.http import HttpResponse
from django.conf import settings


class ReactAppView(View):

    def get(self, request):
        try:
            with open(os.path.join("[path to react root folder]", "build", "index.html")) as file:
                return HttpResponse(file.read())
        except:
            return HttpResponse(
                """
                index.html not found!! build your react app
                """,
                status=501
            )

```

#### 9. Add the ReactAppView as a URL

```python
urlpatterns = [
    ...,
    ...,
    path("", views.ReactAppView.as_view()),
]
```
