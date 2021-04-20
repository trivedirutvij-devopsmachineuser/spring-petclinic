pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        echo 'Test'
        withSonarQubeEnv(installationName: 'sonarqube-server', credentialsId: 'sonar-token', envOnly: true) {
          sh '''echo ${sonar-token}
# ./mvnw clean install
# ./mvnw clean verify sonar:sonar -Dsonar.login=${sonar-token}
'''
          sh 'echo "done"'
        }

      }
    }

  }
}