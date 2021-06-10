pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git credentialsId: 'GitHub-Token', 
                url: 'https://github.com/jeatorresr/TercerPunto.git'
            }
        }
    }
}