pipeline {
    agent any

    tools {nodejs "NodeJS10.24.1"}

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
                sh 'npm run build --port 3006'
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