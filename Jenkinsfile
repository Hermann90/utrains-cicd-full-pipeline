pipeline{
     agent {
                docker {
                    image 'openjdk:11'
                }
            }
    stages{
        stage("sonar quality check"){
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
