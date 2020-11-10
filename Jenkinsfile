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
                withSonarQubeEnv(installationName: 'sonar', credentialsId: 'sonar', envOnly: true) {
                    sh '''
                        echo ${SONAR_HOST_URL}
                        echo ${SONAR_CONFIG_NAME}
                        echo ${SONAR_AUTH_TOKEN}
                        echo ${SONAR_MAVEN_GOAL}
                        
                        cd ./sonarqube-scanner-maven/maven-basic/
                        mvn clean verify sonar:sonar
                    '''
                }
            }
        }
    }
}
