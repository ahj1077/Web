# UUID(Universally unique identifier)  

- 범용 고유 식별자로, 128bit의 식별자 (xxxxxxxx-xxxx-Mxxx-Nxxx-xxxxxxxxxxxx, 8-4-4-4-12)  

- 테이블의 식별자로 UUID를 사용하는 경우, 추후 테이블끼리의 통합할 때 식별자가 중복되지 않는다는 장점이 있음  

- 식별자가 중복이 될 확률이 0은 아니지만 무시할 수 있을 정도로 고유성을 보장한다.    

-  시간 흐름에 따른 순차성을 없기때문에, 시퀀스 기반의 순차성이 필요한 경우 사용할 수 없다.  
  
  
### java.util.UUID 클래스 예제

```

import java.util.UUID; 

public class UUIDTest {

    public static void main(String[] args) {

        UUID uuid1 = UUID.randomUUID();
        UUID uuid2 = UUID.randomUUID();

        System.out.println("UUID 1: " + uuid1.toString()); // 8-4-4-4-12 문자열로 출력됨
        System.out.println("UUID 2: " + uuid2.toString());
    }

}

```
