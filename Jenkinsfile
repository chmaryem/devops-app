pipeline {
    agent any

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
            }
        }

        stage('Test') {
            steps {
                echo '--- Lancement des tests ---'
            }
        }

        stage('Deploy') {
            steps {
                echo '--- Déploiement ---'
            }
        }


        stage('SonarQube Analysis') {
                    steps {
                        withSonarQubeEnv('devops') {  // Nom exact de ton installation
                            bat 'mvn sonar:sonar'
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
