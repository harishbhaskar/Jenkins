pipeline {
   
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
               echo 'hello'
            }
        }
       stage('Sonar Analysis'){
          steps {
         withSonarQubeEnv('sonar01'){
            sh 'mvn sonar:sonar'
         }
         }
       }
    }
}
