pipeline {
    agent any

    stages {
        stage('Build Demo') {
            steps {
                echo "Running demo build..."
            }
        }
    }

    post {
        success {
            emailext(
                subject: "Jenkins Build Success!",
                body: "Your Jenkins build of the demo project finished successfully.",
                to: "lodgymagdy1@gmail.com"
            )
        }
        failure {
            emailext(
                subject: "Jenkins Build FAILED!",
                body: "Your Jenkins build has failed.",
                to: "lodgymagdy1@gmail.com"
            )
        }
    }
}
