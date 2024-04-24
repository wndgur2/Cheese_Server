<h1 align="center">
  🧀 치즈한장 백엔드
</h1>

## cloudtype docker container, Maria DB 배포

https://port-0-container-128y2k2llv9ia95q.sel5.cloudtype.app/

지점 정보 GET Test

https://port-0-container-128y2k2llv9ia95q.sel5.cloudtype.app/branch

## Docker Image

leejunghyeok/cheese:1.4

### 4.23 cloudtype 백엔드 배포

-   mvn package: ROOT.war 생성
-   pull tomcat 9.0.88 image with docker
-   build new docker image with ROOT.war in tomcat/webapps
-   Error에 따라 cheese image의 config/properties files 수정
-   linux/amd64 platform으로 docker hub에 push
-   Cloudtype에 image tag명 (leejunghyeok/cheese:1.4)으로 Conatiner 구동

### 4.24 cloudtype MariaDB 배포, 연동

-   Mysql Workbench에서 기존 local database의 structure/data export
-   Cloudtype mariaDB template 생성 및 외부 TCP 접근 허용
-   Mysql Workbench에서 Cloudtype mariaDB 연결
-   Cloudtype mariaDB 연결된 Workbench에서 export했던 .sql import

-   leejunghyeok/cheese:1.4의 application.properties 파일에 DB 주소, password 등 수정

### 4.25

-   TODO: frontend 수정, vercel 배포
