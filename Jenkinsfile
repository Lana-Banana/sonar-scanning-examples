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
                        echo ${SONAR_CONFIG_NAME}
                        echo ${SONAR_HOST_URL}
                        echo ${SONAR_AUTH_TOKEN}
                        
                        pwd
                        ls -al
                        cd ./sonarqube-scanner-maven/maven-basic/
                        // mvn clean verify sonar:sonar
                    '''
                }
            }
        }
    }
}
