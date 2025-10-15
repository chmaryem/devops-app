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

                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo '--- Lancement des tests ---'
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo '--- Déploiement ---'

                sh 'echo Deploiement réussi !'
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
