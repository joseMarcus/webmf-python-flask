pipeline {
    agent { docker { image 'python:3.10' } }
    stages {
        stage('build') {
            steps {
                sh 'bash -c pip install flask'
            }
        }
        stage('test') {
            steps {
                sh 'bash -c python3 test.py'
            }
        }
    }
}
