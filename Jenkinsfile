pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Récupération du code depuis GitHub...'
                checkout scm
            }
        }

        stage('Build & Run HelloWorld') {
            steps {
                sh 'javac HelloWorld.java'
                sh 'echo "--- Exécution de HelloWorld ---"'
                sh 'java HelloWorld'
            }
        }

        stage('Build & Run Merci') {
            steps {
                sh 'javac Merci.java'
                sh 'echo "--- Exécution de Merci ---"'
                sh 'java Merci'
            }
        }

        stage('Build & Run DeRien') {
            steps {
                sh 'javac DeRien.java'
                sh 'echo "--- Exécution de DeRien ---"'
                sh 'java DeRien'
            }
        }
    }

    post {
        always {
            echo 'Pipeline terminée !'
        }
        success {
            echo 'Tous les builds ont réussi !'
        }
        failure {
            echo 'Échec quelque part...'
        }
    }
}
