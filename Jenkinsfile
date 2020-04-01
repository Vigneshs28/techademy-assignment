pipeline {
  agent any
  stages {
    stage('Build') {
      steps { 
        bat 'set -m MAVEN_HOME "C:\\Programe Files\\apache-maven-3.6.3\\bin"'
        bat 'mvn clean'
        bat 'C:\\apache-maven-3.6.3\\bin\\mvn compile'
      }
    }
    stage('Test') {
      steps {
        bat 'C:\\apache-maven-3.6.3\\bin\\mvn test'
      }
    }
    stage('Deploy') {
      steps {
        bat 'C:\\apache-maven-3.6.3\\bin\\mvn package'
      }
    }
  }
  post {
    always {
        emailext body: 'Current Build Failed. Please Review It.', to: 'vigneshsubramani28@gmail.com,dondom828@gmail.com' , subject: 'Build Failed'
    }
  }
}
