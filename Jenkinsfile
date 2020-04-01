pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        //bat 'mvn clean'
        bat 'C:\Program Files\apache-maven-3.6.3\bin compile'
      }
    }
    stage('Test') {
      steps {
        bat 'C:\Program Files\apache-maven-3.6.3\bin test'
      }
    }
    stage('Deploy') {
      steps {
        bat 'C:\Program Files\apache-maven-3.6.3\bin package'
      }
    }
  }
  post {
    always {
        emailext body: 'Current Build Failed. Please Review It.', to: 'vigneshsubramani28@gmail.com,dondom828@gmail.com' , subject: 'Build Failed'
    }
  }
}
