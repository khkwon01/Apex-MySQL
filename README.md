# Apex-MySQL

개발툴인 Apex와 MySQL를 연결하여 사용하기 위해서는 아래와 같은 단계를 수행하여 구성 하면 됩니다.   
MySQL Service 구성 --> Database Tools Connection 구성 --> APEX instances 구성 --> APEX에서 MySQL 연결 설정  

### 1. MySQL Service 구성
<img width="1324" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/c2aed366-2007-4804-8cec-7668ee5f863b">
- APEX에서 사용할 MySQL MDS 생성하여 구성

### 2. Database Tools Connection 생성
<img width="1329" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/77b5796e-5ce1-41ce-87c1-193c85febc10">
- APEX와 MySQL를 중간에서 연결할 Connection 서비스를 구성
     
<img width="1359" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/08330ba5-2b79-46ac-bb52-7c5040fb4e7d">
- Connection 서비스는 또한 SQL 작업을 위한 SQL Worksheet를 제공하기 때문에 쉽게 GUI 기반 데이터 작업이 가능함

### 3. APEX instance 구성
<img width="1022" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/8ed92998-91a9-4c8f-8bf5-f56e8d1cc2f1">
- APEX 이름을 정하고 DB는 기본 19c를 선택해서 구성     

<img width="1254" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/c67e07a7-2521-4d2a-918a-b4431dac309f">   
- 구성후 APEX instance를 선택하여 상세 페이지에서 들어가서 APEX 웹 인스턴스에 접속 (그림중 Launch APEX)    
<img width="783" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/aedf4208-aaff-48a0-8dc7-8a6f01b05cde">     
- Admin 페이지 접속 로그인이 나오면 구성시 등록한 패스워드로 로그인하여 신규 application 서비스를 하나 생성하여 해당 application 로그인     
<img width="696" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/5a62d4db-58c8-4dac-988d-3234b656f93f">    
- 여기 예제로 testapp1 서비스를 생성하여 설정한 계정과 패스워드로 로그인함
