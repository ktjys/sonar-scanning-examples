pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        withSonarQubeEnv('sonar') {
          sh '''cd sonarqube-scanner-gradle
./gradlew -Dsonar.login=ed4d9996ab4948f15e756be7ab126bae0d6fe881 sonarqube'''
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