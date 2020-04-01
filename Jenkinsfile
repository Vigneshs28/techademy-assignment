pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'setx -m JAVA_HOME "C:\Program Files\Java\jdk1.8.0_191"'
        bat 'C:\\apache-maven-3.6.3\\bin\\mvn clean'
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
