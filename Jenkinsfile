pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', credentialsId: 'GitHub-Token', 
                url: 'https://github.com/jeatorresr/TercerPunto.git'
            }
        }
    }
}