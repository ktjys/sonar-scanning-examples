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
gradle -Dsonar.host.url=https://sonar.acldevsre.de -Dsonar.login=de9bd89410120c3e08f5f54dabc27d34816e88e8 build sonarqube'''
        }

      }
    }

  }
}