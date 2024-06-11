---
layout: page
current: about
title: MarkDown 사용법
navigation: true
logo: 'assets/images/ghost.png'
class: page-template
subclass: 'post page'
---

# 게시물 등록 방법
1. _post 폴더에 작성하기 원하는 태그 폴더에 파일을 만든다.<br>
    ex) _post > it2024
2. 파일명은 다음 규칙에 따른다.<br>
    년도-월-일-태그명-타이틀명.md<br>
    ex) 2024-05-24-it2024-title.md
3. md 파일 상단에는 다음 내용을 필수 작성 후 MarkDown 작성법에 따라 게시글을 작성한다.<br>
`---`<br>
`layout: post`<br> 
`current: post`<br>
`cover:  assets/images/welcome.jpg`<br>
`navigation: True`<br>
`title: 게시글 제목`<br>
`date: 2024-05-31 09:00:00 +0900`<br>
`tags: [it2024]`<br>
`class: post-template`<br>
`subclass: 'post'`<br>
`author: hby`<br>
`---`
<br>
- layout, current, cover, navigation, class, subclass 변경 X
- title : 게시글 제목
- date : 게시글 작성 날짜
- tags : 원하는 태그
- author : 작성자(자신의 이니셜)
<br><br><br>


# MarkDown 작성법
1. 제목 (Headings)<br>
제목은 #을 사용하여 작성합니다. #의 개수에 따라 제목의 수준이 달라집니다.<br>
`# 제목 1`<br>
`## 제목 2`<br>
`### 제목 3`<br>
`#### 제목 4`<br>
`##### 제목 5`<br>
`##### 제목 6`<br>

***

2. 강조 (Emphasis)<br>
텍스트를 굵게 또는 기울임으로 강조할 수 있습니다.<br>
`**굵은 글씨** 또는 __굵은 글씨__`<br>
`*기울임 글씨* 또는 _기울임 글씨_`<br>
`***굵고 기울임 글씨*** 또는 ___고 기울임 글씨___`<br>

***

3. 리스트 (Lists)<br>
순서 있는 리스트와 순서 없는 리스트를 작성할 수 있습니다.<br>
`1. 첫 번째 아이템`<br>
`2. 두 번째 아이템`<br>
`3. 세 번째 아이템`<br>

`- 첫 번째 아이템`<br>
`- 두 번째 아이템`<br>
`- 세 번째 아이템`<br>
 
`* 첫 번째 아이템`<br>
`* 두 번째 아이템`<br>
`* 세 번째 아이템`<br>

***

4. 링크 (Links)<br>
링크를 삽입할 때는 대괄호와 괄호를 사용합니다.<br>
`[링크 텍스트](https://www.example.com)`<br>

***

5. 이미지 (Images)<br>
이미지를 삽입할 때는 링크와 비슷하지만, 앞에 !를 붙입니다.<br>
`![대체 텍스트](https://www.example.com/image.jpg)`<br>

***

6. 코드 (Code)<br>
한 줄의 코드는 백틱(\`)으로 감쌉니다. 여러 줄의 코드는 세 개의 백틱(\`\`\`)으로 감쌉니다.<br>
\`한 줄 코드\`
 
여러 줄의 코드<br>
\`\`\`markdown<br>

***

7. 블록 인용 (Blockquotes)<br>
블록 인용은 >를 사용합니다.<br>
`> 이것은 인용입니다.`<br>
`> `<br>
`>  여러 줄의 인용입니다.`<br>

***

8. 수평선 (Horizontal Rules)<br>
수평선은 ---, ***, ___ 등을 사용합니다.<br>
`---`<br>
`***`<br>
`___`<br>

***

9. 표 (Tables)<br>
표는 |와 -를 사용합니다.<br>
`| 헤더 1 | 헤더 2 |`<br>
`| ------ | ------ |`<br>
`| 셀 1   | 셀 2   |`<br>
`| 셀 3   | 셀 4   |`<br>

***

10. 체크리스트 (Task Lists)<br>
체크리스트는 - [ ] (미완료)와 - [x] (완료)를 사용합니다.<br>
`- [ ] 할 일 1`<br>
`- [x] 할 일 2`<br>
`- [ ] 할 일 3`<br>