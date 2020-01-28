# node-multer

사용자가 업로드한 파일을 받아서 저장하는 방법<br>

+ 사용자가 앱에게 전달하는 정보는 크게 텍스트와 파일 2가지로 나눌 수 있다.<br>

+ 사용자가 파일을 앱에게 전달하는 방법<br>

+ 동작 개요<br>
  + 파일 선택 form<br>
  + 파일 선택 후 submit 버튼을 눌러 파일 전송<br>
  + 로프 디렉토리 내 uploads 폴더에 전송된 파일이 저장<br>
  + 전송된 파일명을 화면에 표시<br>
+ express는 사용자가 업로드한 파일을 받아서 저장하는 기본 기능을 제공하지 않는다<br>
+ 따라서 모듈을 설치해서 (ex.multer) 사용자가 전송한 파일을 처리하는 작업을 해야한다<br>

파일 업로드 양식 (form)<br>

라우팅 1 - / upload path의 get 방식<br>

+ http://localhost:3000/upload path 로 접속하면 업로드 화면을 보여주도록 라우터 연결<br>

// 업로그 - 파일 업로드 풀<br>
  app.get('/upload', function(req, res){<br>
    res.render('upload');<br>
  });<br>
  <br>
템플릿 파일<br>
+ 탬플릿 파일 저장 경로인 /views_file/ 폴더 내의 업로드 화면 구현을 위한 탬플릿 파일 작성(upload.jade)<br>
+ form 의 type을 enctype="multipart/form-data" 로 설정해야 사용자가 전송한 파일을 서버로 전송할 수 있다<br>
+ 업로드폼 탬플릿 파일 (upload.jade) 코드 예시<br>

  doctype html<br>
  html<br>
    head<br>
      meta(charset='utf-8')<br>
    body<br>
      form(action='upload' method='post' enctype="multipart/form-data")<br>
        input(type='file' name='userfile')<br>
        input(type='submit')<br>
        
      
