<h1 align="center">
  🧀 치즈한장 백엔드
</h1>

### 지점 정보 GET Test

http://cheese.ap-northeast-2.elasticbeanstalk.com/branch

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

Cloudtype 가동 제한: 1일 1회 정지됨
-> AWS에 배포

beanstalk docker 배포

-   새로운 환경 생성
-   플랫폼 docker, 로컬 코드 Dockerrunner.aws.json 업로드

http://cheese.ap-northeast-2.elasticbeanstalk.com

AWS RDS 인스턴스 생성

-   보안 그룹 인바운드, 아웃바운드 설정
-   로컬 Workbench에서 연결
-   cheese db structure/data import
-   Cheese/src/resource/application.properties DB url 수정
-   AWS EC2 instance와 RDS instance 연동됨
