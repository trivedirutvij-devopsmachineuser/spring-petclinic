pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        echo 'Test'
        withSonarQubeEnv(installationName: 'sonarqube-server', credentialsId: 'sonar-token', envOnly: true) {
          sh '''./mvnw clean verify sonar:sonar -Dsonar.login=${sonar-token}
'''
          sh 'echo "done"'
        }

      }
    }

  }
}