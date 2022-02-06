# CS50's Web Programming with Python and JavaScript 2020
(用 Python 和 JavaScript 进行 Web 开发)

## HTML

### 1.第一个HTML文件

```html
<!DOCTYPE html> /* <!DOCTYPE> 声明不是 HTML 标签；它是指示 web 浏览器关于页面使用哪个 HTML 版本进行编写的指令。*/
<html lang="en">
    <head>
        <title>Hello!</title>
    </head>
    <body>
        Hello world!
    </body>
</html>
```

### 2.标题（h1元素）

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Headings!</title>
    </head>
    <body>
        <h1>This is the biggest head.</h1>
        <h6>This is the smallest head.</h6>
    </body>
</html>
```

### 3.列表（ol，ul元素）

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Lists</title>
    </head>
    <body>
        An Unordered list:
        <ul> // 无需列表
            <li>One Item</li>
            <li>Another Item</li>
            <li>Yet Another Item</li>
        </ul>
        An ordered list:
        <ol> // 有序列表
            <li>First item</li>
            <li>Second item</li>
            <li>Third item</li>
        </ol>
    </body>
</html>
```

### 4.图片(img元素)

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Image</title>
    </head>
    <body>
        <img src="test.jpg" alt="test" width="500">
    </body>
</html>
```

### 5.链接（a元素）anchor

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Link</title>
    </head>
    <body>
        <a href="image.html">Click here</a> <!href=Hyperlink reference>
    </body>
</html>
```

### 6.表格（table元素）

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Table</title>
</head>

<body>
    <table>
        <thead>
            <th>Ocean</th>  <!th=table head>
            <th>Average Depth</th>
            <th>Maximum Depth</th>
        </thead>
        <tbody>
            <tr>  <!tr=table row>
                <td>Pacific Ocean</td>
                <td>4,820m</td>
                <td>10,911m</td>   <!td=table data>
            </tr>
            <tr>
                <td>Atlantic Ocean</td>
                <td>3,646m</td>
                <td>8,486m</td> 
            </tr>
        </tbody>
    </table>
</body>

</html>
```

![image-20210823204246388](https://i.loli.net/2021/08/23/p9GV17xSincHqym.png)

### 7.表单（form元素）

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Form</title>
    </head>
    <body>
        <form>     <! placeholder指默认的提示文字，name指返回给服务器的这个对象的名字>
            <div>
            <input name="name" type="text" placeholder="Full name" >
            <input name="password" type="password" placeholder="Password">
            <input type="submit">
            </div>

            <div>
                Favorite color?
                <input name="color" type="radio" value="red">Red
                <input name="color" type="radio" value="green">Green
                <input name="color" type="radio" value="blue">Blue
                <input name="color" type="radio" value="other">Other 
            </div>


            <!Data list>
            <div>
                <input name="country" list="countries" placeholder="Country">
                <datalist id="countries">
                    <option value="America">
                    <option value="China">
                    </option>
                    </option>
                </datalist>
            </div>
        </form>
    </body>
</html>
```

## CSS

### 1.内联样式

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello!</title>
    </head>
    <body >
        <h1 style="color: red;text-align: center;">Welcome to my Web Page!</h1>
        Hello world!
    </body>
</html>
```

### 2.内部样式表

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello!</title>
        <style>
            h1{
                color: red;
                text-align: center;
            }
        </style>
    </head>
    <body >
        <h1 >Welcome to my Web Page!</h1>
        <h1>This is a second head.</h1>
        Hello world!
    </body>
</html>
```

### 3.外部样式表

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello!</title>
        <link rel="stylesheet" href="styles.css">
    </head>
    <body >
        <h1 >Welcome to my Web Page!</h1>
        <h1>This is a second head.</h1>
        Hello world!
    </body>
</html>
```

```CSS
h1{
    color: pink;
    text-align: center;
}
```

### 4.宽带，高度，内外边距

```CSS
div{
    background-color:orangered;
    width: 200px;
    height: 200px;
    padding: 20px; /*内边距*/
    margin: 20px;  /*外边距*/
    }
```

### 5.字体样式

```CSS
div{
    font-family:Arial,sans-serif;
    font-size: 40px;
    font-weight: bold;
    }
```

### 6.边框和表格应用

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Table</title>
    <style>
        table{
            border: 1px solid blue;
            border-collapse: collapse;
        }
        td,th{
            border: 1px solid black;
            padding: 5px;
        }
    </style>
</head>

<body>
    <table>
        <thead>
            <th>Ocean</th>  <!th=table head>
            <th>Average Depth</th>
            <th>Maximum Depth</th>
        </thead>
        <tbody>
            <tr>  <!tr=table row>
                <td>Pacific Ocean</td>
                <td>4,820m</td>
                <td>10,911m</td>   <!td=table data>
            </tr>
            <tr>
                <td>Atlantic Ocean</td>
                <td>3,646m</td>
                <td>8,486m</td> 
            </tr>
        </tbody>
    </table>
</body>

</html>
```

![image-20210825155840786](https://i.loli.net/2021/08/25/sek9PMbJ4vcKpX7.png)

### 7.id和class

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello!</title>
        <style>
            #foo {                               /*id用#引用，每个id都是唯一的 */
                color: brown;
                text-align: center;
            }

            .baz {                               /*class用.引用*/
                color:red;
            }
        </style>
    </head>
    <body >
        <h1 id="foo">Welcome to my Web Page!</h1>
        <h1 class="baz">This is a second head.</h1>
        <h1 class="baz">This is a third head.</h1>
        Hello world!
    </body>
</html>
```

### 8.Specificity（CSS样式权重）

1.inline

2.id

3.class

4.type

### 9.CSS选择器

![image-20210824094149040](https://i.loli.net/2021/08/24/FQSA8KBO9VyHfTI.png)

子类

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Descendant</title>
        <style>
            ul>li {     /*改变unordered list的子类item的样式*/
                color: blue;
            }
        </style>
    </head>
    <body>
        <ol>
            <li>list item one</li>
            <li>list item two</li>
            <ul>
                <li>sub list item one</li>
                <li>sub list item two</li>
            </ul>
            <li>]list item three</li>
        </ol>
    </body>
</html>
```

![image-20210825155941241](https://i.loli.net/2021/08/25/YcFI92QtSDiau37.png)

单独给链接设置属性

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Attribute</title>
        <style>
            a{
                color: green;
            }
            a[href="http://www.jsut.edu.cn"]{
                color: greenyellow;
            }
        </style>
    </head>
    <body>
        <ul>
            <li><a href="https://baidu.com">Baidu</a></li>
            <li><a href="http://www.jsut.edu.cn">JSUT</a></li>
            <li><a href="http://www.xhgz.com">Xinhai</a></li>
        </ul>
    </body>
</html>
```

![image-20210824100709449](https://i.loli.net/2021/08/24/L8PaQe1EBTSrt7I.png)

伪类

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hover</title>
        <style>
            button{
                width: 200px;
                height: 50px;
                font-size: 24px;
                background-color: green;
            }

            button:hover {
                background-color: orange;
            }
        </style>
    </head>
    <body>
        <button>Click me!</button>
    </body>
</html>
```

![image-20210824105153691](https://i.loli.net/2021/08/24/8bmNVOMHfrP7qsT.png)

### 10.Responsive Design

* Viewport

```HTML
<meta name="viewport" content="width=device-width,initial-scale=1.0">
```

* media query

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Responsive</title>
        <style>
            @media (min-width:600px) { /*如果宽度大于等于600px*/
                body{
                    background-color: red;
                }
            }
            @media (max-width:599px) { /*如果宽度小于等于599px*/
                body{
                    background-color: blue;
                }
            }
        </style>
    </head>
    <body>
        <h1>Welcome to my web page!</h1>
    </body>
</html>
```

* flexbox

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Flexbox</title>
        <style>
            #container {
                display: flex;
                flex-wrap: wrap;
            }
            #container > div{
                background-color: green;
                font-size: 20px;
                margin: 20px;
                padding: 20px;
                width: 200px;
            }
        </style>
    </head>
    <body>
        <div id="container">
            <div>1.This is inside of a div to demo flexbox</div>
            <div>2.This is inside of a div to demo flexbox</div>
            <div>3.This is inside of a div to demo flexbox</div>
            <div>4.This is inside of a div to demo flexbox</div>
            <div>5.This is inside of a div to demo flexbox</div>
            <div>6.This is inside of a div to demo flexbox</div>
            <div>7.This is inside of a div to demo flexbox</div>
            <div>8.This is inside of a div to demo flexbox</div>
            <div>9.This is inside of a div to demo flexbox</div>
            <div>10.This is inside of a div to demo flexbox</div>
            <div>11.This is inside of a div to demo flexbox</div>
            <div>12.This is inside of a div to demo flexbox</div>
        </div>
    </body>
</html>
```

* grid(网格)

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Grid</title>
        <style>
            #grid{
                background-color: green;
                display: grid;
                padding: 20px;
                grid-column-gap: 20px; 
                grid-row-gap: 10px;
                grid-template-columns: 200px 200px auto;
            }
            .div-item{
                background-color: white;
                font-size: 20px;
                padding: 20px;
                text-align: center;

            }
        </style>
    </head>
    <body>
        <div id="grid">
            <div class="div-item">1</div>
            <div class="div-item">2</div>
            <div class="div-item">3</div>
            <div class="div-item">4</div>
            <div class="div-item">5</div>
            <div class="div-item">6</div>
            <div class="div-item">7</div>
            <div class="div-item">8</div>
            <div class="div-item">9</div>
            <div class="div-item">10</div>
            <div class="div-item">11</div>
            <div class="div-item">12</div>
        </div>
    </body>
</html>
```

![image-20210824115553622](https://i.loli.net/2021/08/24/NHacuSrnPCmiZWf.png)

### 11.Bootstrap

[Bootstrap](https://getbootstrap.com/)

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Hello!</title>
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-KyZXEAg3QhqLMpG8r+8fhAXLRk2vvoC2f3B09zVXn8CA5QIVfZOJ3BCsw2P0p/We" crossorigin="anonymous">
    </head>
    <body>
        Hello world!
        <div class="alert alert-danger" role="alert">
            Here is my alert!
        </div>
    </body>
</html>
```

### 12.Sass

给CSS添加变量，找出其中的共同性，每次改变后都要编译scss文件，浏览器只能识别css

```
scss .\variable.scss:.\variable.css
scss --watch .\variable.scss:.\variable.css
```

```scss
%message{
    font-family: 'Courier New', Courier, monospace;
    font-size: 19px;
    font-weight: bold;
    margin: 4px;
    padding: 4px;
}

.success{
    @extend %messages;
    background-color: aqua;
}
```

## Git

## Python

```python
print(f"There is {len(s)} elements in it")
```

```python
houses={"Harry":"Gryffindor","Draco":"Slytherin"}
houses["Hermione"]="Gryffindor"
print(houses["Harry"])
```

### 1.第一个类

```Python
class Point():
    def __init__(self,x,y):
        self.x=x
        self.y=y

p=Point(2,8)
print(p.x)
print(p.y)
```

### 2.Python类的应用

```Python
class Flight():
    def __init__(self,capacity) -> None:
        self.capacity = capacity
        self.passengers = []

    def add_passenger(self,name):
        if not self.open_seats():
            return False
        self.passengers.append(name)
        return True

    def open_seats(self):
        return self.capacity - len(self.passengers)

flight = Flight(3)

people = ["Harry","Ron","Hermione","Ginny"]

for person in people:
    if flight.add_passenger(person):
        print(f"Add {person} to flight successfully!")
    else:
        print(f"No available seat for {person}.")
```

### 3.装饰器

```Python
def announce(f):
    def wrapper():
        print("About to run the function")
        f()
        print("Done with the function.")
    return wrapper

@announce
def hello():
    print("Hello world!")

hello()
```

## Django

![image-20210825123741695](https://i.loli.net/2021/08/25/oHZckUSR8euXpJ2.png)

### 1.安装Django

```
python -m pip install Django
```

### 2.新建Django项目

```
django-admin startproject lecture3
```

### 3.启动项目

```
python .\manage.py runserver
```

### 4.结束项目

```
Ctrl+C
```

### 5.新建APP

```
python .\manage.py startapp hello
```

新建APP后，在项目文件夹setting.py和urls.py中，添加必要信息

```python
setting.py
INSTALLED_APPS = [
    'hello',
    'newyear',
    'tasks',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
```



```python
urls.py
urlpatterns = [
    path('admin/', admin.site.urls),
    path('hello/', include("hello.urls")),
    path('tasks/', include("tasks.urls")),
    path('newyear/',include("newyear.urls"))
]
```



### 6.配置URL

/hello/urls.py

```python
from django.urls import path

from . import views

urlpatterns=[
    path("",views.index,name = "index")
]
```

### 7.Templates

**curly based percent sign** ：花括号百分号 即 {% %}

```html
{% load static %}
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Is it New Year's?</title>
        <link href="{% static 'newyear/styles.css' %}" rel="stylesheet">
    </head>
    <body>
        {% if newyear %}
            <h1>YES</h1>
        {% else %}
            <h1>NO</h1>
        {% endif %}
    </body>
</html>
```

### 8.应用:To Do List

views.py

```python
from django.shortcuts import render
from django import forms
from django.http.response import HttpResponseRedirect
from django.http import HttpResponseRedirect
from django.urls import reverse


tasks=[]

class NewTaskForm(forms.Form):
    task=forms.CharField(label="New Task")
    # priority=forms.IntegerField(label="Priority",min_value=1,max_value=5)

# Create your views here.
def index(request):
    return render(request,"tasks/index.html",{
        "tasks":tasks
    })

def add(request):
    if request.method == "POST":
        form = NewTaskForm(request.POST)
        if form.is_valid():
            task = form.cleaned_data["task"]
            tasks.append(task)
            return HttpResponseRedirect(reverse("tasks:index"))
        else:
            return render(request,"task/add.html",{
                "form":form
            })
    return render(request,"tasks/add.html",{
        "form":NewTaskForm()
    })
```

## SQLite

![image-20210826175655544](https://i.loli.net/2021/08/26/bWY26VmtTOIAzK9.png)

![image-20210826175716696](C:\Users\leo\AppData\Roaming\Typora\typora-user-images\image-20210826175716696.png)

![image-20210826175954588](https://i.loli.net/2021/08/26/AJnpLxuwmcvbBTa.png)

![image-20210826180133584](https://i.loli.net/2021/08/26/UhAX2KxFo5BOSCl.png)

### 1.SQLite Types

* TEXT
* NUMERIC
* INTEGER
* REAL
* BLOB

### 2. 新建一个数据库

```sqlite
CREATE TABLE flights (
	id INTEGER PRIMARY KEY AUTOINCREMENT,
    origin TEXT NOT NULL,
    destination TEXT NOT NULL,
    duration INTEGER NOT NULL
);
```

### 3.添加数据

```sqlite
INSERT INTO flights (origin,destination,duration) VALUES ("New York","London",415);
```

### 4.查看数据

```sqlite
SELECT * FROM flights;
SELECT * FROM flights WHERE origin ="New York";
SELECT * FROM flights WHERE duration > 500;
SELECT * FROM flights WHERE duration > 500 AND destination = "Paris";
SELECT * FROM flights WHERE origin LIKE "%a%";
```

### 5.修改样式

```sqlite
.mode columns
.headers yes
```

### 6.修改数据

```sqlite
UPDATE flights 
	SET duration = 430
	WHERE origin = "New York"
	AND destination = "London";
```

### 7.删除数据

```sqlite
DELETE FROM flights WHERE destination = "Tokyo";
```

### 8.Other Clauses

* LIMIT
* ORDER BY
* GROUP BY
* HAVING

### 9.JOIN语句

```sqlite
SELECT first,origin,destination
	FROM flights JION passsengers
ON passengers.flight_id = flights.id;
```

### 10. CREAT INDEX

```sqlite
CREATE INDEX name_index ON passengers(last); 
```

## JavaScript

```html
<script>
alert('Hello world!');
</script>
```

```javascript
// Change font color to red
                document.querySelector('#red').onclick = function(){
                    document.querySelector('#hello').style.color = 'red';
                }
```

```javascript
document.addEventListener('DOMContentLoaded',function(){
                document.querySelectorAll('button').forEach(function(button){
                    button.onclick = function(){
                        document.querySelector('#hello').style.color = button.dataset.color;
                    }
                });
            });
```

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Colors</title>
        <script>

            document.addEventListener('DOMContentLoaded',() => {

                document.querySelectorAll('button').forEach(button => {
                    button.onclick = function() {
                        document.querySelector('#hello').style.color = button.dataset.color;
                    }
                });
            });

        </script>
    </head>
    <body>
        <h1 id="hello">Hello!</h1>
        <button data-color="red">Red</button>
        <button data-color="blue">Blue</button>
        <button data-color="green">Green</button>
    </body>
</html>
```

```javascript
document.addEventListener('DOMContentLoaded',() => {

                document.querySelector('select').onchange = function() {
                    document.querySelector('#hello').style.color = this.value;
                }
            });

```

```javascript
document.addEventListener('DOMContentLoaded',function() {

                // By default, submit button should be disabled
                document.querySelector('#submit').disabled = true;

                document.querySelector('#task').onkeyup = () =>{
                    if(document.querySelector('#task').value.length > 0) {
                        document.querySelector('#submit').disabled = false;
                    } else {
                        document.querySelector('#submit').disabled = true;
                    }
                }

                document.querySelector('form').onsubmit = () => {
                    const task = document.querySelector('#task').value;
                    
                    const li = document.createElement('li');
                    li.innerHTML = task;

                    document.querySelector('#tasks').append(li);

                    document.querySelector('#task').value = '';

                    document.querySelector('#submit').disabled = true;
                    // Stop form from submitting
                    return false;
                }
            });
```

```JavaScript
setInterval(count,1000);
```

### singlepage.html

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>SinglePage</title>
        <style>
            div {
                display: none;
            }
        </style>
        <script>
            function showPage(page) {
                document.querySelectorAll('div').forEach(div => {
                    div.style.display = 'none';
                })
                document.querySelector(`#${page}`).style.display = 'block';
            }

            document.addEventListener('DOMContentLoaded',function() {
                document.querySelectorAll('button').forEach(button => {
                    button.onclick = function() {
                        showPage(this.dataset.page);
                    }
                })
            });
        </script>
    </head>
    <body>
        <button data-page="page1">Page 1</button>
        <button data-page="page2">Page 2</button>
        <button data-page="page3">Page 3</button>
        <div id="page1">
            <h1>This is Page 1</h1>
        </div>
        <div id="page2">
            <h1>This is Page 2</h1>
        </div>
        <div id="page3">
            <h1>This is Page 3</h1>
        </div>
    </body>
</html>
```

### animation

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Animate</title>
        <style>
            @keyframes grow {
                0% {
                    left: 0%;
                    font-size: 20px;
                    color: rgb(0, 255, 21);
                } 
                50% {
                    left: 50%;
                    font-size: 100px;
                    color: rgb(0, 183, 255);
                }

                100% {
                    left: 0%;
                    font-size: 20px;
                    color: red;
                }
            }

            h1 {
                position: relative;
                animation-name:grow;
                animation-duration:2s ;
                animation-fill-mode:forwards ;
                animation-iteration-count: infinite;
            }
        </style>
        <script>
            document.addEventListener('DOMContentLoaded',function() {

                const h1 = document.querySelector('h1');
                h1.style.animationPlayState = 'paused';

                document.querySelector('button').onclick = () => {
                    if(h1.style.animationPlayState === 'paused') {
                        h1.style.animationPlayState = 'running';
                    } else {
                        h1.style.animationPlayState = 'paused';
                    }
                }
            });
        </script>
    </head>
    <body>
        <button>Click Here!</button>
        <h1>Welcome</h1>
    </body>
</html>
```

# CI/CD

* Continuous Integration
  * Frequent merges to main branch
  * Automated unit testing
* Continuous Delivery
  * Short release schedules
