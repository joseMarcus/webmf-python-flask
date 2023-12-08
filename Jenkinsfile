pipeline {
    agent { docker { image 'python:3.10' } }
    stages {
        stage('build') {
            steps {
                sh 'pip install flask'
            }
        }
        stage('test') {
            steps {
                sh 'python3 test.py'
            }
        }
    }
}
