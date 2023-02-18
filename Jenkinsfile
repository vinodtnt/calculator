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
        deploy adapters: [tomcat9(credentialsId: 'f79d5183-29ae-4bb6-9a2b-c1614e80a13a', path: '', url: 'http://34.235.116.156:8282/')], contextPath: null, war: 'target/calculator.war'
     }
    }    
  }
}
