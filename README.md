 # Netflix 화면 구현
> 2023년 2월 9일 ~ 2023년 2월 10일


<div align='center'>
</div>
<br/>

## 팀원 💁
- 고석주
- 강동엽
- 이재영F



## 목차 :bookmark_tabs:

- [Mock up](#Mockup)


- [개요](#개요)


- [시연영상](#시연영상)



- [코드](#코드)


- [추가기능](#추가하고싶은기능)

## 개요
- JavaScript
- HTML
- CSS
- Bootstrap
- Firebase


#### 서비스 개요


## Mockup

## 시연영상
### 1.Google Search
![google_search](https://user-images.githubusercontent.com/116260619/218020671-0dd0595b-09b2-458c-b4fa-02c95d950b61.gif)

## 2.Join
![join](https://user-images.githubusercontent.com/116260619/218020750-aa874d56-c70c-4de2-a14e-7a0061751eff.gif)
### 
![create_id](https://user-images.githubusercontent.com/116260619/218020770-1a5e9d37-4bb3-45e6-a8b2-5b8b71feefe7.jpg)
### 회원가입 완료 후 Firebase Database 안에 조건에 맞는 회원이 생성 되었음을 알 수 있다.

## 시연영상 3
![login_check](https://user-images.githubusercontent.com/116260619/218020903-11059bd5-be81-4726-af76-b334b74b2d72.gif)

## 시연영상 4

## 시연영상 5





### 링크 [https://kdy1493.github.io/Netflix-clone/]




## Trouble Shooting
- 





## 코드

### index.html
```
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD" crossorigin="anonymous">
    <link href="./index.css" rel="stylesheet">
    <link rel="icon" href="./image/favicon.ico">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js" integrity="sha384-w76AqPfDkMBDXo30jS1Sgez6pr3x5MlQ1ZAGC+nuZB+EYdgRZgiwxhTBTkF7CXvN" crossorigin="anonymous"></script>
    <title>넷플릭스 대한민국 - 인터넷으로 시리즈와 영화를 시청하세요</title>
</head>
<body>
    <div class="container fixed-top">
        <nav class="navbar navbar-expand-lg d-flex">
            <div class="container-fluid d-flex justify-content-between">
                <a class="navbar-brand" href="#">
                    <img src="./image/logo.png" alt="logo" height="50">
                </a>
            <button class="btn btn-danger" style="background-color: #E50914;"><a href="./log.html"><b>로그인</b></a></button>
            </div>
        </nav>
    </div>

    <div class="position-relative" id="background">
        <div id="main-text" class="container-fluid position-absolute start-50 translate-middle text-center">
            <h2 class="text-light">영화와 시리즈를 무제한으로.</h2>
            <h5 class="text-light">다양한 디바이스에서 시청하세요. 언제든 해지하실 수 있습니다.</h5>
            <p class="text-light">시청할 준비가 되셨나요? 시작하려면 상단의 로그인 버튼을 클릭하세요.</p>      
            <form method="GET" action="https://www.google.com/search" target="_blank">
                <div class="container d-flex justify-content-center">
                    <div class="form-floating">
                        <input name="query" class="form-control" id="floatingInput"  required value=""  maxlength=255 placeholder="google search">
                        <label for="floatingInput" class="text-secondary text-opacity-75">구글 검색</label>    
                    </div>
                    <input type="submit" id="email-btn" class="btn btn-danger" style="background-color:#E50914;" value="검색하기">
                </div>
            </form>
        </div>

        <div id="background-gradient" class="container-fluid position-absolute"></div>
        <img src="./image/netflix_background.jpg" class="img-fluid position-relative" alt="background image">
    </div>

</body>
</html>
```

### Join.html
```
<!doctype html>
<html lang="en">
  <head>
  
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <link rel="icon" href="./image/favicon.ico">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
    <link rel="stylesheet" href="./style.css">
    <title>넷플릭스 대한민국 - 인터넷으로 시리즈와 영화를 시청하세요</title>
    
  </head>
  <body>
    
    <div class="container">
      <nav class="navbar navbar-expand-lg d-flex">
          <div class="container-fluid">
              <a class="navbar-brand" href="./index.html">
                  <img src="./image/logo.png" alt="logo" height="50">
              </a>
          </div>
      </nav>
    </div>

    <div class="d-flex justify-content-center align-items-center" style="width: 100vw;">
      <section class="login-box rounded-0">
        <h2 class="Login mb-4">회원 가입</h2>
        <form>
          <h6 class="name mb-2">이름</h6>

        <div class="input-group mb-5">
          <div class="input-group-text" id="basic-addon1"></div>
          <input type="text" id="name" class="form-control" placeholder="Username" aria-label="Username" >
        </div>
        
        <h6 class="email mb-2">이메일</h6>
        <div class="input-group mb-5">
          <input type="email" id="signUpEmail" class="form-control" placeholder="email" aria-label="email">
        </div>
        
        <h6 class="password mb-2">비밀번호</h6>
        <div class="input-group mb-4">
          <div class="input-group-text" id="basic-addon1"></div>
          <input type="password" id="signUpPassword" class="form-control" placeholder="password" aria-label="password" aria-describedby="basic-addon1">
        </div>

        <div class="d-grid gap-2 mb-2">
          <button type="submit" id="signUpButton" class="btn text-white btn-lg mt-3" style="background-color: #E50914;">회원 가입</button>
          </div>
        </form>
        <script type="module">
          // Import the functions you need from the SDKs you need
          import { initializeApp } from "https://www.gstatic.com/firebasejs/9.17.1/firebase-app.js";
          import { getAnalytics } from "https://www.gstatic.com/firebasejs/9.17.1/firebase-analytics.js";
          // TODO: Add SDKs for Firebase products that you want to use
          // https://firebase.google.com/docs/web/setup#available-libraries
        
          // Your web app's Firebase configuration
          // For Firebase JS SDK v7.20.0 and later, measurementId is optional
          const firebaseConfig = {
            apiKey: "AIzaSyBzTu2i61Pbu6zVwf4aIp8h0X6W-MR0lUE",
            authDomain: "netfilx-login.firebaseapp.com",
            projectId: "netfilx-login",
            storageBucket: "netfilx-login.appspot.com",
            messagingSenderId: "296625560128",
            appId: "1:296625560128:web:d81d0beef1e1003a101da5",
            measurementId: "G-B7VR01MCY2"
          };
        






          
          // Initialize Firebase
          const app = initializeApp(firebaseConfig);
          const analytics = getAnalytics(app);

          import { getAuth, createUserWithEmailAndPassword } from "https://www.gstatic.com/firebasejs/9.17.1/firebase-auth.js";

          document.getElementById("signUpButton").addEventListener('click', (event) => {
            event.preventDefault()
            const signUpEmail = document.getElementById('signUpEmail').value
            const signUpPassword = document.getElementById('signUpPassword').value
            
            const auth = getAuth();
            createUserWithEmailAndPassword(auth, signUpEmail, signUpPassword)
            
            .then((userCredential) => {
              console.log(userCredential)
              // Signed in 
              const user = userCredential.user;
              var link = 'log.html';
 
                location.href=link;
                location.replace(link);
                alert("가입 성공!")
                window.open(link);
              // ...
            })
            .catch((error) => {
              alert('아이디 또는 비밀번호를 확인하세요!')
              const errorCode = error.code;
              const errorMessage = error.message;
              // ..
            });
          })


          
        </script>

      </section>
    </div>
    


  
    
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-kenU1KFdBIe4zVF0s0G1M5b4hcpxyD9F7jL+jjXkk+Q2h455rYXK/7HAuoJl+0I4" crossorigin="anonymous"></script>
  </body>
</html>
```
### log.html
```<!doctype html>
<html lang="en">
  <head>
  
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <link rel="icon" href="./image/favicon.ico">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
    <link rel="stylesheet" href="./style.css">
    <title>넷플릭스 대한민국 - 인터넷으로 시리즈와 영화를 시청하세요</title>
    
  </head>
  <body>
    
    <div class="container">
      <nav class="navbar navbar-expand-lg d-flex">
          <div class="container-fluid">
              <a class="navbar-brand" href="./index.html">
                  <img src="./image/logo.png" alt="logo" height="50">
              </a>
          </div>
      </nav>
    </div>

    <div class="d-flex justify-content-center align-items-center" style="width: 100vw;">
      <section class="login-box rounded-0">
        <h2 class="Login">로그인</h2>

        <form action="./img_gallery.html" method="post">
          <div class="mb-1">
            <label for="exampleInputEmail1" class="form-label small-text"></label>
            <input type="email" class="form-control" id="signInEmail" aria-describedby="emailHelp" placeholder="이메일 주소 또는 전화번호">
          </div>
          <div class="mb-4">
            <label for="exampleInputPassword1" class="form-label"></label>
            <input type="password" class="form-control" id="signInPassword" placeholder="비밀번호">
          </div>

          <div class="d-grid gap-2 mb-2">
            <button type="submit" formaction="./img_gallery.html" id="signInButton" class="btn text-white btn-lg mt-3" style="background-color: #E50914;">로그인</button>
            </div>

          <!-- <div class="mb-3 form-check">
              <input type="checkbox" class="form-check-input" id="exampleCheck1">
              <label class="form-check-label text-white-50 small-text" for="exampleCheck1">로그인 정보 저장</label>
              <a class="btn btn-primary" href="join.html" role="button">회원가입</a>
          </div> -->
          <div class="hybrid-login-form-help d-flex justify-content-between">
            <div class="ui-binary-input login-remember-me">
              <input type="checkbox" class="" name="rememberMe" id="bxid_rememberMe_true" value="true" tabindex="0" data-uia="rememberMe" checked="">
              <label for="bxid_rememberMe_true" data-uia="label+rememberMe">
                <span class="login-remember-me-label-text text-white-50">로그인 정보 저장</span>
              </label>
             
            </div>
            <div>
              <a class="join_in text-white-50 small-text" style="text-decoration: none"  href="join.html">회원 가입</a>
            </div>  
            </form>
            <script type="module">
              // Import the functions you need from the SDKs you need
              import { initializeApp } from "https://www.gstatic.com/firebasejs/9.17.1/firebase-app.js";
              import { getAnalytics } from "https://www.gstatic.com/firebasejs/9.17.1/firebase-analytics.js";
              // TODO: Add SDKs for Firebase products that you want to use
              // https://firebase.google.com/docs/web/setup#available-libraries
            
              // Your web app's Firebase configuration
              // For Firebase JS SDK v7.20.0 and later, measurementId is optional
              const firebaseConfig = {
                apiKey: "AIzaSyBzTu2i61Pbu6zVwf4aIp8h0X6W-MR0lUE",
                authDomain: "netfilx-login.firebaseapp.com",
                projectId: "netfilx-login",
                storageBucket: "netfilx-login.appspot.com",
                messagingSenderId: "296625560128",
                appId: "1:296625560128:web:d81d0beef1e1003a101da5",
                measurementId: "G-B7VR01MCY2"
              };
            
              // Initialize Firebase
              const app = initializeApp(firebaseConfig);
              const analytics = getAnalytics(app);

              import { getAuth, signInWithEmailAndPassword } from "https://www.gstatic.com/firebasejs/9.17.1/firebase-auth.js";
              
              document.getElementById("signInButton").addEventListener('click', (event) => {
                event.preventDefault()
                const signInEmail = document.getElementById('signInEmail').value
                const signInPassword = document.getElementById('signInPassword').value

              const auth = getAuth();
              
              signInWithEmailAndPassword(auth, signInEmail, signInPassword)
                .then((userCredential) => {
                  // Signed in 
                  console.log(userCredential)
                  const user = userCredential.user;
                  // ...
                  var value = "hello";
                  location.href="./img_gallery.html/?value="+signInEmail.toString();
                })
                .catch((error) => {
                  console.log('로그인 실패')
                  const errorCode = error.code;
                  const errorMessage = error.message;
                });

              })

            </script>
           
        
      
      </section>
    </div>
    


  
    
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-kenU1KFdBIe4zVF0s0G1M5b4hcpxyD9F7jL+jjXkk+Q2h455rYXK/7HAuoJl+0I4" crossorigin="anonymous"></script>
  </body>
  ``` 
  
### img_gallery.html
```
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD" crossorigin="anonymous">
    <link href="./img_gallery.css" rel="stylesheet">
    <link rel="icon" href="./image/favicon.ico">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js" integrity="sha384-w76AqPfDkMBDXo30jS1Sgez6pr3x5MlQ1ZAGC+nuZB+EYdgRZgiwxhTBTkF7CXvN" crossorigin="anonymous"></script>
    <title>넷플릭스 대한민국 - 인터넷으로 시리즈와 영화를 시청하세요</title>
</head>
<body>
    <div class="container">
        <nav class="navbar navbar-expand-lg d-flex">
            <div class="container-fluid justify-content-start">
                <a class="navbar-brand" href="./index.html">
                    <img src="./image/logo.png" alt="logo" height="50">
                </a>
                <a class="nav-link" href="#"><p class="h6">TV프로그램</p></a>
                <a class="nav-link" href="#"><p class="h6">영화</p></a>
                <a class="nav-link" href="#"><p class="h6">내가 찜한 콘텐츠</p></a>
            </div>
            <div id="logout" class="container-fluid justify-content-end">
                <a class="nav-link" href="log.html"><p class="h6">로그아웃</p></a>
            </div>
        </nav>
    </div>
    <div id="carouselExampleCaptions" class="carousel slide" data-bs-ride="carousel">
        <div class="carousel-indicators">
            <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
            <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1" aria-label="Slide 2"></button>
            <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2" aria-label="Slide 3"></button>
            <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="3" aria-label="Slide 4"></button>
            <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="4" aria-label="Slide 5"></button>
            <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="5" aria-label="Slide 6"></button>
            <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="6" aria-label="Slide 7"></button>
        </div>
        <div class="carousel-inner">
            <div class="carousel-item position-relative active" data-bs-interval="6000">
                <span class="gradient position-absolute"></span>
                <img src="./image/Wednesday.jpg" class="d-block w-100" alt="Wednesday.jpg">
                <a href="https://www.netflix.com/kr/title/81231974">
                    <div class="carousel-caption d-none d-md-block">
                        <h5><b>웬즈데이</b></h5>
                        <p>
                            암울함을 풍기는 그녀가 네버모어 아카데미에서 연쇄 살인 사건을 조사하기 시작한다. <br/>
                            새 친구도 사귀고, 앙숙도 만들며.
                        </p>
                    </div>
                </a>
            </div>
            <div class="carousel-item position-relative" data-bs-interval="6000">
                <span class="gradient position-absolute"></span>
                <img src="./image/deluna.jpg" class="d-block w-100" alt="deluna.jpg">
                <a href="https://www.netflix.com/kr/title/81205849">
                    <div class="carousel-caption d-none d-md-block">
                        <h5><b>호텔 델루나</b></h5>
                        <p>
                            서울 도심에 수상한 호텔이 있다. 천년 영업에 숙박한 사람이 없다. 왜? 산 사람은 안 받으니까. <br/>
                            귀신만 묵는 그곳에 인간 지배인이 왔다. 알고 보면 심약한 이 남자, 고객 응대 잘 해낼까?
                        </p>
                    </div>
                </a>
            </div>
            <div class="carousel-item position-relative" data-bs-interval="6000">
                <span class="gradient position-absolute"></span>
                <img src="./image/CrashLanding.jpg" class="d-block w-100" alt="CrashLanding.jpg">
                <a href="https://www.netflix.com/kr/title/81159258">
                    <div class="carousel-caption d-none d-md-block">
                        <h5><b>사랑의 불시착</b></h5>
                        <p>
                            뜻밖의 돌풍은 행운일까, 불운일까. 패러글라이딩 사고로 북한에 불시착한 재벌 딸. <br/>
                            그곳에서 깐깐한 북한군 장교를 만난다. 이 와중에 피어오르는 낯선 감정은 뭐지?
                        </p>
                    </div>
                </a>
            </div>
            <div class="carousel-item position-relative" data-bs-interval="6000">
                <span class="gradient position-absolute"></span>
                <img src="./image/RebornRich.jpg" class="d-block w-100" alt="RebornRich.jpg">
                <a href="https://www.netflix.com/kr/title/81633267">
                    <div class="carousel-caption d-none d-md-block">
                        <h5><b>재벌집 막내아들</b></h5>
                        <p>
                            재벌가의 온갖 비리를 처리하다 죽은 비서. <br/>
                            전생의 기억을 모두 간직한 채, 그 집의 막내아들로 태어난다.
                        </p>
                    </div>
                </a>
            </div>
            <div class="carousel-item position-relative" data-bs-interval="6000">
                <span class="gradient position-absolute"></span>
                <img src="./image/DecisiontoLeave.jpg" class="d-block w-100" alt="DecisiontoLeave.jpg">
                <a href="https://www.netflix.com/kr/title/81646755">
                    <div class="carousel-caption d-none d-md-block">
                        <h5><b>헤어질 결심</b></h5>
                        <p>진심을 숨기는 용의자, 용의자에게 의심과 관심을 동시에 느끼는 형사, <br/> 그들의 헤어질 결심.</p>
                    </div>
                </a>
            </div>
            <div class="carousel-item position-relative" data-bs-interval="6000">
                <span class="gradient position-absolute"></span>
                <img src="./image/BirdBox.jpg" class="d-block w-100" alt="BirdBox.jpg">
                <a href="https://www.netflix.com/kr/title/80196789">
                    <div class="carousel-caption d-none d-md-block">
                        <h5><b>버드 박스</b></h5>
                        <p>
                            세상이 뒤집힌 지 5년. 용케 살아남은 여자와 그녀의 아이들이 또다시 위기에 처한다. <br/>
                            안전한 곳을 향해, 그들은 필사적인 모험을 감행한다.
                        </p>
                    </div>
                </a>
            </div>
            <div class="carousel-item position-relative">
                <span class="gradient position-absolute"></span>
                <img src="./image/TheGlory.jpg" class="d-block w-100" alt="TheGlory.jpg">
                <a href="https://www.netflix.com/kr/title/81519223">
                    <div class="carousel-caption d-none d-md-block">
                        <h5><b>더 글로리</b></h5>
                        <p>
                            고등학교 시절, 끔찍한 괴롭힘에 시달렸던 여자. <br/>
                            많은 시간이 흐른 후, 가해자들을 응징하기 위해 그녀가 치밀한 복수를 감행한다.
                        </p>
                    </div>
                </a>
            </div>
        </div>
        <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
        </button>
    </div>
    
    <div id="footer" class="container-fluid">
        <p class="h3 text-light"><b>지금 떠오르는 콘텐츠</b></p>
        <div id="first-col" class="row row-cols-1 row-cols-sm-2 row-cols-md-4">
            <div class="col">
                <img src="./image/img_gall_thum1.jpg" id="thum1" class="img-fluid" alt="thum1.jpg">
                <script>
                    document.getElementById("thum1").addEventListener("click", function() {
                        window.location.href = "https://www.netflix.com/kr/title/80223989";
                    });
                </script>
            </div>
            <div class="col">
                <img src="./image/img_gall_thum2.jpg" id="thum2"class="img-fluid" alt="thum2.jpg">
                <script>
                    document.getElementById("thum2").addEventListener("click", function() {
                        window.location.href = "https://www.netflix.com/kr/title/81277950";
                    });
                </script>
            </div>
            <div class="col">
                <img src="./image/img_gall_thum3.jpg" id="thum3"class="img-fluid" alt="thum3.jpg">
                <script>
                    document.getElementById("thum3").addEventListener("click", function() {
                        window.location.href = "https://www.netflix.com/kr/title/81406219";
                    });
                </script>
            </div>
            <div class="col">
                <img src="./image/img_gall_thum4.jpg" id="thum4"class="img-fluid" alt="thum4.jpg">
                <script>
                    document.getElementById("thum4").addEventListener("click", function() {
                        window.location.href = "https://www.netflix.com/kr/title/80218885";
                    });
                </script>
            </div>
        </div>
        <div class="row row-cols-1 row-cols-sm-2 row-cols-md-4">
            <div class="col">
                <img src="./image/img_gall_thum5.jpg" id="thum5"class="img-fluid" alt="thum5.jpg">
                <script>
                    document.getElementById("thum5").addEventListener("click", function() {
                        window.location.href = "https://www.netflix.com/kr/title/80133311";
                    });
                </script>
            </div>
            <div class="col">
                <img src="./image/img_gall_thum6.jpg" id="thum6"class="img-fluid" alt="thum6.jpg">
                <script>
                    document.getElementById("thum6").addEventListener("click", function() {
                        window.location.href = "https://www.netflix.com/kr/title/81312802";
                    });
                </script>
            </div>
            <div class="col">
                <img src="./image/img_gall_thum7.jpg" id="thum7"class="img-fluid" alt="thum7.jpg">
                <script>
                    document.getElementById("thum7").addEventListener("click", function() {
                        window.location.href = "https://www.netflix.com/kr/title/80194387";
                    });
                </script>
            </div>
            <div class="col">
                <img src="./image/img_gall_thum8.jpg" id="thum8"class="img-fluid" alt="thum8.jpg">
                <script>
                    document.getElementById("thum8").addEventListener("click", function() {
                        window.location.href = "https://www.netflix.com/kr/title/81442115";
                    });
                </script>
            </div>
        </div>
    </div>
</body>
</html>
```

### 1. 

### 2. 


### 3. 



## 추가하고싶은기능
- 
