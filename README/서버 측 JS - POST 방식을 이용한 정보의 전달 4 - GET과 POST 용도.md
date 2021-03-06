# 서버 측 JS - Express, POST 방식을 이용한 정보의 전달 4 : GET과 POST 용도

- #### GET

  > GET방식은, 하나의 라우터가 GET방식을 통해서 전송된 query string에 따라서 다른 데이터를 보여줄 수 있다

  - 링크를 클릭했을 때, 원하는 것은 주소가 바뀌는 것
  - 누군가에게 링크를 공유했을 때 자신이 보는 정보를 그대로 보여주고 싶다
    URL에 모든 정보를 담고 있어야 함

- #### POST

  > URL 에 데이터가 포함되지 않고 조용히 암시적으로 전송되기 때문에 불필요하게 정보가 노출되지 않는다 라는 장점, 용량이 큰 데이터를 전송하는데도 제한이 없다는 그러한 장점을 갖는다

  - 로그인 했을 때 ID와 PA가 URL에 표시되므로, 보안적으로 GET보다 그나마 나음
  - POST가 GET방식보다 보안적으로 안전하다 라는 느낌은 아님 ! (HTTPS, SSL)

- #### URL을 통해서 어떤 정보를 전달한다

  - 굉장히 긴 글을 URL을 통해서 query string에 담아 GET 방식을 사용한다면 브라우저 자체에서 데이터를 버려버릴 수 있음
  - 제목과 본문일 경우 데이터가 없어질 수 있으므로 POST 방식을 사용하는 것이 맞음

- #### 결론

  > GET방식은 Express가 기본적으로 제공하지만 POST방식은 Express가 기본적으로 제공하는 방식이 아니기 때문에, bodyParser 라는 middleware를 Load하고 Use를 통해 붙이고, 사용자의 요청을 중간에서 function의 req 에 body 라고 하는 객체를 추가시켜주는 역할을 한다.

  > body라는 객체는 form으로 전송될 때, name의 값으로 전달된 데이터의 이름이 body 객체의 property 로 들어오기 때문에 form의 이름을 통해서 사용자가 전달한 데이터를 받을 수 있다.


- ### 서버 측 JS - 팁 [Supervisor](https://www.npmjs.com/package/supervisor)

  > 자신의 삶의 맥락에서(일의 맥락에서) 필요하지 않은 도구를 처음부터 다루는 것은 그 도구와 멀어지는 길이 될 수 있다고 생각합니다
  >
  > 적재적소에 도구가 있을 수 밖에 없는 이유가 성숙된 순간에 도구를 만나면 눈이 맞는 것 처럼 :)

  ```
  supervisor app.js
  ```

  - app.js 가 변경되었음을 감지(해당 기능을 Watcher라고 표현)하고 서버를 다시 재시작 해주는 Module
  - **supervisor을 사용하는 방법에는 여러가지가 있고, 기본적으로 되지 않을 때 document 를 항상 참고할 것!**
    **예제들을 보면서 자기에게 어떻게 적용하는지 궁리해서 스스로 알아낼 수 있어야 함 !**