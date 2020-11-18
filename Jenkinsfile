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
        stage ('Deploy-qa') {
            steps{
                sshagent(['tomcat_qa']) {
                    sh """
                        whoami
                        scp -ov StrictHostKeyChecking=no target/*war tomcat@10.128.0.3:/home/tomcat/apache-tomcat-8.5.59/webapps/
                        ssh tomcat@10.128.0.3 /home/tomcat/apache-tomcat-8.5.59/shutdown.sh
                        ssh tomcat@10.128.0.3 /home/tomcat/apache-tomcat-8.5.59/startup.sh
                    
                    """
                        }  
                 }
        }
    }
}
