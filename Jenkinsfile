pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building Application...'

                bat '''
                if exist build rmdir /s /q build
                mkdir build
                copy index.html build\\
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Application...'

                bat '''
                if exist build\\index.html (
                    echo Test Passed
                ) else (
                    echo Test Failed
                    exit /b 1
                )
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application...'

                bat '''
                if exist deploy rmdir /s /q deploy
                mkdir deploy
                copy build\\index.html deploy\\
                '''
            }
        }

    }

    post {
        success {
            echo 'CI/CD Pipeline Successful'
        }

        failure {
            echo 'Pipeline Failed'
        }
    }
}