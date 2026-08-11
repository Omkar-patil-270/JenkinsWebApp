pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub...'
            }
        }

        stage('Build') {
            steps {
                echo 'Build successful - HTML/CSS/JS files are ready.'
                bat 'dir'
            }
        }

        stage('Test') {
            steps {
                echo 'Running basic web application test...'
                bat 'if not exist index.html exit /b 1'
                bat 'if not exist style.css exit /b 1'
                bat 'if not exist script.js exit /b 1'
                echo 'Test passed!'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying website...'
                bat 'if not exist C:\\JenkinsDeploy mkdir C:\\JenkinsDeploy'
                bat 'xcopy /Y index.html C:\\JenkinsDeploy\\'
                bat 'xcopy /Y style.css C:\\JenkinsDeploy\\'
                bat 'xcopy /Y script.js C:\\JenkinsDeploy\\'
                echo 'Deployment completed!'
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check the console output.'
        }
    }
}