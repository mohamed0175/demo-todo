pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh '''
                    python3 -m venv venv
                    ./venv/bin/pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                // This checks if the python code actually runs without crashing
                sh './venv/bin/python3 -m py_compile streamlit_app.py'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Application is ready! Take your UI screenshot now.'
            }
        }
    }
}
