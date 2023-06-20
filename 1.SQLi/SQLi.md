# 1. SQL injection

# SQL Injection

SQL Injection은 웹 애플리케이션에서 가장 일반적인 보안 취약점 중 하나입니다. 이 취약점은 악의적인 사용자가 웹사이트의 데이터베이스에 액세스할 수 있도록 허용합니다. SQL Injection을 이용하면 공격자는 데이터베이스에서 데이터를 수정, 삭제 또는 검색할 수 있습니다.

## SQL Injection 개념

SQL Injection은 웹 애플리케이션에서 사용되는 데이터베이스 질의 언어(SQL)를 이용하여 공격하는 기술입니다. 악의적인 사용자는 입력 폼 등을 이용하여 SQL 쿼리를 조작하여 데이터베이스에 액세스합니다.

예를 들어, 로그인 폼에서 아이디와 비밀번호를 입력하는 경우, 아래와 같은 SQL 쿼리문이 실행됩니다.

```
SELECT * FROM users WHERE username='input_username' AND password='input_password';

```

하지만, 공격자는 입력 폼에 아래와 같은 데이터를 입력하면 SQL Injection 공격이 가능합니다.

```
input_username: admin'; --
input_password: anything

```

위의 입력값으로 SQL 쿼리문이 아래와 같이 변조됩니다.

```
**SELECT * FROM users WHERE username='admin'; --**' AND password='anything';

```

위와 같이 SQL Injection을 이용하면, 공격자는 로그인을 우회하거나 데이터베이스에서 데이터를 삭제/수정/조회할 수 있습니다.

## SQL Injection 공격 기법

SQL Injection 공격 기법은 크게 Error-based, Union-based, Blind-based 등으로 나눌 수 있습니다. 각각의 공격 기법은 데이터베이스에 대한 정보를 얻거나 데이터베이스에서 데이터를 추출하기 위한 다양한 방법을 제공합니다.

### Error-based SQL Injection

Error-based SQL Injection은 데이터베이스에서 에러 메시지를 이용하여 데이터베이스에 대한 정보를 추출하는 방법입니다. 공격자는 입력 폼에 다양한 값을 입력하여 에러 메시지를 출력하도록 유도합니다.

[SQL Injection 취약점(2)_Error Based Injection](https://byounghee.tistory.com/148)

### Union-based SQL Injection

Union-based SQL Injection은 UNION 연산자를 이용하여 데이터베이스에서 다른 테이블의 정보를 가져오는 방법입니다. 공격자는 입력 폼에 UNION 연산자를 이용하여 데이터베이스에서 필요한 정보를 추출합니다.

[[Web 취약점] Injection 공격 방법(SQL Injection 2 : union based injection)](https://c-i-s.tistory.com/entry/Web-취약점-Injection-공격-방법SQL-Injection-2-union-based-injection)

### Blind SQL Injection

Blind SQL Injection은 데이터베이스에서 결과를 반환하지 않는 쿼리를 이용하여 데이터베이스에 대한 정보를 추출하는 방법입니다. 공격자는 입력 폼에 조건을 이용하여 데이터베이스에서 정보를 추출합니다.

[SQL Injection : Blind SQL Injection](https://hanuscrypto.tistory.com/entry/SQL-Injection-Blind-SQL-Injection)

# 과제

1. 각자의 프로그래밍 언어에서 SQL injection 막는 법 정리해서 발표

