pipeline {
    agent any

    stages {
        stage('Build') {
                     steps {
                         echo 'Building...'
                         sh './gradlew build'
                         echo 'successful build by github push trigger'
                         echo 'wow another-2 time successful build by github push trigger'
                     }
                 }
        stage('Create a Docker Image') {
                    steps {
                        echo 'Docker Image building..'
                        sh 'sudo ./gradlew build docker'
                        echo 'docker image build success'
                    }
                }
        stage('Push to docker hub') {
                    steps {
                            withDockerRegistry([ credentialsId: "docker-hub-credentials", url: "" ]) {
                              sh 'docker push brucegwanhooh/docker-test'
                            }

                    }
                    }
}
}