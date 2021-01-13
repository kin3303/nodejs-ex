# NodeJS 앱을 위한 Jenkins Project 구성

## TestApp

- Jenkins > Pipeline Job > TestApp

1. Parameters
   - DO_TEST (Boolean)
   - DO_PUBLISH (Boolean)
   - APP_IMAGE_NAME (String)
   - APP_IMAGE_TAG (String) 
   - SOURCE_IMAGE_NAME (String)
     - Default Value : node
   - SOURCE_IMAGE_TAG (String)
     - Default Value : latest
   - TemplatePath
     - Default Value : toolchain/openshift
2. Pipeline (Pipeline script from SCM)
   - SCM : Git
   - Repository : https://github.com/kin3303/nodejs-ex.git
   - Credentials : 생성해 놓은 Git Credential
   - Branches to build : */master
   - Script Path : toolchain/jenkins/Jenkinsfile
  
## TestApp_Postman

1. Pipeline (Pipeline script from SCM)
   - SCM : Git
   - Repository : https://github.com/kin3303/nodejs-ex.git
   - Credentials : 생성해 놓은 Git Credential
   - Branches to build : */master
   - Script Path : toolchain/Jenkinsfile_Postman

## TestApp_BackupApp

1. Parameters
   - PROJECT_NAME (String)
   - CLUSTER_NAME (String)
   - APP_NAME (String)

1. Pipeline (Pipeline script from SCM)
   - SCM : Git
   - Repository : https://github.com/kin3303/nodejs-ex.git
   - Credentials : 생성해 놓은 Git Credential
   - Branches to build : */master
   - Script Path : toolchain/Jenkinsfile_BackupApp
   
## TestApp_ReplaceRoute

1. Parameters
   - PROJECT_NAME (String)
   - CLUSTER_NAME (String)
   - APP_NAME (String)

1. Pipeline (Pipeline script from SCM)
   - SCM : Git
   - Repository : https://github.com/kin3303/nodejs-ex.git
   - Credentials : 생성해 놓은 Git Credential
   - Branches to build : */master
   - Script Path : toolchain/Jenkinsfile_ReplaceRoute


## TestApp_RollbackApp

1. Parameters
   - PROJECT_NAME (String)
   - CLUSTER_NAME (String)
   - APP_NAME (String)

1. Pipeline (Pipeline script from SCM)
   - SCM : Git
   - Repository : https://github.com/kin3303/nodejs-ex.git
   - Credentials : 생성해 놓은 Git Credential
   - Branches to build : */master
   - Script Path : toolchain/Jenkinsfile_RollbackApp
   
## TestApp_UpdateApp

1. Parameters
   - PROJECT_NAME (String)
   - CLUSTER_NAME (String)
   - APP_NAME (String)

1. Pipeline (Pipeline script from SCM)
   - SCM : Git
   - Repository : https://github.com/kin3303/nodejs-ex.git
   - Credentials : 생성해 놓은 Git Credential
   - Branches to build : */master
   - Script Path : toolchain/Jenkinsfile_UpdateApp
