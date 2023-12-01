pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh '#./mvnw package'
            echo 'Build complete'
          }
        }

        stage('Test Ansible') {
          steps {
            sh 'ansiblePlaybook credentialsId: \'devops2\', disableHostKeyChecking: true, installation: \'Ansible\', playbook: \'/etc/ansible/playbook.yaml\', vaultTmpPath: \'\''
          }
        }

      }
    }

  }
}