pipeline {
    agent any

    environment {
        FIREBASE_TOKEN = credentials('FIREBASE_TOKEN')
    }

    stages {
        stage('Install Firebase CLI') {
            steps {
                sh 'npm install -g firebase-tools'
            }
        }
        stage('Build (not needed for HTML)') {
            steps {
                echo 'No build step needed, static site'
            }
        }
        stage('Deploy') {
            steps {
                sh "firebase deploy --token $FIREBASE_TOKEN"
            }
        }
    }
}
