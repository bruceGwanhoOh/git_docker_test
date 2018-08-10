pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh './gradlew build'
                echo 'successful build by github push trigger'
                echo 'wow another-2 time successful build by github push trigger'

                sh 'sudo ./gradlew build docker'
                echo ' running spinrg boot'
                sh 'sudo docker run -p 8081:8081 -t brucegwanhooh/docker-test'
            }
        }
    }
}