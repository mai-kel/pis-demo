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
                    bat 'set M2_HOME=E:\\maven\\apache-maven-3.8.8'
                    bat 'set path=E:\\maven\\apache-maven-3.8.8\\bin;%path%'
                    bat 'mvn clean install' // Użycie bat dla komendy powłoki w systemie Windows
                }
            }
        }

        stage('Package') {
            steps {
                // Tworzenie paczki
                script {
                    bat 'set M2_HOME=E:\\maven\\apache-maven-3.8.8'
                    bat 'set path=E:\\maven\\apache-maven-3.8.8\\bin;%path%'
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
// test
