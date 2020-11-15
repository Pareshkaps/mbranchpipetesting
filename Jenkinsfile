pipeline {
    agent any
    stages {
        stage('Git-checkout') {
            steps { 
                git branch: 'main', credentialsId: 'mbranchpipetesting-creds', url: 'https://github.com/Pareshkaps/mbranchpipetesting.git'
            }
        }
    }
}
