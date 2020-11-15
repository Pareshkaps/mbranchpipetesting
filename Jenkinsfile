pipeline {
    agent any
    
    tools {
        maven "MyMaven"
    }
    stages {
        stage('Git-checkout') {
            steps { 
                git branch: 'main', credentialsId: 'mbranchpipetesting-creds', url: 'https://github.com/Pareshkaps/mbranchpipetesting.git'
            }
        }
        stage('Maven-build') {
            steps {
                sh "mvn clean package"
            }
        }
    }
}
