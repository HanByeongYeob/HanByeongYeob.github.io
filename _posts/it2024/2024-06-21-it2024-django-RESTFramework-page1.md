---
layout: post
current: post
cover:  assets/images/welcome.jpg
navigation: True
title: django -REST Framework(1) - Dhango 설치 및 DRF 라이브러리 설치
date: 2024-06-21 09:00:00 +0900
tags: [IT2024]
class: post-template
subclass: 'post'
author: hby
---

<span class="table-of-contents-list">Django REST Framework 강좌는 django 글에서 이어서 작성합니다.</span>
<ul class="table-of-contents-list">
    <li><a href="./it2024-django-RESTFramework-page1">django -REST Framework(1) - Dhango 설치 및 DRF 라이브러리 설치</a></li>
    <li><a href="./it2024-django-page2">django(2) - django 앱 생성</a></li>
    <li><a href="./it2024-django-page3">django(3) - django css 꾸미기</a></li>
    <li><a href="./it2024-django-page4">django(4) - POST, GET 통신 / DB 연결 및 데이터 저장</a></li>
</ul>


# Django 세팅 
<a href="./it2024-django-page1">django(1) - django 세팅</a>

# REST Framework 및 markdown 설치
1. REST Framework 및 markdown 설치

```
pip install djangorestframework==3.14.0
pip install markdown
```


2. settings.py의 INSTALLED_APPS에 rest_framework 추가

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'rest_framework',
]
```

3. urls.py에 urlpatterns 추가

```python
urlpatterns = [
    path('admin/', admin.site.urls),
    path('api-auth', include('rest_framework.urls')),
]
```

※ 참고<br>
[(YouTube) 작정하고 장고! Django REST Framework 6강 - Django 프로젝트 시작](https://youtu.be/G-nWsddnoDI?si=60Wu7WEzznqF1VN-)<br>
[(YouTube) 작정하고 장고! Django REST Framework 7강 - DRF 라이브러리 설치](https://youtu.be/JY68wovx9Zw?si=lXAiWhFbfasNsFA5)<br>