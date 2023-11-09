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
            sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=devops2 \\
  -Dsonar.projectName=\'devops2\' \\
  -Dsonar.host.url=http://localhost:9000 \\
  -Dsonar.token=sqp_2890044f11c5fb9ac229b946c818b4097393bb39'''
          }
        }

        stage('Deploy') {
          steps {
            sh 'cd target'
            sh 'ls'
            sh 'java -jar *.jar'
          }
        }

      }
    }

  }
}