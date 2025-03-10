Fuzzingzzingi
==============
안녕하세요! WHS2기 교육생들이 만드는 스마트 웹 퍼저 프로젝트예요! 😊

목차
> [프로젝트 소개](프로젝트-소개)
>    * 팀 소개
>    * 주제
>    * 목표
>
> [개발 전](개발-전)
> 
> [전체 파이프라인](전체-파이프라인)
>    
> [세부 구조 및 기능](세부-구조-및-기능)
>    * Crawler
>    * Proxy
>    * Fuzzer
>
> [시연 영상](시연-영상)
> 
> [개발 이후](개발-이후)
>    * 느낀점
>    * 향후 계획
>   

<br>
<br>

# 프로젝트 소개
> #### 프로젝트 명
> Smart Web Fuzzer 제작
>
> #### 프로젝트 팀명
> 퍼징징이
>
> #### 프로젝트 멘토
> 유재욱 멘토님
> 
> #### 프로젝트 PL
> 원요한 PL님
>
> #### 팀원
> PM - 우승훈
> 남정운
> 박지양
> 전다울
> 지연태
> 최희원
> 안현수
>
> 저희 팀은 웹 해킹을 잘 모르는 사람들도 함께 공부하며, 결과에 집착하기보다는 과정에서의 ***발전***을 위해서 노력하는 팀원으로 구성되어 있습니다.
>
<br>

> ## 팀 소개
> <img src="https://github.com/user-attachments/assets/6dd9e3ba-b482-4d7b-b411-483f2f86f9ff"/>
<br>

> ## 주제
> Web Fuzzer란 웹 애플리케이션 및 서비스의 보안 취약점을 자동으로 탐지, 분석하는 프로그램
>
> 기존의 Web Fuzzer보다 더 적은 패킷을 이용하여 취약점을 진단하는 ***Smart Web Fuzzer***를 개발 
<br>

> ## 목표
> 1. 다양한 취약점을 진단한다.
>    - SQL Injection
>    - Command Injection
>    - SSRF
>    - XSS
>    - File Download
>      
> 2. 프록시 구현
>    - 오픈 소스 사용을 최소화하여 HTTPS 프록시 구현한다.
>      
> 3. 플랫폼
>    - 각 취약점에 대한 탐지 로직을 모듈화하여 오픈 소스로 배포하여 지속적으로 업데이트한다.

<br>
<br>

# 개발 전
> ## 오픈 소스 도구 분석
> <img src="https://github.com/user-attachments/assets/fd37b461-6ed7-4e4f-84de-06e6e3774b7e" width=400 height=200/>

> ## 코드 컨벤션 작성
> <img src="https://github.com/user-attachments/assets/b145c087-ba38-46f0-8455-38ab647dfd5a" width=400 height=200/>

> ## 깃허브 사용법 학습 및 커밋 메세지 통일
> <img src="https://github.com/user-attachments/assets/f1802c26-58b6-4cc9-aa1b-d891307caf03" width=400 height=200/>

<br>
<br>

# 전체 파이프라인
>
> <img src="https://github.com/user-attachments/assets/789a1264-2cc4-463c-a9c8-5a010c048a86"/>

<br>
<br>

# 세부 구조 및 기능
> ## Crawler
>

> ## Proxy
> <img src="https://github.com/user-attachments/assets/9a601653-2a6d-4c0a-b38f-8989621d97b0" width=500 height=300/>

> ## Fuzzer
> #### SQL Injection
> <img src="https://github.com/user-attachments/assets/3d4f0334-27f5-4885-8963-622ccb3970d9" width=500 height=300/>
>
> 1. DB 내 저장된 타겟 엔드포인트들의 URL, HTTP 메소드, 파라미터 조회
>
> 2. 디렉토리 내 텍스트 파일로부터 기본 Payload 로드
>  
> 3. DB에서 조회한 메소드, 파라미터에 맞춰 기본 Payload를 Injection하여 취약점 여부 체크
>  
> 4. 취약점 의심 시 메인 Payload를 로드하여 Fuzzing
>  
>
> #### Command Injection
> <img src="https://github.com/user-attachments/assets/a12b1fc5-9e0c-4111-94c6-f6aa82988fe7" width=500 height=300/>
>
> 1. DB 내 저장된 타겟 엔드포인트들의 URL, HTTP 메소드, 파라미터 조회
> 
> 2. Sleep 명령어를 여러 형태로 조합된 기본 Payload를 Injection
>
> 3. 응답 시간이 5초 이상 소요될 경우 URL만 필터링
>
> 4. 기본 Payload를 10초로 설정 후 다시 Injection
>
> 5. 응답 시간이 10초 이상 소요될 경우 취약점 의심
>
> 6. 메인 Payload를 로드하여 Fuzzing
>
>
> #### SSRF
> <img src="https://github.com/user-attachments/assets/e7be2f34-4754-4169-baa9-39f2fa45586d" width=500 height=300/>
>
> 1. DB 및 
>
> #### XSS
> <img src="https://github.com/user-attachments/assets/a20b19fd-6f0c-4ab2-a838-f87f3490c176" width=500 height=300/>
>
>
> #### File Download
> <img src="https://github.com/user-attachments/assets/7c4e7e75-b6ec-467d-991c-714b7c690942" width=500 height=300/>
>
>

<br>
<br>

# 시연 영상
><img src="https://github.com/user-attachments/assets/e70b9429-b435-484d-85cb-033b145b91d1"/>

<br>
<br>

# 개발 이후
> ## 느낀점
> 그동안 워게임을 풀면서 나름 기초적인 기법들은 잘 알고 있다고 생각했었는데, 사실 진짜 중요한 것은 기본이었습니다.
> 
> 퍼저 부분을 만들면서 수많은 구글링을 했습니다. 특히 OWASP를 학교 강의 시간보다 오랫동안 봤는데, 이게 엄청난 도움이 되었습니다.
> 
> 솔직히 처음에는 어떻게 만들어야 할까 감도 안잡혔습니다. 하지만 기본 원리를 다시 공부하고, 웹 애플리케이션과의 상호작용을 머릿속에 그려보니 생각보다 쉽게 구현이 되었습니다.
> 
> 사실 보완할 부분도 많습니다. 해킹 기법도 더 남았고, 특히 Payload가 한참 부족하고 더 발전시켜야 하는데, 이건 차차 해킹 실력을 더 키워나가면서 보완해야 할 과제인 것 같습니다.
> 
> 학기 중에 진행하는 게 생각보다 힘들었는데, 그럼에도 불구하고 너무 값진 시간이었습니다. 실력을 키우기에도, 꿈을 키우기에도.
> 
> 함께한 팀원들, 멘토님 그리고 PM님 모두 고생하셨습니다. 항상 늘 행운이 함께하길.

> ## 향후 계획
>  * 프로젝트 종료 이후에도 Fuzzer 개선 예정
>  * 제작한 Fuzzer를 이용한 버그 바운티 참가 예정
