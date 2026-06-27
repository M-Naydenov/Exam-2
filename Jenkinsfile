pipeline {
    agent any
    stages {

        stage('Restore Dependencies') {
            when {
                branch 'main'
            }
            steps {
                echo 'Restoring dependencies...'
                bat 'dotnet restore'
            }
        }
        stage('Dotnet build') {
            when {
                branch 'main'
            }
            steps {
                echo 'Building...'
                bat 'dotnet build --no-restore'
            }
        }
        stage('Test') {
            when {
                branch 'main'
            }
            steps {
                echo 'Testing...'
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}