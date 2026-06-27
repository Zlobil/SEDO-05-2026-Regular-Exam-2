 
pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout scmGit(
                    branches: [[name: '*/main']], 
                    extensions: [], 
                    userRemoteConfigs: [[url: 'https://github.com/Zlobil/SEDO-05-2026-Regular-Exam-2.git']]
                )
            }
        }

        stage('Restore Dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build Application') {
            steps {
                bat 'dotnet build --configuration Release'
            }
        }

        stage('Execute Tests') {
            steps {
                bat 'dotnet test --configuration Release'
            }
        }
    }
}
