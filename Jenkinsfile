pipeline {
  agent {
    node {
      label 'baseubuntu'
    }
  }

  parameters {
    string(name:'DOCKER_USERNAME',defaultValue: '',description:'')
    string(name:'DOCKER_PASSWORD',defaultValue: '',description:'')
  }

  stages {
    stage('baseubuntu hello') {
      steps {
        container('baseubuntu') {
          sh 'docker buildx use my-builder-proxy'
          sh 'docker login -u ${DOCKER_USERNAME} -p ${DOCKER_PASSWORD}'
          sh 'cd base-image && make -f Makefile build-alpine-edge'
        }
      }
     }
   }
}