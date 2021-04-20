pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        echo 'Test'
        withSonarQubeEnv(installationName: 'abcd', credentialsId: 'sonar-token') {
          waitForQualityGate(credentialsId: 'sonar-token', abortPipeline: true)
        }

      }
    }

  }
}