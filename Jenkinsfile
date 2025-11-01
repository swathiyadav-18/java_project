pipeline {
    agent any
    tools {
        maven 'Maven3' // Name of Maven installation in Jenkins
        jdk 'JDK11'   // Name of JDK installation in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project with Maven...'
                bat 'mvn clean install'
            }
        }
        stage('Run') {
            steps {
                echo 'Running the Spring Boot app...'
                bat 'mvn spring-boot:run -Dspring-boot.run.arguments=--server.port=9090'

            }
        }
    }
}
