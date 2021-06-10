pipeline {
    agent any
    
    tools {nodejs "nodejs"}
    
    options {
        ansiColor('xterm')
    }
    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', credentialsId: 'GitHub-Token', 
                url: 'https://github.com/jeatorresr/TercerPunto.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                sh 'npm run test'
            }
        }
        stage('Deploy to AWS') {
            steps {
                sh 'ls'
            }
        }
    }
}
