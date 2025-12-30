pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh '''
                python3 --version
                pip3 install flask
                '''
            }
        }

        stage('Run Test') {
            steps {
                sh '''
                python3 -m py_compile app.py
                '''
            }
        }
    }
}

