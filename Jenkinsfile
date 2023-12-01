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
            sh 'cd /etc/ansible; ls; ansible-playbook /etc/ansible/playbook.yml credentialsId: \'devops2\', disableHostKeyChecking: true, installation: \'Ansible\',  vaultTmpPath: \'\''
          }
        }

      }
    }

  }
}