pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }

        stage('Check Python Version') {
            steps {
                sh 'python3 --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt --break-system-packages'
            }
        }

        stage('Run Unit Tests') {
            steps {
                sh 'PYTHONPATH=. pytest tests/test_app.py'
            }
        }

        stage('Run Integration Tests') {
            steps {
                sh 'PYTHONPATH=. pytest tests/'
            }
        }
    }
}