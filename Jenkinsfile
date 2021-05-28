pipeline {
    agent any
    stages {
        stage('Pushing the image to the local Docker registry.') {
            steps {
                 withDockerRegistry([credentialsId: 'DOCKER_CREDENTIALS', url: "https://192.168.0.144:5000/"]) {
                        sh 'docker pull ubuntu'
                        sh 'docker build -t devtest-dockerimage .'
                        sh 'docker tag devtest-dockerimage:1.0'
                        sh 'docker push devtest-dockerimage:1.0'
                    }
                }
            }
        }
    }
}

