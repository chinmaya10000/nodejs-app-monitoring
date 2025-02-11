pipeline {
  agent any

  stages {
    stage('s1-any-agent') {
      steps {
        script {
          sh 'cat /etc/os-release'
          sh 'node -v'
          sh 'npm -v'
        }
      }
    }
    stage('s2-my-agent') {
      agent {
        label 'slave-1'
      }
      steps {
        script {
          sh 'cat /etc/os-release'
          sh 'node -v'
          sh 'npm -v'
        }
      }
    }
  }
}
