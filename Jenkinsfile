pipeline {
    agent any

    tools {
        maven "Maven"
        jdk "JDK-17"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ahlemhidri01/devops.git'
            }
        }

        stage('Build') {
            steps {
                sh '''
                export MAVEN_OPTS="--add-opens java.base/java.lang=ALL-UNNAMED"
                mvn clean package -Dmaven.test.skip=true
                '''
            }
        }
    }
}
