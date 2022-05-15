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
