def maven_home = "C:\\Program~1\\apache-maven-3.6.3\\bin"

pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        //bat 'mvn clean'
          bat "$maven_home\\mvn compile"
      }
    }
    stage('Test') {
      steps {
        bat "$maven_home\\mvn test"
      }
    }
    stage('Deploy') {
      steps {
        bat "$maven_home\\mvn package"
      }
    }
  }
  post {
    always {
        emailext body: 'Current Build Failed. Please Review It.', to: 'vigneshsubramani28@gmail.com,dondom828@gmail.com' , subject: 'Build Failed'
    }
  }
}
