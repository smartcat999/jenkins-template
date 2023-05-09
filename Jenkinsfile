pipeline {
  agent {
    node {
      label 'baseubuntu'
    }
  }

  parameters {
    string(name:'DOCKER_USERNAME',defaultValue: '',description:'')
  }

  stages {
    stage('baseubuntu hello') {
      steps {
        container('baseubuntu') {
          sh 'docker buildx use my-builder-proxy'
          sh 'cd base-image && make -f Makefile build-alpine-edge'
        }
      }
     }
   }
}