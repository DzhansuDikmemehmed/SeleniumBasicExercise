pipeline {
    agent any
    triggers{
        pollSCM('* * * * *')
    }
    stages {
        stage('Checkout'){
            steps{
                checkout scm
            }
        }
         stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        
                stage('Execute tests') {
                    steps {
                        bat 'dotnet test --no-build --verbosity normal'
                    }
                }
              
           
        
    }
}
