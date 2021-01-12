# Jenkins Project 구성
  

## TestApp

- Jenkins > Pipeline Job > TestApp

1. Parameters
   - DO_TEST (Boolean)
   - DO_PUBLISH (Boolean)
   - APP_IMAGE_NAME (String)
   - APP_IMAGE_TAG (String) 
   - SOURCE_IMAGE_NAME (String)
     - Default Value : node
   - SORUCE_IMAGE_TAG (String)
     - Default Value : latest
   - TemplatePath
     - Default Value : toolchain/openshift
2. Pipeline (Pipeline script from SCM)
   - SCM : Git
   - Repository : https://github.com/kin3303/nodejs-ex.git
   - Credentials : 생성해 놓은 Git Credential
   - Branches to build : */master
   - Script Path : toolchain/Jenkinsfile
  
## Postman

1. Pipeline (Pipeline script from SCM)
   - SCM : Git
   - Repository : https://github.com/kin3303/nodejs-ex.git
   - Credentials : 생성해 놓은 Git Credential
   - Branches to build : */master
   - Script Path : toolchain/Jenkinsfile_Postman
