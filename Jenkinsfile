pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Getting code from GitHub'
            }
        }

        stage('Validate HTML') {
            steps {
                echo 'HTML Validation Successful'
            }
        }

        stage('Build') {
            steps {
                echo 'Build Successful'
            }
        }

    }

    post {
        success {
            echo 'Pipeline Completed Successfully'
        }
    }
}