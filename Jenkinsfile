pipeline {
  agent any
  stages {
    def maven_home = "C:\\Program Files\\apache-maven-3.6.3\\bin"
    stage('Build') {
      steps {
        //bat 'mvn clean'
        dir(maven_home){
          bat 'mvn compile'
        }
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
