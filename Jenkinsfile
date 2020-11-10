pipeline {
    agent {
        label 'jenkins-jenkins-slave'
     }
    stages {
        stage('Sonar Scan') {
            // tools {
            //     maven 'M3'
            // }
            steps {
                withSonarQubeEnv(installationName: 'sonar', credentialsId: 'sonar', envOnly: true) {
                    sh '''
                        echo ${env.SONAR_HOST_URL}
                        echo ${env.SONAR_CONFIG_NAME}
                        echo ${env.SONAR_AUTH_TOKEN}
                        echo ${env.SONAR_MAVEN_GOAL}
                    '''
                }
            }
        }
    }
}
