pipeline {
  agent any
  stages {
    stage('build') {
      tools {
        gradle 'gradle6.7'
      }
      steps {
        withSonarQubeEnv('sonar') {
          sh '''cd sonarqube-scanner-gradle
pwd
gradle sonarqube'''
        }

      }
    }

  }
}