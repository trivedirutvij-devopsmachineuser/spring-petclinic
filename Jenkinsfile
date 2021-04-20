pipeline {
  agent any
  stages {
    stage('Setup') {
      steps {
        echo 'Test'
        withSonarQubeEnv(installationName: 'sonarqube-server', credentialsId: 'sonar-token', envOnly: true) {
          sh '''./mvnw clean install 
./mvnw sonar:sonar -Dsonar.login=${sonar-token}'''
          sh 'echo "done"'
        }

      }
    }

  }
}