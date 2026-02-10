pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Récupération du code depuis GitHub...'
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                echo 'Construction du projet...'
                // Ajoutez vos commandes de build
            }
        }
        
        stage('Test') {
            steps {
                echo 'Exécution des tests...'
                // Ajoutez vos commandes de test
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline exécuté avec succès!'
        }
        failure {
            echo 'Le pipeline a échoué.'
        }
    }
}
