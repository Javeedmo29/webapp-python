pipeline {
    environment {
     registry = "arkakundu1407/docker-pipeline"
     registryCredential = 'dockerhub'
     dockerImage = ''
     containerId = sh(script: 'docker ps -aqf "name=node-app"',returnStdout: true)
   }
    agent any
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'python:2-alpine' 
                }
            }
            steps {
                sh 'python -m py_compile app.py' 
            }
        }
        stage('Sonar Sacnner')
        {
            steps {  
           sh 'sonar-scanner \
  -Dsonar.projectKey=ddd \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://13.71.113.179:9000 \
  -Dsonar.login=81866269906b1bcc1e5cda2d1437c5d2ca9439e4'
            
            }  
        }
      }
}
