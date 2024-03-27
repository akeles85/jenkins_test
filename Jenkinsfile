pipeline {
    agent {
        label 'm1-build-agent'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
                // If you need to install dependencies, add commands here, for example:
                // sh 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'                
                sh 'pip3 install pytest'
                sh 'python3 -m pytest test_calculator.py'
            }
        }
    }
    post {
        always {
            echo 'Build finished.'
        }
        success {
            echo 'Build was successful!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}