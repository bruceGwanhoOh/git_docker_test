pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh './gradlew clean build'
                echo 'successful build by github push trigger'
                echo 'wow another-2 time successful build by github push trigger'
            }
        }
    }
    stages {
        stage('Making docker image') {
            steps {
                echo 'makeing a docker image..'
                sh './gradlew build docker'
                echo 'successful making docker image'
            }
        }
    }
    stage('run spring boot docker image'){
        echo 'running spring boot docker image'
        sh 'docker run -p 81:8081 -t brucegwanhooh/docker-test'
    }
}