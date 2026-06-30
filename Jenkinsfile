pipeline {
    agent any

    stages {

        stage('Build') {
    steps {
        sh '''
        docker run --rm -v $PWD:/app -w /app mcr.microsoft.com/dotnet/sdk:9.0 \
        dotnet build -c Release
        '''
    }
}

        stage('Test') {
            steps {
                sh 'dotnet test'
            }
        }

        stage('Publish') {
            steps {
                sh 'dotnet publish -c Release -o publish'
            }
        }

    }
}
