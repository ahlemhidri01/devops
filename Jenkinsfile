pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Récupération du code depuis GitHub...'
                git branch: 'main', url: 'https://github.com/ahlemhidri01/devops.git'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Construction du projet avec Maven Wrapper...'
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
