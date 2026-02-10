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
                echo 'Construction du projet avec Maven...'
                bat 'mvnw.cmd clean package -DskipTests'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Exécution des tests...'
                bat 'mvnw.cmd test'
            }
        }
        
        stage('Archive') {
            steps {
                echo 'Archivage de l\'artifact...'
                archiveArtifacts artifacts: 'target/*.jar', allowEmptyArchive: true
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline exécuté avec succès! ✅'
        }
        failure {
            echo 'Le pipeline a échoué. ❌'
        }
        always {
            echo 'Build terminé.'
        }
    }
}
