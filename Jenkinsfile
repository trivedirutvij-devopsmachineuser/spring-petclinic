pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        echo 'Test'
        withSonarQubeEnv(installationName: 'sonarqube-server', credentialsId: 'sonar-token', envOnly: true) {
          waitForQualityGate(credentialsId: 'sonar-token', abortPipeline: true)
        }

      }
    }

  }
}