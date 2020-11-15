pipeline {
    agent any
    
    tool {
        Maven 'MyMaven 3.6.3'
        Java 'MyJdk8'
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
