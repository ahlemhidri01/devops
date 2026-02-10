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
                sh 'chmod +x mvnw'
                sh './mvnw clean package -DskipTests'
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
