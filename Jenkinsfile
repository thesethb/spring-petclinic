pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
        echo 'Build complete'
      }
    }

  }
}