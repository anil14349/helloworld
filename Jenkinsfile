pipeline {

  agent any
  environment {
    //adding a comment for the commit test
    //DEPLOY_CREDS = credentials('deploy-anypoint-user')
    MULE_VERSION = '4.3.0'
    //BG = "<BUSINESS-GROUP>"
    WORKER = "Micro"
  }
  stages {
  
    stage('Build') {
      steps {
            sh 'mvn -B -U -e -V clean package -DskipMunitTests'
      }
    }

    stage('Test') {
      steps {
          sh "mvn test"
      }
    }
/*
     stage('Deploy Development') {
      environment {
        ENVIRONMENT = 'Sandbox'
        APP_NAME = '<DEV-API-NAME>'
      }
      steps {
            sh 'mvn -U -V -e -B -DskipTests deploy -DmuleDeploy -Dmule.version="%MULE_VERSION%" -Danypoint.username="%DEPLOY_CREDS_USR%" -Danypoint.password="%DEPLOY_CREDS_PSW%" -Dcloudhub.app="%APP_NAME%" -Dcloudhub.environment="%ENVIRONMENT%" -Dcloudhub.bg="%BG%" -Dcloudhub.worker="%WORKER%"'
      }
    }
    
    stage('Deploy Production') {
      environment {
        ENVIRONMENT = 'Production'
        APP_NAME = '<API-NAME>'
      }
      steps {
            sh 'mvn -U -V -e -B -DskipTests deploy -DmuleDeploy -Dmule.version="%MULE_VERSION%" -Danypoint.username="%DEPLOY_CREDS_USR%" -Danypoint.password="%DEPLOY_CREDS_PSW%" -Dcloudhub.app="%APP_NAME%" -Dcloudhub.environment="%ENVIRONMENT%" -Dcloudhub.bg="%BG%" -Dcloudhub.worker="%WORKER%"'
      }
    }
    
 */  
  }

  tools {
    maven 'M3'
  }
}