### Jenkins Plugin 설치

1. `Docker Pipeline` 플러그인 설치
2. dockerHub 에 로그인하기 위한 Credential 을 Jenkins 에 추가
    - Credentials -> Add Credentials (구버전)
    - Manage Jenkins -> Manage Credentials -> Provider : Jenkins -> Global credentials  -> Add Credentials (최신버전)
        - Kind : Username with password
        - Scope : Global
        - Username : nexus-registry 계정명
        - Password : nexus-registry 패스워드
        - ID : nexus-registry
        - Description : nexus-registry
        
### Jenkins Project 설정

1. 프로젝트 추가
    - New Item
        - ItemName : nodejs-pipe
        - ItemType : Pipeline

2. 프로젝트 Configure
    - Configure -> General
       - This project is parameterized
         - Add Parameter -> Boolean Parameter -> Name : DO_TEST
         - Add Parameter -> Boolean Parameter -> Name : DO_PUBLISH  
         - Add Parameter -> Boolean Parameter -> Name : DO_FUNCTION_TEST
         - Add Parameter -> String Parameter -> Name : TAG_NAME  
         - Add Parameter -> String Parameter -> Name : APP_IMAGE_NAME  
    - Configure -> Advanced Project Options -> Pipeline
        - Definition : Pipeline script from SCM
        - SCM : Git
        - Repository URL : https://github.com/kin3303/nodejs-ex.git
        - Branches to build : */master
        - Script Path : misc/Jenkinsfile

### Reference

- Docker Pipeline 
  - https://www.jenkins.io/doc/book/pipeline/docker/
  - https://docs.cloudbees.com/docs/admin-resources/latest/plugins/docker-workflow
  
- Test Container
  - https://hackernoon.com/testing-strategies-for-docker-containers-f633e261e75a
