pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        withSonarQubeEnv('sonar') {
          sh '''cd sonarqube-scanner-gradle
gradle sonarqube'''
        }

      }
    }

  }
}