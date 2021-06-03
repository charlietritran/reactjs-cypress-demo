pipeline {
    agent any

    tools {nodejs "node"}

    environment {
        CHROME_BIN = '/bin/google-chrome'
    }

    stages {
        stage('Dependencies') {
            steps {
                sh 'npm i'
            }
        }
        stage('Build') {
            steps {
                sh 'npm start'
            }
        }
        stage('Unit Tests') {
            steps {
                sh 'npm run cypress:headless'
            }
        }
        stage('e2e Tests') {
            steps {
                echo 'e2e Testing....'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}