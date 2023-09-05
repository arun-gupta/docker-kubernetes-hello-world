pipeline {
  agent any
  stages {
    stage('stage1') {
      steps {
        echo 'This is buid number ${BUILD_NUMBER} of Hello-world-with-Docker-Kubernetes ${Hello}'
        sh 'echo "This is buid number ${BUILD_NUMBER} of Hello-world-with-Docker-Kubernetes ${Hello}"'
      }
    }

  }
  environment {
    Hello = '1'
  }
}