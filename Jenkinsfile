pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t todo-app .'
            }
        }
        
        stage('Test') {
            steps {
                sh 'docker run todo-app python manage.py test'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'docker run -d -p 8000:8000 todo-app python manage.py runserver 0.0.0.0:8000'
            }
        }
    }
}
