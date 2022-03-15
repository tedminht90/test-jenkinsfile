pipeline {
    agent any
    stages {
            stage('Clone'){
                steps {
                    git 'https://github.com/tedminht90/test-jenkinsfile.git'
                }
            }
            stage('Build'){
                steps {
                    withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/'){
                        sh 'docker build -t tedminht/html:v10 .'
                        sh 'docker push tedminht/html:v10'
                    }
                }
            }
    }
}