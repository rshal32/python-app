pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/rshal32/python-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install flask'
            }
        }

        stage('Run Test') {
            steps {
                sh 'python3 -m py_compile app.py'
            }
        }
    }
}
