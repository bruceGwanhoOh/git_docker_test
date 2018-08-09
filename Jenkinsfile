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
        stage('Make an image') {
                    steps {
                        echo 'making a docker image..'
                                                sh './gradlew build docker'
                                                echo 'successful making docker image'
                    }
                }
                stage('Run an image') {
                            steps {
                                echo 'Building..'
                                echo 'running spring boot docker image'
                                                sh 'docker run -p 81:8081 -t brucegwanhooh/docker-test'
                            }
                        }


    }

}