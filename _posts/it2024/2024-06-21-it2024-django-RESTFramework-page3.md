---
layout: post
current: post
cover:  assets/images/welcome.jpg
navigation: True
title: django -REST Framework(3) - token 생성
date: 2024-06-21 09:00:00 +0900
tags: [IT2024]
class: post-template
subclass: 'post'
author: hby
---

<span class="table-of-contents-list">Django REST Framework 강좌는 django 글에서 이어서 작성합니다.</span>
<ul class="table-of-contents-list">
    <li><a href="./it2024-django-RESTFramework-page1">django -REST Framework(1) - Dhango 설치 및 DRF 라이브러리 설치</a></li>및 데이터 저장</a></li>
</ul>


# 토큰 생성을 위한 세팅
1. settings.py의 INSTALLED_APPS에 ***rest_framework.authtoken*** 작성

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'rest_framework',
    'rest_framework.authtoken',
    'accountapp',
    'student',
]
```

2. REST_FRAMEWORK 변수 추가

```python
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES' : [
        'rest_framework.authentication.TokenAuthentication'
    ],
    'DEFAULT_PERMISSION_CLASSES' : [
        'rest_framework.permissions.IsAuthenticated'
    ]
}
``` 

3.[프로젝트명] > urls.py에 auth view 추가

```python
from django.contrib import admin
from django.urls import path, include
from rest_framework.authtoken import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('api-auth/', include('rest_framework.urls')),
    path('student/', include('student.urls')),
    path('auth', views.obtain_auth_token, name='user_auth-create')
]
```

# 토큰이 잘되는지 test 코드

```python
#토큰을 이용한 접근 test
import requests

url = 'http://127.0.0.1:8000/auth'

token_resonse = requests.post(url, data={'username':'admin', 'password':'admin'})

myToken = token_resonse.json()
token = myToken['token']
header = {'Authorization' : 'Token '+token}

resonse = requests.get('http://127.0.0.1:8000/student/list/', headers=header)
print(resonse.text)


```
※ 참고<br>
[(YoTube) [Django Rest API - 7] Django Rest API Token AUTH 토큰인증](https://youtu.be/CWquxPk1S_k?si=jHEbhNB7Z0AENKmB)<br>
[(YoTube) [Django Rest API - 8] Django rest API Token 토큰 만들기](https://youtu.be/MMWQw8PXMgg?si=Kgz9E25cjBWnlx_k)<br>