pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'docker build -t danushvithiyarth/dev:latest .'
                }
            }
        }

        stage('Push') {
            steps {
                script {
                    sh 'docker login -u "danushvithiyarth" -p "$docker_pass" docker.io'
                    sh 'docker push danushvithiyarth/dev:latest'
                }
            }
        }

        stage('Cleanup') {
            steps {
                script {
                    sh 'docker image prune -f'
                }
            }
        }
    }
}
