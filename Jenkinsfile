pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building project...'
                // your build commands here, e.g., mvn clean package
            }
        }

        stage('Deploy') {
            steps {
                echo 'Preparing deploy folder...'

                // Step 1: create deploy folder safely
                bat '''
                if not exist deploy (
                    mkdir deploy
                )
                '''

                echo 'Deploy folder ready!'

                // Step 2: copy build artifacts to deploy folder
                bat 'copy target\\*.jar deploy\\'

                echo 'Artifacts copied to deploy folder.'

                // Optional: Step 3 - deploy to server or archive
                // e.g., archiveArtifacts artifacts: 'deploy/', fingerprint: true
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
