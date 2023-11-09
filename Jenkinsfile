pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean install'
        echo 'Build complete'
      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh '''mvn clean verify sonar:sonar 






-Dsonar.projectKey=devops2 -Dsonar.projectName=\'devops2\''''
          }
        }

        stage('Deploy') {
          steps {
            sh 'java -jar target/*.jar'
          }
        }

      }
    }

  }
}