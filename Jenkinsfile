pipeline {
  agent any
  stages {
    stage('Compile') {
      steps{
        sh 'mvn clean compile'
      }
    }

    stage('UnitTest') {
      steps{
        sh 'mvn clean test'
      }
    }
    
    stage('Package') {
      steps{
        sh 'mvn package'
     }
    }

    stage('Deliver') {
      steps{
        deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://34.235.116.156:9090/')], contextPath: null, war: 'target/calculator.war'
     }
    }    
  }
}
