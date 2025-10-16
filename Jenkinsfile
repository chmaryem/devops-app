pipeline {
    agent any

    tools {
        maven 'M3'
    }

    stages {
        stage('Checkout') {
            steps {
                echo '--- Clonage du dépôt Git ---'
                git branch: 'main', url: 'https://github.com/chmaryem/devops-app.git'
            }
        }

        stage('Build') {
            steps {
                echo '--- Étape de build ---'
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo '--- Lancement des tests ---'
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo '--- Déploiement ---'

            }
        }

        stage('Scan') {
            steps {
                withSonarQubeEnv('devops') {
                    bat 'mvn sonar:sonar -Dsonar.projectKey=devops-app'
                }
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline terminé avec succès !'
        }
        failure {
            echo '❌ Pipeline échoué !'
        }
    }
}