1. **스프링 프레임워크란 무엇인가요?**
- 자바 엔터프라이즈 애플리케이션 개발을 위한 가장 널리 사용되는 프레임워크입니다.
- 경량화, 제어 역전(IOC), 관점 지향 프로그래밍(AOP), 트랜잭션 관리 등의 기능을 제공합니다.
1. **스프링을 사용하면 어떤 장점이 있나요?**
- 경량화로 프레임워크로 인한 개발 오버헤드가 적습니다.
- IoC 컨테이너가 객체 간 의존성 주입을 관리해줍니다.
- AOP로 핵심 로직과 시스템 서비스를 분리할 수 있습니다.
1. **대표적인 스프링 하위 프로젝트들은 무엇인가요?**
- 스프링 코어: IoC/DI 등 프레임워크 핵심 기능 제공
- 스프링 JDBC: JDBC 코딩 없이 DB 연동 기능
- 스프링 ORM: JPA, Hibernate 등의 ORM 연동 계층
- 스프링 웹: 파일 업로드, 서블릿 리스너 등 웹 관련 기능
- 스프링 MVC: MVC 아키텍처 웹 개발 모듈
- 스프링 AOP: AOP 구현 및 메소드 인터셉터 정의
1. **의존성 주입(DI)이란 무엇인가요?**
- 객체를 직접 생성하지 않고, 생성 방법을 기술하면 IoC 컨테이너가 필요할 때 인스턴스화해서 주입하는 개념입니다.
1. **스프링에서 빈을 주입하는 방식에는 어떤 것들이 있나요?**
- Setter 주입
- 생성자 주입
- 필드 주입
- XML 또는 애노테이션으로 설정 가능
1. **빈 주입 방식 중 권장되는 방식은 무엇이고 그 이유는 무엇인가요?**
- 필수 의존성은 생성자 주입, 선택적 의존성은 Setter 주입을 권장합니다.
- 생성자 주입을 사용하면 immutable 필드에 값 주입이 가능하고 테스트가 용이해집니다.
1. **BeanFactory와 ApplicationContext의 차이점은 무엇인가요?**
- BeanFactory는 빈 인스턴스를 제공하고 관리하는 컨테이너 인터페이스입니다. getBean()이 호출될 때 lazy하게 빈을 생성합니다.
- ApplicationContext는 BeanFactory를 상속하면서 애플리케이션의 모든 정보, 메타데이터, 빈을 담고 있는 컨테이너 인터페이스입니다. 기본적으로 애플리케이션 구동 시점에 eager하게 빈을 생성합니다.
1. **스프링 빈이란 무엇인가요?**
- 스프링 IoC 컨테이너에 의해 인스턴스화, 관리되는 자바 오브젝트를 말합니다.
1. **스프링 프레임워크에서 빈의 기본 스코프는 무엇인가요?**
- 별도 설정이 없다면 스프링 빈은 singleton 스코프로 생성됩니다.
1. **빈의 스코프는 어떻게 지정할 수 있나요?**
- @Scope 애노테이션이나 XML 설정 파일에서 "scope" 속성을 사용해 지정할 수 있습니다.
- 스프링에서 지원하는 빈 스코프에는 다음과 같은 것들이 있습니다.
    - singleton
    - prototype
    - request
    - session
    - global-session
1. **싱글톤 빈은 스레드에 안전한가요?**
- 아니오. 싱글톤 빈 자체는 스레드 세이프하지 않습니다.
- 스레드 안전성은 빈의 실행 방식에 달려 있고, 싱글톤은 생성 방식에 초점을 둔 디자인 패턴입니다.
- 빈의 구현 코드에 따라 스레드 안전성이 결정됩니다.
1. **스프링 빈의 생명주기는 어떻게 되나요?**
- 빈 정의를 읽고 인스턴스화 → 의존성 주입 → 초기화 콜백 메소드 호출 → 사용 → 소멸 콜백 메소드 호출 → 빈 소멸
- 각 단계별로 초기화 메소드, 소멸 메소드 등을 빈에 적절히 설정해서 사용할 수 있습니다.
1. **스프링 자바 기반 설정이란 무엇인가요?**
- XML 기반 설정의 대안으로, 자바 클래스와 애노테이션을 사용해 설정하는 방식입니다.
- 타입 세이프한 방식으로 스프링 애플리케이션 구성이 가능합니다.
1. **하나의 프로젝트에 여러 개의 스프링 설정 파일을 사용할 수 있나요?**
- 네, 가능합니다. 큰 프로젝트에서는 모듈화와 유지보수성을 위해 여러 개의 설정 파일 사용이 권장됩니다.
- 자바 기반 설정에서는 @Configuration과 @Import 애노테이션을 사용해 여러 설정 클래스를 조합할 수 있습니다.
- XML 기반 설정에서는 <import> 태그를 사용해 여러 XML 파일을 조합할 수 있습니다.
1. **스프링 시큐리티란 무엇인가요?**
- 스프링 기반 애플리케이션의 인증과 권한 부여 등 보안 기능을 담당하는 프레임워크입니다.
- 스프링 시큐리티를 사용하면 인증/인가 관련 표준 로직을 작성하지 않아도 되고, CSRF 공격 등을 방어할 수 있습니다.
- 웹 애플리케이션에 @EnableWebSecurity 애노테이션만 붙여주면 기본적인 웹 보안 기능이 작동합니다.
1. **스프링 부트란 무엇인가요?**
- 스프링 기반 애플리케이션을 빠르게 개발할 수 있게 도와주는 프로젝트입니다.
- 단독 실행 가능한 스프링 애플리케이션을 쉽게 생성할 수 있습니다.
- 내장 서버, 자동 설정, starter 의존성 등으로 최소한의 설정으로 개발을 시작할 수 있습니다.
1. **스프링 프레임워크에서 사용되는 디자인 패턴에는 어떤 것들이 있나요?**
- 싱글톤 패턴: 싱글톤 스코프의 빈
- 팩토리 패턴: BeanFactory 클래스
- 프로토타입 패턴: 프로토타입 스코프의 빈
- 프록시 패턴: 스프링 AOP
- 템플릿 메소드 패턴: JdbcTemplate, HibernateTemplate 등
- 프론트 컨트롤러 패턴: 스프링 MVC의 DispatcherServlet
- 데이터 접근 오브젝트(DAO) 패턴: 스프링 DAO 지원
1. **프로토타입 스코프는 어떻게 동작하나요?**
- 프로토타입 스코프로 정의된 빈은 매번 getBean() 메소드가 호출될 때마다 새로운 오브젝트를 생성해서 반환합니다.
- 이는 기본인 싱글톤 스코프와 대조적입니다. 싱글톤은 IoC 컨테이너당 하나의 오브젝트만 생성합니다.
1. **스프링 빈에서 ServletContext와 ServletConfig 객체는 어떻게 얻나요?**
- 스프링에서 제공하는 Aware 인터페이스들을 구현하는 방법이 있습니다.
- @Autowired 애노테이션을 사용해서 주입받는 방법도 가능합니다.
1. **스프링 MVC의 컨트롤러란 무엇인가요?**
- 스프링 MVC에서 사용자의 요청을 처리하는 컴포넌트입니다.
- @Controller 애노테이션이 붙은 클래스가 컨트롤러의 역할을 합니다.
- 컨트롤러 클래스의 메소드는 @RequestMapping 애노테이션으로 매핑된 특정 URI를 처리합니다.
1. **@RequestMapping 애노테이션은 어떻게 사용하나요?**
- 요청 URL을 컨트롤러의 메소드와 매핑할 때 사용하는 애노테이션입니다.
- URL 패턴 외에도 HTTP 메소드 타입, 헤더, 파라미터 등을 매핑 조건으로 지정 가능합니다.
- @PathVariable을 통해 URL 템플릿 변수를 메소드 파라미터로 받을 수 있습니다.
- @RequestParam을 통해 HTTP 요청 파라미터를 메소드 파라미터로 받을 수 있습니다.
1. **스프링 JDBC의 JdbcTemplate 클래스는 무엇이고 어떻게 사용하나요?**
- 스프링에서 JDBC 프로그래밍을 쉽게 할 수 있도록 제공하는 템플릿 클래스입니다.
- 리소스 생성, 해지 등의 low-level 작업을 대신 처리해줍니다.
- SQLException을 스프링 DataAccessException으로 변환하는 기능도 제공합니다.
- JdbcTemplate을 사용하려면 DataSource를 스프링 설정 파일에 등록해야 합니다.
1. **스프링에서 트랜잭션은 어떻게 사용하고, 어떤 이점이 있나요?**
- 선언적 트랜잭션(@Transactional)과 프로그래밍적 트랜잭션(TransactionTemplate) 두 가지 방식을 제공합니다.
- 선언적 트랜잭션은 코드 침투가 없고 AOP를 사용하기 때문에 권장됩니다.
- 트랜잭션 전파, 격리 수준, 읽기 전용 등을 애노테이션 속성으로 제어할 수 있습니다.
- 트랜잭션 경계를 메소드 단위로 설정할 수 있어서 productivity가 높아집니다.
- 다양한 데이터 접근 기술에 대해 일관된 트랜잭션 제어가 가능합니다.
1. **스프링 DAO란 무엇인가요?**
- Data Access Object의 약자로, 데이터 접근을 추상화한 객체입니다.
- 스프링은 일관성 있는 DAO를 작성할 수 있도록 다양한 기능을 제공합니다.
- 저수준 예외를 스프링의 통일된 예외 체계로 변환해줍니다.
- 템플릿 클래스를 통해 boilerplate 코드를 제거할 수 있습니다.
1. **AOP(Aspect-Oriented Programming)란 무엇인가요?**
- 관점 지향 프로그래밍이라고 하며, 스프링의 핵심 기능 중 하나입니다.
- 여러 객체에 공통으로 적용될 수 있는 기능(cross-cutting concern)을 분리해서 모듈화합니다.
- 주로 로깅, 트랜잭션, 보안 등 인프라 레벨의 공통 기능을 구현하는데 사용합니다.
- AOP를 통해 객체 간 결합도를 낮추고, 코드 재사용성을 높일 수 있습니다.
1. **AOP에서 Aspect, Advice, Pointcut, JoinPoint란 무엇인가요?**
- Aspect: 여러 객체에 공통으로 적용되는 공통 관심사(cross-cutting concern)를 모듈화 한 것입니다. 트랜잭션 관리 등이 대표적입니다.
- Advice: 특정 JoinPoint에서 Aspect에 의해 취해지는 조치입니다. Around, Before, After 등의 타입이 있습니다.
- Pointcut: Advice가 적용될 JoinPoint를 선별하는 조건입니다. 주로 정규 표현식으로 표현합니다.
- JoinPoint: Advice가 적용될 수 있는 위치입니다. 메소드 호출, 예외 발생 등이 있습니다.
1. **AOP의 Weaving이란 무엇인가요?**
- Aspect를 타깃 객체에 적용해서 새로운 프록시 객체를 생성하는 과정을 말합니다.
- 즉, Advice를 핵심 로직 코드에 삽입하는 과정입니다.
- 컴파일타임, 로딩타임, 런타임에 적용할 수 있는데, 스프링 AOP는 런타임 위빙을 사용합니다.
1. **리액티브 프로그래밍이란 무엇인가요?**
- 데이터 흐름과 변경 전파에 중점을 둔 프로그래밍 패러다임입니다.
- 주요 특징으로는 논블로킹(non-blocking), 이벤트 기반(event-driven), 느슨한 결합(loosely coupled), 확장성(scalable) 등이 있습니다.
- Observer 패턴을 확장해서, 데이터 스트림을 비동기적으로 처리합니다.
- 스프링에서는 5.0 버전부터 WebFlux를 통해 리액티브 프로그래밍을 지원하고 있습니다.
1. **스프링 WebFlux란 무엇인가요?**
- 스프링 5.0에서 추가된 리액티브 웹 프레임워크입니다.
- 기존의 스프링 MVC와는 별개의 모듈로서 완전한 논블로킹 방식으로 동작합니다.
- 네티(Netty)를 기반으로 동작하며, 서블릿 컨테이너에서도 동작 가능합니다.
- 함수형 프로그래밍 방식을 지원하며, Mono와 Flux 타입을 사용해 리액티브 데이터 타입을 표현합니다.
1. **Mono와 Flux란 무엇인가요?**
- 스프링 5의 리액티브 프로그래밍에서 사용되는 핵심 객체 타입입니다.
- Mono는 0-1개의 데이터를 발행하는 Reactive Stream 구현체입니다.
- Flux는 0-N개의 데이터를 발행하는 Reactive Stream 구현체입니다.
- 모두 Reactive Stream 표준 인터페이스인 Publisher를 구현하고 있습니다.
1. **WebClient와 WebTestClient는 각각 어떤 용도인가요?**
- WebClient는 스프링 WebFlux에서 제공하는 논블로킹 방식의 리액티브 HTTP 클라이언트입니다.
- HTTP 요청을 비동기적으로 처리하며, Mono나 Flux를 사용해 응답을 받을 수 있습니다.
- WebTestClient는 WebFlux 애플리케이션을 테스트할 때 사용하는 클라이언트입니다.
- 실제 서버를 띄우지 않고도 mock request/response를 사용해 컨트롤러 테스트를 할 수 있습니다.
1. **리액티브 스트림 사용 시 주의할 점은 무엇인가요?**
- 리액티브 프로그래밍은 기존 방식과 사고의 전환이 필요해 진입장벽이 높습니다.
- 리액티브 스트림을 디버깅하기 쉽지 않기 때문에 디버깅 방식에 대한 학습이 필요합니다.
- 전통적인 JDBC 기반 DB 드라이버는 리액티브 방식을 지원하지 않아 사용에 주의가 필요합니다.
1. **스프링 5에서 리액티브 프로그래밍을 지원하기 위해 최소 자바 버전이 올라갔나요?**
- 네, 맞습니다. 스프링 5는 자바 8 이상에서만 동작합니다.
- 자바 8의 람다, Stream API, CompletableFuture 등을 활용하기 위해 최소 사양을 올린 것으로 보입니다.
1. **스프링 5는 자바 9의 모듈 시스템(Jigsaw)을 어떻게 지원하나요?**
- 스프링 5의 프레임워크 라이브러리들은 자바 9 모듈 시스템을 따르도록 변경되었습니다.
- 그래서 필요한 모듈만 선택적으로 가져올 수 있게 되었습니다.
- 하지만 스프링 부트 2.0에서는 아직 자바 9 모듈을 완벽하게 지원하지 않습니다.
1. **스프링 MVC와 WebFlux를 함께 사용할 수 있나요?**
- 스프링 부트에서는 현재 둘 중 하나만 선택해서 사용하는 것을 권장합니다.
- 왜냐하면 둘 다 사용하면 자동 설정이 제대로 동작하지 않기 때문입니다.
- 또한 스프링 MVC는 서블릿 기반인 반면 WebFlux는 네티 기반이라 함께 사용하기에 적절치 않습니다.
