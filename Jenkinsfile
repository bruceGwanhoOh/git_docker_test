pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh './gradlew build'
                echo 'successful build by github push trigger'
                echo 'wow another-2 time successful build by github push trigger'

                sh 'sudo ./gradlew build docker'
                echo ' running spinrg boot'
                sh 'sudo docker run -p 8081:8081 -t brucegwanhooh/docker-test'
            }
        }
        stage('Create a Docker Image') {
                    steps {
                        echo 'Docker Image building..'
                        ssh 'sudo ./gradlew build docker'
                        echo 'docker image build success'
                    }
                }
        stage('Push to docker hub') {
                    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                               echo 'pushing docker image'
                               ssh 'sudo docker push brucegwanhooh/docker-test'
                               echo 'push success'
                            }
    }
}