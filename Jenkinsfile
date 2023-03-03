pipeline {
    agent any

    stages {
        stage('Build maven project') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}