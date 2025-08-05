pipeline {
    agent any
    tools {
        nodejs 'NodeJS17'  // This should match the name you set in Jenkins
    }
    stages {
        stage('Build') {
            steps {
                echo 'Installing dependencies...'
                bat 'npm install'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging...'
                bat 'xcopy * C:\\staging /E /Y'
            }
        }
        stage('Approval for Production') {
            steps {
                input message: 'Deploy to Production?'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
                bat 'xcopy * C:\\production /E /Y'
            }
        }
    }
}
