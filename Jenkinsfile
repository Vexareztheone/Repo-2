pipeline{
    agent any
    stages{
        stage("Restore"){
            when {
                anyOf {
                    branch "main"
                    branch "develop"
                }
            }
            steps{
                bat "dotnet restore"
            }
            
        }
        stage("Build the app"){
            when {
                anyOf {
                    branch "main"
                    branch "develop"
                }
            }
            steps{
                bat "dotnet build --no-restore"
            }
            
        }
        stage("Run tests"){
            when {
                anyOf {
                    branch "main"
                    branch "develop"
                }
            }
            steps{
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}