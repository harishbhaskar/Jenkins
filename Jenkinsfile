pipeline {
   
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
               echo 'hello'
               echo 'hello'
            }
        }
       stage('Sonar Analysis'){
          steps {
         withSonarQubeEnv('sonar'){
            sh 'mvn sonar:sonar'
         }
         }
       }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
