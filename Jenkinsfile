pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t myapp .'
            }
        }
        
        stage('Test') {
            steps {
                sh 'docker run myapp python manage.py test'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'docker run -d -p 8000:8000 myapp python manage.py runserver 0.0.0.0:8000'
            }
        }
    }
}
