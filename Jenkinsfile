pipeline {
    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')        
    } 

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
                sh 'aws s3 sync build s3://tercerpunto --delete'
            }
        }
        stage('Invalidate Cache') {
            steps {
                sh 'aws cloudfront create-invalidation --distribution-id "E1TD8XBADRO14I" --paths "/*"'
            }
        }
    }
}


