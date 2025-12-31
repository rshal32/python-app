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
        stage('Build Docker Image') {
    steps {
        sh 'docker build -t python-jenkins-app .'
    }
}
stage('Deploy') {
    steps {
        sh '''
        docker stop python-app || true
        docker rm python-app || true
        docker run -d --name python-app -p 80:5000 python-jenkins-app
        '''
    }
}

    }
}

