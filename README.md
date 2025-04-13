# sq-common-resp-excp

## 소개
**sq-common-resp-excp**는 스프링(Spring) 프로젝트에서 공통적으로 사용되는 응답 클래스와 공통 예외 클래스를 정의한 라이브러리입니다.  
이 라이브러리는 일관된 응답 포맷과 예외 처리를 제공함으로써 개발 생산성을 높이고, 코드의 재사용성을 향상시키는 데 목적이 있습니다.

---

## 주요 기능
- **공통 응답 클래스**
  - API 응답에 사용되는 표준화된 응답 객체 제공
  - 응답 상태, 메시지, 데이터 필드 포함
- **공통 예외 클래스**
  - 자주 사용되는 커스텀 예외 클래스 정의
  - 상태 코드와 메시지를 활용하여 예외 상황 처리 간소화

---

## 설치 방법
이 프로젝트는 Gradle을 통해 설치할 수 있습니다.  
`build.gradle`에 아래 코드를 추가하여 의존성을 추가하세요.

```gradle
dependencies {
    implementation 'com.slicequeue:sq-common-resp-excp:1.0.0'
}
```

*버전 번호는 실제 릴리스된 버전에 맞게 수정하세요.*

---

## 사용 방법
### 1. 공통 응답 클래스 사용
API 응답 데이터를 표준화된 형식으로 반환하고 싶을 때, 아래 예제를 참고하세요.

```java
import com.slicequeue.common.response.CommonResponse;

@RestController
public class ExampleController {

    @GetMapping("/example")
    public CommonResponse<String> exampleEndpoint() {
        return CommonResponse.success("Hello, World!");
    }
}
```

### 2. 공통 예외 클래스 사용
커스텀 예외를 활용하여 비즈니스 로직에서 발생한 에러를 처리할 수 있습니다.

```java
import com.slicequeue.common.exception.BusinessException;
import com.slicequeue.common.response.ErrorCode;

@Service
public class ExampleService {

    public void process() {
        throw new BusinessException(ErrorCode.INVALID_INPUT, "Invalid input provided.");
    }
}
```

---

## 기여 방법
이 프로젝트에 기여하고 싶다면, 리포지토리를 포크(Fork)한 후 Pull Request(PR)를 올려주세요.  
기여 가이드라인을 준수하여 PR을 작성해 주시기 바랍니다.

---

## 라이선스
이 프로젝트는 오픈소스 라이선스로 제공되며, 누구나 자유롭게 사용, 수정 및 배포할 수 있습니다.
