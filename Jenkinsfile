pipeline {
    agent any

    stages {

         stage('Build in Docker') {
            steps {
                script {
                    docker.image('mcr.microsoft.com/dotnet/sdk:9.0').inside {
                        sh 'dotnet restore'
                        sh 'dotnet build -c Release'
                        sh 'dotnet test'
                        sh 'dotnet publish -c Release -o publish'
                    }
                }
            }
        }

    }
}
