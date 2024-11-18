pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/https://github.com/SabaHm123/springAngular.git'
            }
        }
        stage('Build Angular') {
            steps {
                dir('angular') {
                    sh 'npm install'
                    sh 'npm run build --prod'
                }
            }
        }
        stage('Build Backend') {
            steps {
                dir('springboot') {
                    sh './mvnw package'
                }
            }
        }
        stage('Docker Build and Push') {
            steps {
                sh 'docker-compose build'
                sh 'docker-compose up -d'
            }
        }
    }
}
