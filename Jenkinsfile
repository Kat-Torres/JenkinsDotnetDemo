pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            agent {
                docker {
                    image 'mcr.microsoft.com/dotnet/sdk:9.0'
            }
        }

       steps {
                sh 'dotnet restore'
                sh 'dotnet build --configuration Release'
             }
         }
      }
}
