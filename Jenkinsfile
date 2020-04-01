pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        //bat 'mvn clean'
        bat 'C:\\Program~s\\apache-maven-3.6.3\\bin\\mvn compile'
      }
    }
    stage('Test') {
      steps {
        bat 'C:\\Program Files\\apache-maven-3.6.3\\bin\\mvn test'
      }
    }
    stage('Deploy') {
      steps {
        bat 'C:\\Program Files\\apache-maven-3.6.3\\bin\\mvn package'
      }
    }
  }
  post {
    always {
        emailext body: 'Current Build Failed. Please Review It.', to: 'vigneshsubramani28@gmail.com,dondom828@gmail.com' , subject: 'Build Failed'
    }
  }
}
