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
        archiveArtifacts 'target/my-app-*-SNAPSHOT.jar'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
        junit(testResults: 'target/surefire-reports/TEST-*.xml', keepProperties: true, keepTestNames: true)
      }
    }

  }
  tools {
    maven 'm38'
  }
}