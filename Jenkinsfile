pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                
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
        
        
    }
    
}
