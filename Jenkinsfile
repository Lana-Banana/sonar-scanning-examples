pipeline {
    agent {
        label 'jenkins-jenkins-slave'
     }
    stages {
        stage('Sonar Scan') {
            tools {
                maven 'M3'
            }
            steps {
                withSonarQubeEnv(installationName: 'sonar', credentialsId: 'sonar') {
                    sh '''
                        pwd
                        ls -al
                        cd ./sonarqube-scanner-maven/maven-basic/
                        mvn clean verify sonar:sonar
                    '''
                }
            }
        }
    }
}
