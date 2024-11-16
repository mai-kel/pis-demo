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
                mvn clean install // Use 'mvn clean install' if using Maven
            }
        }
        // stage('Test') {
        //     steps {
        //         sh './gradlew test' // Use 'mvn test' if using Maven
        //     }
        // }
        stage('Package') {
            steps {
                 mvn package // Use 'mvn package' if using Maven
            }
        }
        // stage('Deploy') {
        //     steps {
        //         // Add your deployment steps here, e.g., using SCP, SSH, Docker, etc.
        //         sh 'scp build/libs/*.jar builded/'
        //     }
        // }
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
