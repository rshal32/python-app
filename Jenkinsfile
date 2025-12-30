pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install flask
                '''
            }
        }

        stage('Run Test') {
            steps {
                sh '''
                    . venv/bin/activate
                    python3 -m py_compile app.py
                '''
            }
        }
    }
}

