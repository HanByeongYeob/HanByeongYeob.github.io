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
```
---
layout: post
current: post
cover:  assets/images/welcome.jpg
navigation: True
title: 게시글 제목
date: 2024-05-31 09:00:00 +0900
tags: [it2024]
class: post-template
subclass: 'post'
author: hby
---
```
<br>
- layout, current, cover, navigation, class, subclass 변경 X<br>
- title : 게시글 제목<br>
- date : 게시글 작성 날짜<br>
- tags : 원하는 태그<br>
- author : 작성자(자신의 이니셜)<br>
<br><br><br>


# MarkDown 작성법
1. 제목 (Headings)<br>
제목은 #을 사용하여 작성합니다. #의 개수에 따라 제목의 수준이 달라집니다.
```
# 제목 1
## 제목 2
### 제목 3
#### 제목 4
##### 제목 5
##### 제목 6
```

# 
2. 강조 (Emphasis)<br>
텍스트를 굵게 또는 기울임으로 강조할 수 있습니다.
```
**굵은 글씨** 또는 __굵은 글씨__
*기울임 글씨* 또는 _기울임 글씨_
***굵고 기울임 글씨*** 또는 ___고 기울임 글씨___
```

# 
3. 리스트 (Lists)<br>
순서 있는 리스트와 순서 없는 리스트를 작성할 수 있습니다.
```
1. 첫 번째 아이템
2. 두 번째 아이템
3. 세 번째 아이템

- 첫 번째 아이템
- 두 번째 아이템
- 세 번째 아이템
 
* 첫 번째 아이템
* 두 번째 아이템
* 세 번째 아이템
```

# 
4. 링크 (Links)<br>
링크를 삽입할 때는 대괄호와 괄호를 사용합니다.
```
[링크 텍스트](https://www.example.com)
```

#
5. 이미지 (Images)<br>
이미지를 삽입할 때는 링크와 비슷하지만, 앞에 !를 붙입니다.
```
![대체 텍스트](https://www.example.com/image.jpg)
```

# 
6. 코드 (Code)<br>
한 줄의 코드는 백틱(\)으로 감쌉니다. 여러 줄의 코드는 세 개의 백틱(\\\)으로 감쌉니다.
```
`한 줄 코드`
\한 줄 코드\
 ```여러줄 코드```
```
* rouge를 이용한 코드 작성
```
    ```javascript
    function syntaxHighling(code){
        var foo = 'Hello World';
        var bar = 100;
    }
    ```
```
<br>
```
지원가능 언어
abap
actionscript, as, as3
apache
apiblueprint, apiblueprint, apib
applescript, applescript
awk
biml
brainfuck
bsl
c
ceylon
cfscript, cfc
clojure, clj, cljs
cmake
coffeescript, coffee, coffee-script
common_lisp, cl, common-lisp, elisp, emacs-lisp
conf, config, configuration
console, terminal, shell_session, shell-session
coq
cpp, c++
crystal, cr
csharp, c#, cs
css
d, dlang
dart
diff, patch, udiff
digdag
docker, dockerfile
dot
eiffel
elixir, elixir, exs
elm
erb, eruby, rhtml
erlang, erl
escape, esc
factor
fortran
fsharp
gherkin, cucumber, behat
glsl
go, go, golang
gradle
graphql
groovy
hack, hack, hh
haml, HAML
handlebars, hbs, mustache
haskell, hs
hcl
html
http
hylang, hy
idlang
igorpro
ini
io
irb, pry
java
javascript, js
jinja, django
json
json-doc
jsonnet
jsp
jsx, jsx, react
julia, jl
kotlin
lasso, lassoscript
liquid
literate_coffeescript, litcoffee
literate_haskell, lithaskell, lhaskell, lhs
llvm
lua
m68k
magik
make, makefile, mf, gnumake, bsdmake
markdown, md, mkd
mathematica, wl
matlab, m
moonscript, moon
mosel
mxml
nasm
nginx
nim, nimrod
nix, nixos
objective_c, objc, obj-c, obj_c, objectivec
ocaml
pascal
perl, pl
php, php, php3, php4, php5
plaintext, text
plist, plist
powershell, posh, microsoftshell, msshell
praat
prolog, prolog
prometheus, prometheus
properties
protobuf, proto
puppet, pp
python, py
q, kdb+
qml, qml
r, r, R, s, S
racket
ruby, rb
rust, rs, rust, no_run, rs, no_run, rust, ignore, rs, ignore, rust, should_panic, rs, should_panic
sass
scala, scala
scheme
scss
sed
shell, bash, zsh, ksh, sh
sieve
slim
smalltalk, st, squeak
smarty, smarty
sml, ml
sqf
sql
supercollider
swift
tap, tap
tcl
terraform, tf
tex, TeX, LaTeX, latex
toml
tsx
tulip, tulip
turtle
twig
typescript, ts
vala
vb, visualbasic
verilog
vhdl
viml, vim, vimscript, ex
vue, vuejs
wollok
xml
xojo, realbasic
yaml, yml
```



# 
7. 블록 인용 (Blockquotes)<br>
블록 인용은 >를 사용합니다.
```
> 이것은 인용입니다.
> 
>  여러 줄의 인용입니다.
```

#
8. 수평선 (Horizontal Rules)<br>
수평선은 ---, ***, ___ 등을 사용합니다.
```
---
***
___
```

#
9. 표 (Tables)<br>
표는 |와 -를 사용합니다.
```
| 헤더 1 | 헤더 2 |
| ------ | ------ |
| 셀 1   | 셀 2   |
| 셀 3   | 셀 4   |
```

#
10. 체크리스트 (Task Lists)<br>
체크리스트는 - [ ] (미완료)와 - [x] (완료)를 사용합니다.
```
- [ ] 할 일 1
- [x] 할 일 2
- [ ] 할 일 3
```