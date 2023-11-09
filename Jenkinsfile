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
      steps {
        sh '''mvn clean verify sonar:sonar 






-Dsonar.projectKey=devops -Dsonar.host.url=http://localhost:9000 -Dsonar.token=sqp_ddff216d7cd0e2101aa88a5ff151a33f3705fe47
'''
      }
    }

  }
}