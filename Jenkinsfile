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
           sh "mvn sonar:sonar \
  -Dsonar.projectKey=aaa \
  -Dsonar.host.url=http://13.71.113.179:9000 \
  -Dsonar.login=5f8a902396e8045221c9bab75140d37787c37359"
            
            }  
        }
      }
}
