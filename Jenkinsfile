pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
        echo 'Build complete'
      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh '''mvn clean verify sonar:sonar 






-Dsonar.projectKey=devops2 -Dsonar.projectName=\'devops2\' -Dsonar.token=sqb_923f1abc85545789f0792c1cc22de9bf4e6f12b2'''
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