# [All-In-One] 강의 솔루션 플랫폼
![AI 4조 썸네일](https://github.com/user-attachments/assets/8048a79d-23ff-43b6-981e-9611240a00e2)

## 😊 Team Members

| 이승원 | 권도훈 | 송효원 | 양호준 | 이혜미 | 조민기 | 전병찬 |
|:------:|:------:|:------:|:------:|:------:|:------:|:------:|

---

## 📜 서비스 소개

> 영상만 올리면 모든 학습 지원 기능을 한 번에 제공하는 솔루션!

### 🌿 관리자 워크플로우

1. 📤 영상 업로드
2. ☁️ S3 저장소 저장
3. 🧠 AI 모델 영상 분석
4. 🔄 OCR & STT 텍스트 변환
5. 🤖 Chat GPT API 활용
   - 📄 강의자료 PDF 생성
   - ❓ 퀴즈 생성
   - 🖼️ 영상 썸네일 생성

### 🌿 사용자 경험

1. 🚪 시스템 접근
2. ✍️ 회원가입
3. 🏠 메인화면 접속
4. 📚 학습 관리 기능
   - 📋 강의 목록 확인
   - 🎥 강의 시청
   - 📥 PDF 다운로드
   - ✅ 퀴즈 참여
   - 📊 학습 평가 확인
   - 📈 강의 집중도 분석

---

## 🛠 기술 스택

<table>
  <tr>
    <th>Front-end</th>
    <th>Back-end</th>
    <th>DevOps</th>
  </tr>
  <tr>
    <td>
      <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=React&logoColor=black"/>
    </td>
    <td>
      <img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=java&logoColor=white"/>
      <img src="https://img.shields.io/badge/Spring-6DB33F?style=flat-square&logo=Spring&logoColor=white"/>
    </td>
    <td>
      <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=Amazon-AWS&logoColor=white"/>
      <img src="https://img.shields.io/badge/NGINX-009639?style=flat-square&logo=NGINX&logoColor=white"/>
    </td>
  </tr>
  <tr>
    <td></td>
    <td>
      <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=MySQL&logoColor=white"/>
    </td>
    <td>
      <img src="https://img.shields.io/badge/Amazon S3-569A31?style=flat-square&logo=Amazon-S3&logoColor=white"/>
      <img src="https://img.shields.io/badge/Amazon RDS-527FFF?style=flat-square&logo=Amazon-RDS&logoColor=white"/>
    </td>
  </tr>
</table>

---

## 🚀 프로젝트 상세

**🔸 역할:** Back-end Developer

**🔸 프로젝트 기간:**
- 아이디어 구상: 2023/06/14 ~ 2023/06/21
- 개발 기간: 2023/06/24 ~ 2023/07/26

**🔸 주요 링크:**
- [🎥 시연 영상](https://drive.google.com/file/d/1edAgBRdS0zu9Th4e02RKy7H0KcSBZPmc/view?usp=drive_link)
- [📄 프로젝트 자료 (PDF)](https://drive.google.com/file/d/1RyeG4yk8vQp_ac_z0vLo-tUskPM_v_HK/view?usp=drive_link)
- [📘 프로젝트 Notion](https://www.notion.so/93e4136b98234fcdad12f4c79ea8c63f?pvs=21)

---

## 🖥 개발 내용

저는 Backend와 Front를 담당하였습니다.

백엔드는 **Spring Boot**를 사용하여 **REST API**를 구현하였고, 서버의 경우 **AWS EC2**를 사용하고, **DB**와 **Storage**를 **RDS**와 **S3**로 분리하여 구현했습니다. DB는 **MySQL**을 사용했고, API 서버는 **NGINX**로 배포하였습니다.

프론트엔드는 **React**를 사용하여 구현했으며, 이를 NGINX를 통해 호스팅했습니다.
![서비스 아키텍처](https://github.com/user-attachments/assets/4db37469-c8ee-4275-acd3-9e11feffccb1)

### ✅ 아키텍처 구성
* Spring Boot 애플리케이션을 도메인으로 호스팅
* React 애플리케이션을 도메인으로 호스팅
* 두 애플리케이션 모두 NGINX를 사용하여 리버스 프록시 설정

### ✅ 데이터베이스 및 스토리지
* MySQL을 AWS RDS에서 호스팅하여 데이터 저장
* AWS S3를 사용하여 파일 및 미디어 저장

### ✅ 사용자 인증 및 비밀번호 재설정 기능 구현

✔️ **UserController 클래스**
* 사용자 등록, 로그인, 비밀번호 재설정 관련 엔드포인트를 제공합니다.
* 사용자 등록 시 비밀번호를 암호화하여 저장합니다.
* 로그인 시 이메일과 비밀번호를 검증합니다.
* 비밀번호 재설정 요청 시 토큰을 생성하고 이메일로 재설정 링크를 전송합니다.

✔️ **비밀번호 재설정 프로세스**
* PasswordResetToken 엔티티를 사용하여 비밀번호 재설정 토큰을 관리합니다.
* 토큰 생성 시 24시간의 유효 기간을 설정합니다.
* 이메일을 통해 비밀번호 재설정 링크를 전송합니다.
* 토큰의 유효성을 검증한 후 비밀번호를 변경할 수 있습니다.

✔️ **UserService 클래스**
* 사용자 저장, 비밀번호 재설정 토큰 생성, 이메일 전송 등의 비즈니스 로직을 처리합니다.
* PasswordEncoder를 사용하여 비밀번호를 안전하게 암호화합니다.

✔️ **application.yml 설정**
* 이메일 서버 설정을 통해 비밀번호 재설정 메일을 전송할 수 있습니다.

| 비밀번호 재설정 | 비밀번호 변경 |
| --------------- | ------------- |
| ![비밀번호 재설정](https://github.com/user-attachments/assets/8a8cd25b-29e1-44bf-b024-cdccd10261ae) | ![비밀번호 변경](https://github.com/user-attachments/assets/2fa46bf8-0be2-4a07-a33c-91fbab9cbc57) |


### ✅ 사용자 인증 및 보안

✔️ **JWT 토큰 구현**
* `JwtTokenUtil` 클래스를 생성하여 JWT 토큰 생성, 검증, 파싱 기능을 구현했습니다.
* 토큰 생성 시 사용자 이메일을 subject로 설정하고, 만료 시간을 포함합니다.
* 비밀키는 `application.yml`에서 관리하며, HS512 알고리즘을 사용하여 토큰을 서명합니다.

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
* `UserController`에서 로그인 요청을 처리합니다.
* 인증 성공 시 JWT 토큰을 생성하여 클라이언트에게 반환합니다.
* 클라이언트는 받은 토큰을 localStorage에 저장하여 이후 요청 시 사용합니다.

✔️ **토큰 검증**
* `validateToken` API를 구현하여 클라이언트가 보유한 토큰의 유효성을 서버에서 검증할 수 있습니다.
* 토큰 만료 여부를 확인하여 유효성을 판단합니다.

✔️ **Spring Security 설정**
* `SecurityConfig` 클래스에서 Spring Security 설정을 관리합니다.
* CSRF 보호를 비활성화하고, CORS 설정을 활성화했습니다.
* 세션 관리 정책을 STATELESS로 설정하여 세션을 사용하지 않는 RESTful API에 적합하게 구성했습니다.
* 토큰 검증 엔드포인트(`/api/validate-token`)는 인증 없이 접근 가능하도록 설정했습니다.

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
* JWT 비밀키를 환경 변수나 별도의 설정 파일에서 관리하여 보안을 강화했습니다.
* 토큰 만료 시간을 설정하여 장기간 사용으로 인한 보안 위험을 줄였습니다.

이러한 구현을 통해 안전하고 효율적인 사용자 인증 시스템을 구축했습니다. JWT를 사용함으로써 서버의 상태를 유지할 필요 없이 클라이언트 측에서 인증 정보를 관리할 수 있게 되었고, Spring Security를 통해 전반적인 애플리케이션의 보안을 강화했습니다.

### ✅ 기능 구현
* 사용자 관리 시스템 (회원가입, 로그인, 프로필 관리)
* 학습 콘텐츠 관리 (동영상 업로드, 스트리밍)
* 퀴즈 생성 및 관리
* PDF 자료 생성 및 다운로드
* 학습 진도 및 평가 시스템

### ✅ 개발 프로세스
* 프론트엔드와 백엔드의 연동, CORS 이슈 해결
* AWS 서비스 통합 및 배포 자동화

---

## 💡 성장 경험

- 🚀 실전 프로젝트를 통한 백엔드 개발 경험 적용
- 🔒 Spring Security, JWT, REST API에 대한 심층적 이해
- 🌐 프론트엔드 기술 (JavaScript, HTML/CSS, React) 학습
- ☁️ AWS를 통한 클라우드 서비스 실전 경험
- 👥 팀 협업 및 소통 능력 향상

---
