 라즈베리파이에 웹 서버 구축하기 

![img](https://projects-static.raspberrypi.org/projects/python-web-server-with-flask/f90230f1714f7357b1957659e2fe53100da25844/en/images/banner.png)

: 라즈베리파이에 웹 서버를 구축하고, 접속하는 방법을 알아보자.

# 작업순서 
1. 가상환경 설정 
```bash
python3 -m venv venv
```
2. 가상환경 활성화
```bash
source venv/bin/activate
```
3. Flask 설치
```bash
sudo apt-get install python3-flask
```
4. 프로젝트 폴더 만들기   
```bash
mkdir webapp    
```
5. Thonny IDE에서 코드 작성하기
```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return 'Hello world'
```
6. Thonny IDE에서 코드 실행하기
7. 웹 프라우져를 열고 `http://localhost:5000`로 접속하기
8. Thonny IDE에서 코드 실행 정지하기

# 응용 - 1. 새로운 페이지 추가하기
```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return 'Hello world'

@app.route('/cakes')
def cakes():
    return 'Yummy cackes!'

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0')
```
# 응용2 - html 파일을 웹에서 보여지게하기
1. template 폴더 만들기
```bash 
mkdir templates
```
2. index.html 파일 만들기
```html
<html>
<body>
<h1>My website</h1>
</body>
</html>
```
3. render_template 함수를 사용하여 index.html 파일을 웹에서 보여지게 하기
```python 
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def index():
    #return 'Hello world'
    return render_template('index.html')

@app.route('/cakes')
def cakes():
    return 'Yummy cackes!'

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0')
```
4. Thonny IDE에서 코드 실행하기
5. 웹 프라우져를 열고 `http://localhost:5000/cakes`로 접속하기
6. html 파일 내용이 웹에서 보여지는 것을 확인하기

# 응용3 - css 파일을 웹에서 보여지게하기
1. static 폴더 만들기
```bash
mkdir static
```
2. style.css 파일 만들기
```css
body {
	background: red;
	color: yellow;
}
```
3. index.html 파일 수정하기
```html
<html>
<head>
<link rel="stylesheet" href='/static/style.css' />
</head>
<body>
<h1>My website</h1>
</body>
</html>
```
4. Thonny IDE에서 코드 실행하기
5. 웹 프라우져를 열고 `http://localhost:5000`로 접속하기
6. css 파일 내용이 웹에서 보여지는 것을 확인하기




# 참고
- [Build a Python Web Server with Flask](https://projects.raspberrypi.org/en/projects/python-web-server-with-flask)

