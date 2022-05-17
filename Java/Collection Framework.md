# 컬렉션 프레임웤 개요
![개요](https://prashantgaurav1.files.wordpress.com/2013/12/java-util-collection.gif)
참고자료 : https://opentutorials.org/module/516/6446

## ArrayList :
참고자료 : https://junjangsee.github.io/2019/07/25/java/arraylist-Method/

## HashSet :
참고자료 : https://staticclass.tistory.com/104


### .iterator();
> 메소드 iterator는 인터페이스 Collection에 정의되어 있다.<br>
> 따라서 Collection을 구현하고 있는 모든 컬렉션즈 프레임웍크는 이 메소드를 구현하고 있음을 보증한다.<br>
> 메소드 iterator의 호출 결과는 인터페이스 iterator를 구현한 객체를 리턴한다.<br>
> 인터페이스 iterator는 아래 3개의 메소드를 구현하도록 강제하고 있는데 각각의 역할은 아래와 같다.

- hasNext
> 반복할 데이터가 더 있으면 true, 더 이상 반복할 데이터가 없다면 false를 리턴한다.
- next
> hasNext가 true라는 것은 next가 리턴할 데이터가 존재한다는 의미다. 
- 이러한 기능을 조합하면 for 문을 이용하는 것과 동일하게 데이터를 순차적으로 처리할 수 있다.
```java
Iterator ai = al.iterator();
while(ai.hasNext()){
    System.out.println(ai.next());
}
```
