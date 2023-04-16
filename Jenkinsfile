pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'sudo Docker build . -t todo-app'
            }
        }
        stage('deploy') {
            steps {
                sh 'sudo docker run -p 8000:8000 -d todo-app'
            }
        }
    }
}
