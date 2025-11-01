pipeline {
    agent any

    tools {
        jdk 'JDK11'     // Make sure Jenkins has a JDK installation named 'JDK17'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Compile') {
            steps {
                echo 'Compiling Java program...'
                bat '''
                    mkdir -p target
                    javac -d target src/main/java/org/springframework/samples/petclinic/PetClinicApplication.java
                '''
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program...'
                bat 'java -cp target com.example.App'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}

