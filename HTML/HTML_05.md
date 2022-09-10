# HTML

## 8. Embedded content

### `<iframe>`

```html
<iframe width="1280" height="720" src="https://www.youtube.com/embed/-iuX3r8PSzU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
</iframe>
```

- 현재 HTML 문서에 다른 문서를 포함시킬 때 사용한다.
- 보통 유튜브 영상을 불러올 때 사용한다.
- `allow` : `<iframe>`에서 허용할 기능들을 지정한다.

<br>

**유튜브 지원 매개변수**

쿼리스트링 뒤에 `&` 으로 연결하여 작성해준다.

```html
<iframe id="ytplayer" type="text/html" width="640" height="360"
  src="https://www.youtube.com/embed/M7lc1UVf-VE?autoplay=1&mute=1&controls=0"
  frameborder="0"></iframe>
```

- `autoplay=1` 과 `mute=1` : 두 옵션은 세트로 많이 쓰인다. 크롬 정책으로 인해 유튜브 동영상을 자동 재생하려면 음소거 된 상태에서만 자동 재생이 가능하기 때문이다.
- `controls=0` : 유튜브에서 기본으로 제공하는 컨트롤 바를 없애는 옵션이다.

🔗유튜브 지원 매개변수 추가로 알아보기<br>
[https://developers.google.com/youtube/player_parameters?hl=ko](https://developers.google.com/youtube/player_parameters?hl=ko)

<br>

### `<audio>`

```html
<audio src="폴더/파일명" controls autoplay loop ></audio>
```

- 음악 파일을 재생하기 위한 태그
- `controls` 속성을 넣지 않으면 컨트롤 바가 없어지는데, 이럴 때는 사용자가 정지 또는 재생을 시킬 수 있도록 버튼을 따로 만들어 주어야 한다.

<br>

### `<video>`

- 동영상 파일을 재생하기 위한 태그
- 트래픽을 많이 잡아먹으므로 직접 동영상을 올리는 대신 `<iframe>` 유튜브를 활용하자.

<br>

## 9. Forms
### `<form>` 동작 방식

1. 웹 페이지에 있는 `<form>` 에 데이터를 입력
2. 폼 데이터를 웹 서버로 전송
3. 웹 서버는 받은 폼 데이터를 처리하기 위해 App을 호출
4. 필요에 따라 App은 DB로 데이터를 전송
5. DB에서 CRUD(Creat, Read, Update, Delete) 작업이 일어나고 작업 결과를 APP으로, WEB으로 전송
6. 웹 서버는 받은 결과를 브라우저에 보냄
7. 브라우저는 받은 페이지를 렌더링하여 보여줌


- Server : (서빙하는 역할) 요청을 받으면 요청한 정보를 제공하는 컴퓨터 혹은 프로그램. 대부분 IP와 연결되어 있음.
- Web Server : 대부분 정적 파일을 서빙 (PHP와 같은 프로그래밍 언어도 처리하긴 함)
- App Server : (두뇌 역할) 동적 콘텐츠를 서빙
- DB : 데이터 저장소. 이미지 같은 경우에는 이미지 경로만 저장한다.

<br>

### `<form>`의 속성

- `action` : (어디로 보낼까) 속성의 값은 전송 시 form 에 있는 정보를 수신할 서버 페이지의 URL이다.
- `method` : (어떻게 보낼까) 속성의 값은 `get` 과 `post` 가 있다.
    - get : 값이 URL의 뒤에 추가 된다. 게시글의 번호를 쿼리 스트링으로 함께 공유할 수가 있어서 링크를 공유하는 경우에 활용할 수 있다. 웹 서버에 데이터를 요청 할 때 사용한다.
    - post :  파일을 올리는 경우, 민감한 데이터를 전송하는 경우, 전송할 데이터 길이가 매우 긴 경우에 사용한다.

>💡 쿼리 스트링 (Query String)<br>
>URL 주소에 데이터를 넘길 때 `?` 연산자 뒤에 변수 이름과 그 값을 넣어서 보내는 형식
