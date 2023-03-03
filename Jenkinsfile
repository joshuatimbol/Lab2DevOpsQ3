pipeline {
    agent any

    stages {
        
        stage('Checkout') {
            steps {
                git branch: 'main',
                    credentialsId: 'GitHub-PAT',
                    url: 'https://github.com/joshuatimbol/Lab2DevOps301068352.git'
                echo "Jenkins URL: ${env.JENKINS_URL}" 
                echo "Build ID: ${env.BUILD_ID}"
            }
        }
        
        stage('Build maven project') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
