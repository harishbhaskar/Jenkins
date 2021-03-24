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
         withSonarQubeEnv('sonar01'){
            sh 'mvn sonar:sonar'}
       }
    }
}
}
