pipeline {
  agent any
  stages {
    stage('Version') {
      steps {
        sh 'mvn -version'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }

  }
  tools {
    maven 'm38'
  }
}