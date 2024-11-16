pipeline {
    agent any

    tools {
        // Deklaracja wersji JDK i Mavena
        maven 'Maven 3.8.8'   // Wymaga zdefiniowanej wersji w Jenkinsie
    }


    
    stages {
        stage('Checkout') {
            steps {
                // Klonowanie repozytorium
                git branch: 'master', url: 'https://github.com/mai-kel/pis-demo'
            }
        }

        stage('Build') {
            steps {
                // Kompilacja projektu
                script {                    
                    mvn clean install // Użycie bat dla komendy powłoki w systemie Windows
                }
            }
        }

        stage('Package') {
            steps {
                // Tworzenie paczki
                script {
                    mvn package // Użycie bat dla komendy powłoki w systemie Windows
                }
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
