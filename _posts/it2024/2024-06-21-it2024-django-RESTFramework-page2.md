---
layout: post
current: post
cover:  assets/images/welcome.jpg
navigation: True
title: django -REST Framework(2) - django 앱 생성
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


# 앱생성
1. 앱 생성 명령어 실행
```
python manage.py startapp [앱명칭]
```

2. [프로젝트명] > settings.py를 열어서 INSTALLED_APPS 배열에 생성한 [앱명칭] 작성
```python
	INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
	'[앱명칭]'
]
```
# 모델 생성
1. [앱명칭] > models.py에 작성
```python
from django.db import models

# Create your models here.
class Student(models.Model) :
    student_id = models.CharField(max_length=15, unique=True)
    name = models.CharField(max_length=30)
    age = models.IntegerField()
```

# serializers 생성
1. [앱명칭] > serializers.py 파일 생성 후 작성

```python
from rest_framework import serializers
from student.models import Student


class StudentSerializer(serializers.ModelSerializer) :
    student_id = serializers.CharField(required=False)
    name = serializers.CharField(required=False)
    age = serializers.CharField(required=False)

    class Meta :
        model = Student
        fields = '__all__'

```

# views 생성
1. [앱 명칭] > views.py를 열어서 코드 작성

```python
from rest_framework.response import Response
from rest_framework.views import APIView
from rest_framework import status
from .serializers import *

class StudentList(APIView) :
    def get(self, request):
        model = Student.objects.all()
        serializer = StudentSerializer(model, many=True)
        return Response(serializer.data)

    def post(self, request):
        serializer = StudentSerializer(data=request.data)
        if(serializer.is_valid()) :
            serializer.save()
            return Response(serializer.data, status=status.HTTP_201_CREATED)
        return Response(serializer.errors, status=status.HTTP_400_BAD_REQUEST)

class StudentDetail(APIView) :
    def get(self, request, student_id):
        model = Student.objects.get(student_id=student_id)
        serializer = StudentSerializer(model)
        return Response(serializer.data)

    def put(self, request, student_id):
        model = Student.objects.get(student_id=student_id)

        serializer = StudentSerializer(model, data=request.data)
        if serializer.is_valid() :
            serializer.save()
            return Response(serializer.data, status=status.HTTP_201_CREATED)
        return Response(serializer.data, status=status.HTTP_400_BAD_REQUEST)

    def delete(self, request, student_id):

        model = Student.objects.get(student_id=student_id)
        model.delete()
        return Response(status=status.HTTP_204_NO_CONTENT)
```

# 라우팅 설정
1. [프로젝트명] > urls.py의 urlpatterns 배열에 해당 코드 추가

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('student/', include('student.urls')),
]
```

2. [앱 명칭] 폴더에 urls.py 파일을 생성하고 해당 코드 작성

```python
from django.urls import path
from accountapp.views import hello_world, hello_world_drf
from student.api import StudentList, StudentDetail

app_name = "student"

urlpatterns = [
    path('list/', StudentList.as_view(), name='list'),
    path('list/<int:student_id>', StudentDetail.as_view(), name='detail'),
]
```

※ 참고<br>
[(YouTube) 작정하고 장고! Django REST Framework 9강 - Django 개발 패턴](https://youtu.be/O7u4W-hpeXQ?si=0EV_JM_Ljc5nQsNd)<br>
[(YouTube) 작정하고 장고! Django REST Framework 10강 - 첫번째 View 작성](https://youtu.be/TLFZCZVuzjQ?si=D4xTdTrzt0kpVjmd)<br>
[(YoTube) [Django Rest API - 3] Django Rest API 만들기](https://youtu.be/UPzCd4H2K0k?si=wBSDkSzQh0eDVTKz)<br>
[(YoTube) [Django Rest API - 4] Django Rest API 생성(Post)](https://youtu.be/UlXRaDOqRaw?si=sYOvc-LEq4Ky7sVJ)<br>
[(YoTube) [Django Rest API - 5(1)] Django Rest API 업데이트 (Put)](https://youtu.be/q5iHXuoDFHA?si=10YsN26PpcvnNp01)<br>
[(YoTube) [Django Rest API - 5(2)] Django Rest API Put(Update)](https://youtu.be/HEAqyYEi6iE?si=aZpQJHnU87chfJDF)<br>
[(YoTube) [Django Rest API - 6] Django Rest API Delete(삭제)](https://youtu.be/Ft6QAhKQ8UQ?si=WuM6I0np5Go3YjHo)<br>
