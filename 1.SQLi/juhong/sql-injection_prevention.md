# SQL Injection 을 막는 법

1. 매개 변수화된 쿼리 사용
    1. ORM은 쿼리를 자동으로 생성하고 실행할 때 매개 변수화된 쿼리를 사용 -> 입력 값을 직접 쿼리에 삽입하는 대신, 매개 변수로 처리하여 쿼리를 안전하게 실행 -> 사용자 입력이 직접 쿼리에 포함되지 않으므로 SQL 인젝션을 방지할 수 있다.
2. 입력 값의 자동 이스케이프(Escape) 처리
	1. ORM은 입력 값에 대해 자동으로 이스케이프(Escape) 처리를 수행(이스케이프 처리는 입력 값 중에서 SQL 문법에 영향을 미칠 수 있는 특수 문자를 변환하여 SQL 인젝션을 방지) ORM은 이러한 이스케이프 처리를 자동으로 처리하여 개발자가 별도로 처리할 필요가 없다.
3. ORM의 보안 기능 활용
	1. 대부분의 ORM 프레임워크는 보안 관련 기능을 제공 -> 예를 들어, Hibernate는 입력 값 유효성 검사, 쿼리 로깅, 필터링 및 검증, 트랜잭션 관리 등의 보안 기능을 지원 -> 개발자는 ORM의 보안 기능을 활용하여 SQL Injection 을 방지할 수 있다.