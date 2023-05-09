pipeline {
  agent {
    node {
      label 'nodejs'
    }
  }

  stages {
    stage('nodejs hello') {
      steps {
        container('nodejs') {
          sh 'cd base-image && make -f Makefile build-alpine-edge'
        }
      }
     }
   }
}