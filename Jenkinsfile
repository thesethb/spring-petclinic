pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh './mvnw package'
            echo 'Build complete'
          }
        }

        stage('Test Ansible') {
          steps {
            sh 'ansible-playbook ~/etc/ansible/playbook.yaml'
          }
        }

      }
    }

  }
}