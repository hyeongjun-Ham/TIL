문자열 처리를 위해 JDK 에서 제공하는 String 클래스가 있습니다.
String 클래스에서는 여러 유용한 기능을 사용할 수 있는 함수를 제공합니다.

```java
public class String_toCaseTest {
 
    public static void main(String[] args) {
        // TODO Auto-generated method stub
        String str = "Test File.)";
        
        String substr1 = str.toLowerCase();
        String substr2 = str.toUpperCase();
        
        System.out.println(substr1); //test file.
        System.out.println(substr2); //TEST FILE.
    }
}
```
