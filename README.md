**BackEnd Developer**

아이디어 : 2023/06/14 ~ 2023/06/21
개발 : 2023/06/24 ~ 2023/07/26

시연 영상 :  [**영상 링크(Link)**](https://drive.google.com/file/d/1edAgBRdS0zu9Th4e02RKy7H0KcSBZPmc/view?usp=drive_link)

pdf : [**자료 링크(Link)**](https://drive.google.com/file/d/1RyeG4yk8vQp_ac_z0vLo-tUskPM_v_HK/view?usp=drive_link)

**Links**

Github : https://github.com/hyowonsong/KT-AIVLE-BigProject

Notion :  [**노션 링크(Link)**](https://www.notion.so/93e4136b98234fcdad12f4c79ea8c63f?pvs=21)

---

## 📜 서비스 내용

![AI 4조 썸네일.jpg](https://prod-files-secure.s3.us-west-2.amazonaws.com/36358b89-fde5-4b16-95d9-7decef74047e/1ea7ef86-7323-49fb-bfcb-332aeb89d86f/AI_4%EC%A1%B0_%EC%8D%B8%EB%84%A4%EC%9D%BC.jpg)

🌱  **관리자 시나리오**

1. 관리자가 영상 업로드를 합니다.
2. 업로드된 영상은 S3 저장소에 저장됩니다.
3. AI 모델이 영상을 분석합니다.
4. OCR과 STT 기술을 이용해 비디오 컨텐츠를 텍스트 데이터로 변환합니다.
5. Chat GPT API를 활용하여 다음 세 가지 작업을 수행합니다:
    - 강의자료 PDF 생성
    - 퀴즈 생성
    - 영상 썸네일 생성

🌱  **유저 시나리오**

1. 사용자가 시스템에 접근합니다.
2. 회원가입 절차를 거칩니다.
3. 메인화면에 접속합니다.
4. 학습 관리 섹션에서 다음 기능들을 이용할 수 있습니다:
    - 강의 목록 확인
    - 강의 화면 시청
    - 강의 자료 PDF 다운로드
    - 퀴즈 참여
    - 학습 평가 확인
    - 강의 집중도 분석

---

## 🚩 프로젝트 배경

- KT Aivle 스쿨을 진행하며 느낀 불편함을 공유한 것이 이 프로젝트의 시작점이 되었습니다.
    - 영상 강의만 있는 경우 학습 자료가 따로 없어 수강하는데 불편함이 있었습니다.
    - 이로 인해, 강의 자료를 자동으로 생성해주는 기능의 필요성을 느꼈습니다.
    - 또한, 실시간 챗봇 기능을 통해 모르는 점을 간단하게 물어볼 수 있으면 좋겠다는 의견이 있었습니다.
- 이러한 서비스를 통해 개인화된 맞춤형 학습 서비스를 제공하고자 합니다.
    - 체계적인 자료 정리 및 복습에 도움을 줄 수 있습니다.
    - 퀴즈를 통해 학습 피드백을 제공할 수 있습니다.
    - 강의 집중도를 파악할 수 있습니다.
- 산업통상자원부 자료에 따르면, 이러닝 수요 시장은 2011년부터 2022년까지 꾸준히 증가해왔으며, 향후 5년간(2022년 기준) 78.9%의 성장 전망이 있어 사업성이 충분하다고 판단됩니다.

---

## 🛠 기술 스택

### 🌟 [**Backend**](https://github.com/AIVLE-School-Third-Big-Project/Team11-Project-back)

- Java, Spring
- AWS (EC2, RDS, S3)
- MySQL
- NGINX

---

## 🖥 개발 내용

저는 Backend와 Front를 담당하였습니다.

백엔드는 **Spring Boot**를 사용하여 **REST API**를 구현하였고,
서버의 경우 **AWS EC2**를 사용하고, **DB**와 **Storage**를 **RDS**와 **S3**로 분리하여 구현했습니다.
DB는 **MySQL**을 사용했고, API 서버는 **NGINX**로 배포하였습니다.

프론트엔드는 **React**를 사용하여 구현했으며, 이를 NGINX를 통해 호스팅했습니다.

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/36358b89-fde5-4b16-95d9-7decef74047e/42bff281-dd77-4082-8248-353954a6f6dc/b5dd09bb-3e5e-43be-8d1b-affb6e1619f5.png)

### ✅ 아키텍처 구성

- Spring Boot 애플리케이션을 [https://allinone-spring.com](https://allinone-spring.com/) 도메인으로 호스팅
- React 애플리케이션을 [https://allinone-flask.com](https://allinone-flask.com/) 도메인으로 호스팅
- 두 애플리케이션 모두 NGINX를 사용하여 리버스 프록시 설정

### ✅ 데이터베이스 및 스토리지

- MySQL을 AWS RDS에서 호스팅하여 데이터 저장
- AWS S3를 사용하여 파일 및 미디어 저장

### ✅ 사용자 인증 및 비밀번호 재설정 기능 구현

✔️ **UserController 클래스**

- 사용자 등록, 로그인, 비밀번호 재설정 관련 엔드포인트를 제공합니다.
- 사용자 등록 시 비밀번호를 암호화하여 저장합니다.
- 로그인 시 이메일과 비밀번호를 검증합니다.
- 비밀번호 재설정 요청 시 토큰을 생성하고 이메일로 재설정 링크를 전송합니다.

✔️ **비밀번호 재설정 프로세스**

- PasswordResetToken 엔티티를 사용하여 비밀번호 재설정 토큰을 관리합니다.
- 토큰 생성 시 24시간의 유효 기간을 설정합니다.
- 이메일을 통해 비밀번호 재설정 링크를 전송합니다.
- 토큰의 유효성을 검증한 후 비밀번호를 변경할 수 있습니다.

✔️ **UserService 클래스**

- 사용자 저장, 비밀번호 재설정 토큰 생성, 이메일 전송 등의 비즈니스 로직을 처리합니다.
- PasswordEncoder를 사용하여 비밀번호를 안전하게 암호화합니다.

✔️ **application.yml 설정**

- 이메일 서버 설정을 통해 비밀번호 재설정 메일을 전송할 수 있습니다.

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/36358b89-fde5-4b16-95d9-7decef74047e/ea2aacfd-f391-4011-8236-bc60ab6a9879/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/36358b89-fde5-4b16-95d9-7decef74047e/42e9d9aa-9b54-4638-b74e-3316e287cd09/image.png)

### ✅ 사용자 인증 및 보안

✔️ **JWT 토큰 구현**

- `JwtTokenUtil` 클래스를 생성하여 JWT 토큰 생성, 검증, 파싱 기능을 구현했습니다.
- 토큰 생성 시 사용자 이메일을 subject로 설정하고, 만료 시간을 포함합니다.
- 비밀키는 `application.yml`에서 관리하며, HS512 알고리즘을 사용하여 토큰을 서명합니다.

```java
public String generateToken(String email) {
    Key key = generateKey();
    return Jwts.builder()
            .setSubject(email)
            .setExpiration(new Date(System.currentTimeMillis() + expiration))
            .signWith(key, SignatureAlgorithm.HS512)
            .compact();
}

```

✔️ **로그인 프로세스**

- `UserController`에서 로그인 요청을 처리합니다.
- 인증 성공 시 JWT 토큰을 생성하여 클라이언트에게 반환합니다.
- 클라이언트는 받은 토큰을 localStorage에 저장하여 이후 요청 시 사용합니다.

✔️ **토큰 검증**

- `validateToken` API를 구현하여 클라이언트가 보유한 토큰의 유효성을 서버에서 검증할 수 있습니다.
- 토큰 만료 여부를 확인하여 유효성을 판단합니다.

✔️ **Spring Security 설정**

- `SecurityConfig` 클래스에서 Spring Security 설정을 관리합니다.
- CSRF 보호를 비활성화하고, CORS 설정을 활성화했습니다.
- 세션 관리 정책을 STATELESS로 설정하여 세션을 사용하지 않는 RESTful API에 적합하게 구성했습니다.
- 토큰 검증 엔드포인트(`/api/validate-token`)는 인증 없이 접근 가능하도록 설정했습니다.

```java
@Configuration
@EnableWebSecurity
public class SecurityConfig {
    @Bean
    public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
        http
            .csrf().disable()
            .cors().and()
            .authorizeRequests()
            .antMatchers("/api/validate-token").permitAll()
            .anyRequest().authenticated()
            .and()
            .sessionManagement().sessionCreationPolicy(SessionCreationPolicy.STATELESS);
        return http.build();
    }
}

```

✔️ **보안 강화**

- JWT 비밀키를 환경 변수나 별도의 설정 파일에서 관리하여 보안을 강화했습니다.
- 토큰 만료 시간을 설정하여 장기간 사용으로 인한 보안 위험을 줄였습니다.

이러한 구현을 통해 안전하고 효율적인 사용자 인증 시스템을 구축했습니다. JWT를 사용함으로써 서버의 상태를 유지할 필요 없이 클라이언트 측에서 인증 정보를 관리할 수 있게 되었고, Spring Security를 통해 전반적인 애플리케이션의 보안을 강화했습니다.

### ✅ 기능 구현

- 사용자 관리 시스템 (회원가입, 로그인, 프로필 관리)
- 학습 콘텐츠 관리 (동영상 업로드, 스트리밍)
- 퀴즈 생성 및 관리
- PDF 자료 생성 및 다운로드
- 학습 진도 및 평가 시스템

### ✅ 개발 프로세스

- 프론트엔드와 백엔드의 연동, CORS 이슈 해결
- AWS 서비스 통합 및 배포 자동화

---

## 💡 성장 경험

이번 팀 프로젝트를 통해 백엔드 개발을 공부한 경험을 실전에 적용하게 되었습니다. 클론 코딩이 아닌 실제 프로젝트를 진행하면서 수많은 오류와 문제들을 마주했지만, 이를 강의와 팀원들과의 협업을 통해 해결해 나갔습니다. 그 과정에서 Spring Security, JWT, REST API에 대한 이해를 얻게 되었습니다.

한편, 팀 내에 프론트엔드 개발자가 없었기 때문에, JavaScript, HTML/CSS, React를 함께 학습하며 프로젝트에 적용했습니다. 이를 통해 서로 성장할 수 있었고, 프론트엔드와 백엔드의 전반적인 흐름을 이해하는 데 큰 도움이 되었습니다.

또한, 클라우드 서비스에 대한 개념이 부족했지만, AWS를 통해 서버를 설정하고 배포하면서 이를 익힐 수 있었습니다. 직접적인 소통을 통해 개발을 원활하게 이어나갔으며, 백엔드, 프론트엔드, AI 파트 간의 협업을 통해 프로젝트를 효율적으로 마무리할 수 있었습니다.

이번 한 달간의 프로젝트 경험은 백엔드 API 구성 방법과 클라우드 서비스에 대해서 많은 것을 배우고 숙달할 수 있었습니다. 또한, 분업과 소통을 통해 개발 능력뿐만 아니라 협업과 소통 능력도 크게 향상되었습니다. 이 경험은 앞으로의 개발자로서의 성장에 큰 밑거름이 될 것이라고 생각합니다. 

## 👀 서비스 화면

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/36358b89-fde5-4b16-95d9-7decef74047e/668004a5-9a59-4fbf-bd26-b9d6395686d3/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/36358b89-fde5-4b16-95d9-7decef74047e/804dadd6-fb57-4a77-8010-b5b690cfd0c5/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/36358b89-fde5-4b16-95d9-7decef74047e/a41f9ee1-7dad-44f0-822f-09910eb146c6/image.png)
