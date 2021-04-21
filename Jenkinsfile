pipeline {
  agent any
  stages {
    stage('Setup') {
      steps {
        sh 'echo $SONAR_MAVEN_GOAL'
        echo '$SONAR_MAVEN_GOAL'
        withSonarQubeEnv(installationName: 'sonar-server', credentialsId: 'sonar-token', envOnly: true) {
          sh '''mvn clean install
mvn sonar:sonar -Dsonar.login=${actual-token}
'''
          sh 'echo "done"'
        }

      }
    }

  }
}