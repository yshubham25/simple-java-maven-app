pipeline {
    agent any

    tools {
        // Install the Maven version configured as "m38" and add it to the path.
        maven 'm38'
    }

    stages {
        stage('Version') {
            steps {

//the below line is valid only if we try to access through Jenkins UI PipeLine Script
               // git 'https://github.com/yshubham25/simple-java-maven-app'
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
}

