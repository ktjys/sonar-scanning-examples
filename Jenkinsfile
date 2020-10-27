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
gradle -Dsonar.login=ed4d9996ab4948f15e756be7ab126bae0d6fe881 -Dsonar.projectKey=dodt:sonarqube-scanner-gradle sonarqube'''
        }

      }
    }

  }
}