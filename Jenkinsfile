pipeline{

    agent any

    stages{
        stage("Install dependencies") {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps{
                bat "dotnet restore"
            }
        }
        stage("Build application") {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Run tests") {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps{
                bat "dotnet test --no-restore --no-build"
            }
        }
    }
}
