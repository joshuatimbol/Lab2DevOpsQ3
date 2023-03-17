pipeline {
    agent any
    tools {
        maven "MAVEN3"
    }
    environment
    {
        DOCKERHUB_PWD=credentials('CredentialID_DockerHubPWD')
    }
                       
stages {
    stage("Check out") {
          steps {
              git branch: 'main', url: 'https://github.com/joshuatimbol/Lab2DevOpsQ3'
          }
          
    }
          
          stage("Build maven project") {
              steps { 
                  sh 'mvn clean install'
              }
          }

            stage ("Docker build") {
                steps {
                  script {
                      sh 'docker build -t timbol/lab3:1.0 .'
                  }
              }
          }
          
            stage ("Docker Login") {
                steps {
                    script {
                        sh 'docker login -u timbol -p ${DOCKERHUB_PWD}'
                    }
                }
          }

          stage ("Docker push") {
                steps {
                    script {
                        sh 'docker push timbol/lab3:1.0'
                    }
                }
          }

          
    
}
                                      
