pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/mai-kel/pis-demo'
            }
        }
        stage('Build') {
            steps {
                mvn 'clean install' // Use 'mvn clean install' if using Maven
            }
        }

        stage('Package') {
            steps {
                 mvn 'package' // Use 'mvn package' if using Maven
            }
        }

    }

    post {
        success {
            echo 'Build and Deploy succeeded!'
        }
        failure {
            echo 'Build or Deploy failed!'
        }
    }
}
