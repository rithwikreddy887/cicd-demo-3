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
                sh 'python3 -m pip install --upgrade pip'
                sh 'python3 -m pip install -r requirements.txt'
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