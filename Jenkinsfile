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
           sh "sonar:sonar \
  -Dsonar.projectKey=aaa \
  -Dsonar.host.url=http://13.71.82.249:9000 \
  -Dsonar.login=2dc37ea543c64738ca801f108ce76b09eae51ee1
  -Dsonar.language=py"
            
            }  
        }
      }
}
