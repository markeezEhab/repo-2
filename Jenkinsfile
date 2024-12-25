pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'dotnet build SOAPService.sln'
                sh 'dotnet build RESTApi.sln'
                sh 'dotnet build GrpcService.sln'
            }
        }
        stage('Test') {
            steps {
                sh 'dotnet test'
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker-compose build'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}
