<!-- # 날짜

### 배운 것
1.

#### 다음 날 할 것
> - -->

# 220509
항해99 첫 날 처음에 갈피를 못 잡아서 많이 헤맸다.<br>
그래서 늦게 잔다.

### 배운 것
1. TIL 길잡이질문
   * 내가 이걸 배워서 어디다 써먹지?<br>
   * 어떤 문제를 해결할 수 있지?<br>
   * 내가 이걸 하면 뭐가 달라지지?<br>
   * 내가 지금 하려는게 중요한가?<br>
   * http://agile.egloos.com/5838463?fbclid=IwAR1D7uMJ2eueKeTsyX8OcM7JoiZLSZrilA5Q6UkVAlAQ1wvDeyAqtO9SzZM<br>
 
2. TSTTCPW : What's The Simplest Thing That Could Possibly Work?<br>

3. 내 경험에서 배우는 것 내가 잘하는 것을 활용했는지?<br>

4. Jinja2 강의 들음 : 대충 어떻게 해야하는지 알겠음
#### 다음 날 할 것
> - 내일 Jinja2로 서버연결, 및 저장수행 해야함<br>
> - 추가로 좋아요,싫어요 버튼 공부 및 구현<br>
> - 시간돼면 로그인,회원가입 페이지도 공부

# 220510
항해 99 둘째 날 갈피 잡고 열심히 함<br>
전 날 해야할일 다함
### 배운 것
1. 코딩 할 때 괄호 하나하나가 소중하다.

#### 다음 날 할 것
> - 좋아요 버튼 jinja로 구현이 가능한가
> - jinja와 ajax 섞어서 쓸 수 없어보이는데 가능한가 알아보기
> - 시간되면 git md사용법 및 git공부

# 220511

### 배운 것
1. Python 3 부터 모든 문자열은 유니코드 객체 decode()에 있으므로 str 객체의 속성을 직접 사용할 수 없다.<br>
> 파이썬에서 인코딩과 디코딩이 무엇인지 이해합시다.<br>
> Encoding - 객체 로 변환하는 str과정bytes 디코딩 -bytes 객체를 다음으로 변환하는 과정str 따라서 AttributeError: 'str' 개체에 'decode' 속성이 없으면 문자열 개체가 이미 유니코드 형식임을 의미합니다.<br>
> 이미 디코딩된 객체에는 decode() 메서드를 적용할 수 없습니다.
AttributeError: 'str' 개체에는decode() 이미 유니코드 형식인 문자열 개체에 메서드를 사용하는 경우 'decode' 속성 이 없습니다.<br>
Python 3부터 모든 문자열은 유니코드 형식이므로 decode()AttributeError를 해결하기 위해 유니코드 문자열에 적용해서는 안 됩니다.

2. 빅 오류! num로 게시물을 게시하다보니 삭제 이후 num이 중복되어 게시글에 붙음
> db 데이터 역으로 정렬해서 가장 최신거 하나 뽑아냄<br>
> 처음 데이터 없으면 count= 0 으로 넣어서 오류없앰<br>
```python
movie_list = list(db.posts.find({}, {"_id": False}).sort("num", -1).limit(1))
if movie_list == []: count = 0
else: count = movie_list[0]["num"] + 1
```
3. 부트스트랩 카드 크기 조절 실패 : 안의 내용도 고정 or 밖의 크기 조절 안됨

#### 다음 날 할 것
> - 

# 220212

### 배운 것
1.JWT<br>
* **JWT의 장점<br>**
  - JWT 의 주요한 이점은 사용자 인증에 필요한 모든 정보는 토큰 자체에 포함하기 때문에 별도의 인증 저장소가 필요 없습니다.<br>
  - 쿠키를 전달하지 않아도 되므로 쿠키를 사용함으로써 발생하는 취약점이 사라집니다.<br> 
  - URL 파라미터와 헤더로 사용<br> 
  - 트래픽 대한 부담이 낮음<br> 
  - REST 서비스로 제공 가능
 
* **JWT의 단점**
  - Self-contained: 토큰 자체에 정보를 담고 있으므로 양날의 검이 될 수 있습니다.<br>
  - 토큰 길이: 토큰의 페이로드(Payload)에 3종류의 클레임을 저장하기 때문에, 정보가 많아질수록 토큰의 길이가 늘어나 네트워크에 부하를 줄 수 있습니다.<br>
  - Payload 인코딩: 페이로드(Payload) 자체는 암호화 된 것이 아니라, BASE64로 인코딩 된 것입니다.<br>
  - 중간에 Payload를 탈취하여 디코딩하면 데이터를 볼 수 있으므로, JWE로 암호화하거나 Payload에 중요 데이터를 넣지 않아야 합니다.<br>
  - Stateless: JWT는 상태를 저장하지 않기 때문에 한번 만들어지면 제어가 불가능합니다. 즉, 토큰을 임의로 삭제하는 것이 불가능하므로 토큰 만료 시간을 꼭 넣어주어야 합니다.<br>
  - Tore Token: 토큰은 클라이언트 측에서 관리해야 하기 때문에, 토큰을 저장해야 합니다.<br>
> 참고자료 : https://gorokke.tistory.com/181

2. 쿠키와 세션<br>
  - 토큰은 일단 세션보다 훨씬 간편한다.
  - 세션처럼 별도의 저장소 관리가 필요하지 않고 토큰을 발급 후 클라이언트에게 전송 후 검증하는 과정만 있으면 된다.
  - 그러나 발급된 JWT는 삭제가 불가능하다.
  - 세션 같은 경우에는 악의정으로 사용된다면 해당 세션을 삭제하면 된다.
  - 토큰은 탈취당하게 되면 유효 시간이 종료되기 전까지는 탈취자가 얼마든지 악의적으로 사용이 가능하다.

> 참고자료 : https://interconnection.tistory.com/74#:~:text=%EB%B3%B4%EC%95%88%2C%20%EC%BF%A0%ED%82%A4%EB%8A%94%20%ED%81%B4%EB%9D%BC%EC%9D%B4%EC%96%B8%ED%8A%B8%20%EB%A1%9C%EC%BB%AC,%EB%B9%84%EA%B5%90%EC%A0%81%20%EB%B3%B4%EC%95%88%EC%84%B1%EC%9D%B4%20%EC%A2%8B%EC%8A%B5%EB%8B%88%EB%8B%A4.

3. 서버 사이드 렌더링
  - 단어 뜻처럼 페이지 띄우고 바뀔일이 없는 것들은 jinja2로 서버사이드 렌더링이 훨씬 좋다.

4. db 아이디 파싱 라이브러리 찾다가 본 것
> 참고자료 : https://www.fun-coding.org/mongodb_basic5.html

5. guard causes -> if문 복잡할 경우 부정을 붙여서 더 가독성이 좋게 만든다.

6. 구글링 잘하는 방법
> 참고자료 : https://makemoneyskills.com/googling-31-tips/

# 220513

### 배운 것
1. 자바 언어에 대해 접했다.

#### 다음 날 할 것
> - 객체, 클래스 수업듣기

# 220514

### 배운 것
1.인텔리제이 단축키 틈틈히보기
> 참고자료 : https://computer-science-student.tistory.com/298


#### 다음 날 할 것
> - 추상클래스, 인터페이스, 객체, 클래스, 다형성(인터페이스)<br>
> - 배열, 리스트 , Stream , Math<br>
> - Math 공부

# 날짜 220515

### 배운 것
1. interface는 method를 강제한다
2. abstract는 상속을 강제한다.
3. overloading은 같은이름에 다른 동작 방법일 때 사용 가능하다.
4. Math는 클래스

#### 다음 날 할 것
> - Spring과제 배운 개념토대로 다시 짜보기.
> - OOP(Object Oriented Programming : 객체지향 프로그래밍)에 대해서는 계속 공부(안 보고도 활용할 수 있도록)
> - 시간남으면 Stream공부
