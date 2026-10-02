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
                bat '"C:\Users\ADMIN\AppData\Local\Programs\Python\Python311\python.exe" -m compileall src'
            }
        }

        stage('Test') {
            steps {
                bat '"C:\Users\ADMIN\AppData\Local\Programs\Python\Python311\python.exe" -m pytest --junitxml=pytest-results.xml'
            }
        }

        stage('Result') {
            steps {
                echo 'Build and tests completed successfully.'
            }
        }
    }

    post {
        always {
            junit 'pytest-results.xml'
        }
    }
}
