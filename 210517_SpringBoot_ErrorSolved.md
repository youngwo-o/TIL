# Error

## 1. java.lang.NoClassDefFoundError: javax/xml/bind/DatatypeConverter

Java 11 버전 사용 중, jwt 인증 구현 도중 위 에러 발생

👉🏻 JAXB API는 Java EE API로 간주되므로, Java 11에서는 JDK에서 제외됨
 
　　`implementation 'javax.xml.bind:jaxb-api:2.1'`
 
　　dependencies에 추가해서 해결

## 2. There is no PasswordEncoder mapped for the id "null"

Spring Security 사용해서 로그인 및 인증 구현 도중 위 에러 발생

👉🏻 Spring Security 버전이 올라가면서 PasswordEncoder가 변경됨

```java
if(!passwordEncoder.matches(password, "{noop}" + user.getPassword()))
            throw new IllegalArgumentException("잘못된 비밀번호입니다.");
```

　　user의 password 값에 {noop} 를 붙여서 해결
