pipeline {
  agent {
    label 'jenkins-slave-slave'
  }
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