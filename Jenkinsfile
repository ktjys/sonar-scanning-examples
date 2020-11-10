pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        withSonarQubeEnv(installationName: 'sonar', credentialsId: 'sonar-token') {
          sh '''cd sonarqube-scanner-gradle
./gradlew sonarqube'''
        }

      }
    }

    stage('Quality Gate') {
      steps {
        timeout(time: 1, unit: 'HOURS') {
          waitForQualityGate true
        }

      }
    }

  }
}