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
                sh 'python -m venv venv'
                sh 'venv/bin/pip install -r requirements.txt'
            }
        }

        stage('Run Unit Tests') {
            steps {
                sh 'venv/bin/pytest'
            }
        }

        stage('Build Application') {
            steps {
                echo 'Building Flask Application'
            }
        }

        stage('Deploy Application') {
            steps {
                sh 'venv/bin/python app.py &'
                echo 'Application Deployed Successfully'
            }
        }
    }
}
