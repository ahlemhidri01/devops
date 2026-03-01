pipeline {
    agent any
    
    stages {
        
        stage('GIT') {
            steps {
                echo "Getting Project from Git"
                git branch: 'main', url: 'https://github.com/ahlemhidri01/devops.git'
            }
        }
        
        stage('MVN CLEAN') {
            steps {
                sh 'chmod +x mvnw'
                sh './mvnw clean'
            }
        }
        
        stage('MVN COMPILE') {
            steps {
                sh './mvnw compile'
            }
        }
        
        stage('MVN SONARQUBE') {
            steps {
                sh './mvnw sonar:sonar \
                    -Dsonar.host.url=http://192.168.50.4:9000 \
                    -Dsonar.login=admin \
                    -Dsonar.password=sonar'
            }
        }
    }
}
