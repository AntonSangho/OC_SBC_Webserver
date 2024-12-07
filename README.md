# 🎬 공학도서관 오리지널 컨텐츠

# 🌐 라즈베리파이 웹페이지 만들기

## 📝 프로젝트 소개
이 프로젝트는 Flask를 활용하여 라즈베리파이에서 웹페이지를 만드는 과정을 설명합니다. 파이썬으로 간단한 웹 서버를 구축하고 HTML과 CSS를 활용하여 웹페이지를 꾸미는 방법을 배울 수 있습니다.

## 📚 사전학습
이 프로젝트를 시작하기 전에 아래 내용을 먼저 공부하고 오시면 좋아요.

- 라즈베리파이 기초
  - 라즈베리파이 OS 사용법
  - 터미널 기본 명령어
  - 파이썬 기본 문법

- 웹 개발 기초
  - HTML 기본 구조 이해하기
  - CSS 기본 스타일링 알아보기
  - Flask 프레임워크 개념

- 개발 환경
  - 가상환경 개념 이해하기
  - pip 패키지 관리자 사용법
  - Thonny IDE 사용법

## 🎯 성취 목표
- Flask로 웹 서버를 구축할 수 있다.
- 파이썬 가상환경을 설정할 수 있다.
- 간단한 웹페이지를 만들 수 있다.
- HTML과 CSS 파일을 수정할 수 있다.
- 한글 웹페이지를 제작할 수 있다.

## 🛠 준비물
- 라즈베리파이 4
- SD 카드
- 모니터
- HDMI 케이블
- 키보드/마우스
- USB 메모리
- 전원 어댑터

## 📋 필요한 패키지
| 패키지명 | 설명 | 설치 명령어 |
|--------|------|------------|
| Python3-venv | 가상환경 패키지 | `sudo apt-get install python3-venv` |
| Flask | 웹 프레임워크 | `pip install flask` |
| ibus-hangul | 한글 입력기 | `sudo apt-get install ibus-hangul` |
| fonts-nanum | 나눔폰트 | `sudo apt-get install fonts-nanum` |

## 📁 프로젝트 구조
```
webapp/
├── app.py           # Flask 메인 애플리케이션
├── templates/       # HTML 템플릿 폴더
│   └── index.html  # 메인 페이지
└── static/         # 정적 파일 폴더
    └── style.css   # CSS 스타일시트
```

## 💾 실습 코드
| 파일명 | 설명 |
|--------|------|
| [app.py](./src/webapp/app.py) | Flask 실행파일 |
| [index.html](./src/webapp/templates/index.html) | HTML 템플릿  |
| [style.css](./src/webapp/static/style.css) | CSS 스타일  |

## 🚀 시작하기
1. 라즈베리파이 부팅하기

2. 가상환경 설정 및 Flask 설치
   ```bash
   python3 -m venv venv                # 파이썬 가상환경 설정
   source venv/bin/activate            # 가상환경 활성화
   deactivate                          # 가상환경 비활성화
   source venv/bin/activate            # 다시 활성화
   pip install Flask                   # Flask 패키지 설치
   pip list                           # 설치된 패키지 확인
   ```

3. 프로젝트 폴더 생성
   ```bash
   mkdir webapp                        # 프로젝트 폴더 생성
   ```

4. 기본 웹 애플리케이션 만들기
   - Thonny 실행
   - 아래 코드 작성
   ```python
   from flask import Flask

   app = Flask(__name__)

   @app.route('/')
   def index():
      return 'Hello world'
   ```
   - webapp 폴더에 app.py로 저장
   - Run 버튼으로 실행
   - http://127.0.0.1:5000 접속 확인

5. 웹 애플리케이션 수정하기
   ```python
   from flask import Flask

   app = Flask(__name__)

   @app.route('/')
   def index():
      return 'Hello world sangho'
   ```

6. 한글 설정하기
   - 라즈베리파이 메뉴 → Preferences → Raspberry Pi Configuration
   - Localisation 탭 선택
   - Set Locale 설정:
     - Language: ko (Korean)
     - Country: KR (South Korea)
     - Character Set: UTF-8
   - 재부팅 여부 묻는 창에서 'No' 선택

7. 시스템 업데이트 및 한글 설치
   ```bash
   sudo apt-get update -y && sudo apt-get upgrade -y   # 시스템 업데이트
   clear                                               # 터미널 정리
   sudo apt install ibus ibus-hangul                   # 한글 입력기 설치
   sudo apt install fonts-nanum fonts-unfonts-core     # 한글 폰트 설치
   sudo reboot                                         # 재부팅
   ```

8. 한글로 웹페이지 수정하기
   ```python
   from flask import Flask

   app = Flask(__name__)

   @app.route('/')
   def index():
      return '공학도서관'
   ```

9. 프로젝트 구조 만들기
   ```bash
   cd webapp
   mkdir templates              # HTML 파일용 폴더
   mkdir static                 # CSS 파일용 폴더
   ```

10. Flask 애플리케이션 수정하기
    ```python
    from flask import Flask, render_template 

    app = Flask(__name__)

    @app.route('/')
    def index():
       return render_template('index.html')

    if __name__ == '__main__':
       app.run(debug=True, host='0.0.0.0')
    ```

11. HTML 템플릿 만들기 (templates/index.html)
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>공학도서관</title>
        <link rel="stylesheet" href="./static/style.css">
    </head>

    <body>
        <div id="wrap">
            <div class="box1">
                <div>포장하기</div>
            </div> 
            <div class="content">
                <div>어떻게 식사?</div>
            </div>
            <div class="box2">
                <div>먹고가기</div>
            </div> 
        </div>
    </body>
    </html>
    ```

12. CSS 스타일 작성하기 (static/style.css)
    ```css
    @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100..900&display=swap');

    body {
        font-size: 2rem;
        font-weight: 600;
        font-family: "Noto Sans KR", sans-serif;
        font-style: normal;
        color: #ffffff;
        margin: 0;
    }

    #wrap {
        width: 100vw;
        height: 100vh;
        background-color: #A52A2A;
        display: flex;
        align-items: center;
        justify-content: space-around;
    }

    .box1 {
        width: 300px;
        height: 300px;
        background-color: #006500;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .box2 {
        width: 300px;
        height: 300px;
        background-color: #DDAA520;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    ```

13. 웹 애플리케이션 실행 및 확인
    - Thonny에서 app.py 실행
    - 웹 브라우저에서 새로고침
    - 스타일이 적용된 페이지 확인

## 🔍 문제해결
- 한글이 깨져서 나와요
  - 라즈베리파이 설정에서 Locale이 제대로 설정되었는지 확인해보세요.
  - HTML 파일의 charset이 UTF-8로 되어있는지 확인해보세요.
  - 한글 폰트가 제대로 설치되었는지 확인해보세요.

- 웹페이지가 열리지 않아요
  - app.py가 실행 중인지 확인해보세요.
  - host='0.0.0.0' 설정이 되어있는지 확인해보세요.
  - 터미널에서 오류 메시지를 확인해보세요.

- CSS가 적용되지 않아요
  - static 폴더 경로가 맞는지 확인해보세요.
  - HTML 파일의 CSS 링크 경로가 올바른지 확인해보세요.
  - 파일 이름이 정확한지 다시 한번 살펴보세요.

## 🌟 이렇게 업그레이드 해볼 수 있어요
- 메뉴판 만들기
  - 음식 사진을 추가해보세요.
  - 가격 정보를 표시해보세요.
  - 클릭하면 주문 페이지로 넘어가도록 만들어보세요.

- 반응형 웹페이지 만들기
  - 모바일에서도 잘 보이도록 수정해보세요.
  - 화면 크기에 따라 레이아웃이 바뀌게 해보세요.
  - 다양한 기기에서 테스트해보세요.

- 주문 시스템 추가하기
  - 장바구니 기능을 만들어보세요.
  - 결제 페이지를 추가해보세요.
  - 주문 내역을 저장하고 관리해보세요.

## 📚 참고 자료
- [Flask 공식 문서](https://flask.palletsprojects.com/)
- [Python 가상환경 설명서](https://docs.python.org/3/tutorial/venv.html)
- [CSS 컬러코드](https://www.w3schools.com/cssref/css_colors.php)

> **주의사항**: 
> - 가상환경을 활성화한 상태에서 작업해야 해요.
> - 파일 경로와 대소문자를 정확히 입력해야 해요.
> - 수정 후에는 항상 서버를 재시작해야 해요.
> - debug=True는 개발 중에만 사용하세요.



