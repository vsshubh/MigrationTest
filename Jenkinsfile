pipeline {
  agent any

  tools {
    maven 'MAVEN'
    jdk 'JDK'
  }

  stages {
    stage('Checkout') {
      steps{
        git branch: 'master', url:'https://github.com/vsshubh/MigrationTest.git'
      }
    }
    stage('Build & Test') {
      steps{
        sh 'mvn clean install'
      }
    }
    stage('Run Application') {
      steps{
        sh 'java -jar build/libs/MigrationApp-1.0-SNAPSHOT.jar'
      }
    }
  }
  post {
    success {
      echo 'Pipeline successfull!'
    }
    failure {
      echo 'Pipeline failed'
    }
  }
}
