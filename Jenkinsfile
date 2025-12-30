pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                url: 'https://github.com/USERNAME/flask-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'python -m venv venv'
                bat 'venv\\Scripts\\pip install -r requirements.txt'
            }
        }

        stage('Run Unit Tests') {
            steps {
                bat 'venv\\Scripts\\pytest'
            }
        }

        stage('Build Application') {
            steps {
                echo 'Build stage completed (Flask app does not require compilation)'
            }
        }

        stage('Deploy Application') {
            steps {
                bat 'venv\\Scripts\\python app.py'
                echo 'Flask application deployed successfully'
            }
        }
    }
}
