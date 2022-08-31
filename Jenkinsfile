pipeline{
    // agent any 
    stages{
        stage("sonar quality check"){
            agent {
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'token') {
                            sh 'chmod +x gradlew'
                            sh './gradlew build'
                            sh './gradlew sonarqube --stacktrace --debug'
                    }
                }  
            }
        }

    }
} 