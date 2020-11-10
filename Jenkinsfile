pipeline {
  agent none
  stages {
    stage('Sonar Scan') {
      steps {
        withSonarQubeEnv(installationName: 'sonar', credentialsId: 'sonar') {
          sh '''
            pwd
            ls -al
          '''
        }

      }
    }

  }
}