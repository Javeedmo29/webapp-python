pipeline {
   agent any
tools {
    maven 'SampleMaven'
    jdk 'JDK1.8'
  }
   stages {
      stage('BUILD') {
           steps {
           
           sh "mvn -B -DskipTests clean install"
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
