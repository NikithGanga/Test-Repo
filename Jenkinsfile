pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/NikithGanga/Test-Repo.git'
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Build stage"'
                // Add build steps here, e.g., compiling code, running tests
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Test stage"'
                // Add test steps here, e.g., running unit tests
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                echo "Deploy stage"
                mkdir -p ${WORKSPACE}/html
                rsync -av --exclude=html . ${WORKSPACE}/html/
                '''
            }
        }
    }
}

