pipeline {
    agent any
    tools {
        maven "MAVEN3"
    }
    environment
    {
        DOCKERHUB_PWD=credentials('CredentialID_DockerHubPWD)
    }
                       
stages {
    stage("Check out) {
          steps {
              git branch: 'main', url: 'https://github.com/joshuatimbol/Lab2DevOpsQ3'
          }
          
    }
          
          stage("Build maven project") {
              steps { 
                  sh 'mvn clean install'
              }
          }
          
          stage("Unit test") {
              steps {
                  sh "mvn test"
              }
          }
          
          stage ("Docker build") {
              steps {
                  script {
                      sh 'docker build -t
    
}
                                      
