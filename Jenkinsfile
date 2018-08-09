pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh './gradlew clean build'
                echo 'successful build by github push trigger'

            }
        }
    }
}