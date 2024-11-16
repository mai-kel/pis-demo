pipeline {
    agent any

    // tools {
    //     // Deklaracja wersji JDK i Mavena
    //     jdk 'Java 17'        // Wymaga zdefiniowanej wersji w Jenkinsie
    //     maven 'Maven 4.0.0'   // Wymaga zdefiniowanej wersji w Jenkinsie
    // }

    environment {
            MAVEN_HOME = 'E:\\maven\\apache-maven-3.8.8' // Ścieżka do zainstalowanego Mavena
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
                    bat 'mvn clean install' // Użycie bat dla komendy powłoki w systemie Windows
                }
            }
        }

        stage('Package') {
            steps {
                // Tworzenie paczki
                script {
                    bat 'mvn package' // Użycie bat dla komendy powłoki w systemie Windows
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
