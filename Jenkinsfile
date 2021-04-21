pipeline {
  agent any
  stages {
    stage('Setup') {
      steps {
        sh 'echo $SONAR_MAVEN_GOAL'
        echo '$SONAR_MAVEN_GOAL'
        withSonarQubeEnv(installationName: 'sonar-server', credentialsId: 'sonar-token', envOnly: true) {
          sh '''./mvnw clean install 
./mvnw sonar:sonar'''
          sh 'echo "done"'
        }

      }
    }

  }
}