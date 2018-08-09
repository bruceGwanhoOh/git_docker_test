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
        stage('clone') {
                    steps {
                        git url: 'https://github.com/bruceGwanhoOh/git_docker_test.git'
                    }
                }
    }

}