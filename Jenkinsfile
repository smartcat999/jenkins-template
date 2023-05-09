pipeline {
  agent {
    node {
      label 'baseubuntu'
    }
  }

  stages {
    stage('baseubuntu hello') {
      steps {
        container('baseubuntu') {
          sh 'cd base-image && make -f Makefile build-alpine-edge'
        }
      }
     }
   }
}