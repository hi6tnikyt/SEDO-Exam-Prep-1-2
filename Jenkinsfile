pipeline {
    agent any
    
    stages {
        stage("Dotnet restore") {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                sh "dotnet restore"
            }
        }
        
        stage("Dotnet build") {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                sh "dotnet build --no-restore"
            }
        }
        
        stage("Dotnet test") {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
}