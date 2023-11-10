# Apex-MySQL 구성

개발툴인 Apex와 MySQL를 연결하여 사용하기 위해서는 아래와 같은 단계를 수행하여 구성 하면 됩니다.   
MySQL Service 구성 --> Database Tools Connection 구성 --> APEX instances 구성 --> APEX에서 MySQL 연결 설정  

### 1. MySQL Service 구성
- APEX에서 사용할 MySQL MDS 생성하여 구성
<img width="1324" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/c2aed366-2007-4804-8cec-7668ee5f863b">

### 2. Database Tools Connection 생성
- APEX와 MySQL를 중간에서 연결할 Connection 서비스를 구성
<img width="1329" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/77b5796e-5ce1-41ce-87c1-193c85febc10">

- Connection 서비스는 또한 SQL 작업을 위한 SQL Worksheet를 제공하기 때문에 쉽게 GUI 기반 데이터 작업이 가능함     
<img width="1359" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/08330ba5-2b79-46ac-bb52-7c5040fb4e7d">

### 3. APEX instance 구성
- APEX 이름을 정하고 DB는 기본 19c를 선택해서 구성   
<img width="1022" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/8ed92998-91a9-4c8f-8bf5-f56e8d1cc2f1">

- 구성후 APEX instance를 선택하여 상세 페이지에서 들어가서 APEX 웹 인스턴스에 접속 (그림중 Launch APEX)   
<img width="1254" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/c67e07a7-2521-4d2a-918a-b4431dac309f">

- Admin 페이지 접속 로그인이 나오면 구성시 등록한 패스워드로 로그인하여 신규 application 서비스를 하나 생성하여 해당 application 로그인    
<img width="783" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/aedf4208-aaff-48a0-8dc7-8a6f01b05cde">

- 예제로 testapp1 서비스를 생성하여 설정한 계정과 패스워드로 로그인함
<img width="696" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/5a62d4db-58c8-4dac-988d-3234b656f93f">          

### 4. APEX에서 MySQL 설정
- Workspace Utilities에서 Web Credentials사용하여 oracle cloud와 연결할수 있도록 설정    
1) Authentication type: OCI    
2) OCI User ID: user 셋팅에 나오는 User ID를 지정    
3) OCI Tenancy ID: user 셋팅에 나오는 Tenancy ID를 지정    
4) OCI Priviate Key: user 셋팅에 API 설정에 등록된 private key를 지정 (없으면 새로 생성해서 등록)    
5) OCI Public Key Fingerprint: user 셋팅에 API 설정에 표시된 Fingerprint를 지정
<img width="1151" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/d6f6e8a5-caa3-4906-8dba-cc00ab032079">   

- Web Credentials 구성하고 나면 아래와 같이 표시됨   
<img width="1173" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/76fbd7d1-9fed-4e45-823f-860c47b028c0">

- OCI Web인증을 통해 Rest Enabled SQL를 설정하기 위해 위에 구성한 connection를 사용하여 MySQL연결      
```
Endpoint URL 입력예 => "https://sql.dbtools.<<수정(리즌):ap-chuncheon-1>>.oci.oraclecloud.com/20201005/ords/<<수정:connection OCID정보>>/_/sql" 로 입력     
```
<img width="816" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/39e729a6-4360-4bb2-bb9d-203a7742a539">

- 위에 Web 인증에 만들어 놓은 인증 정보를 선택하여 구성
<img width="815" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/a7d0835e-c459-4c61-8ac7-bcc9ee8837a2">

- 구성후 아래 Test를 클릭하면 MySQL DB에 접속하여 database 선택하는 화면이 출력되고 선택하면 됨.
<img width="1162" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/235e5d50-e534-4ded-afff-6f73237ea815">
<img width="807" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/4c65a0f2-2427-4cff-9f30-e0db8dd018ed">

### 5. APEX에서 application 생성하여 MySQL 사용
- 간단한 application 생성
<img width="1166" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/0803c82c-f9bc-4e5d-a499-9c40852f3914">

- application 생성후 html페이지를 생성 가능한데, chart 관련된 항목을 선택하여 소스를 mysql설정 항목으로 선택하여 지정
<img width="1367" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/45787450-5884-4d3d-a3da-fd9133d03af3">

- 해당 페이지를 실행하면 아래와 같은 화면이 표시됨 (공항별 항공기 대수를 표시하는데 항공기 대수가 2개 이상인 공항 10개 표시)
<img width="1350" alt="image" src="https://github.com/khkwon01/Apex-MySQL/assets/8789421/daf0266c-d48d-4384-b87b-6542340cab82">


