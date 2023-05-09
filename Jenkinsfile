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
    stage('build alpine base-image') {
      steps {
        container('baseubuntu') {
          sh 'echo ${DOCKER_PASSWORD} | docker login -u ${DOCKER_USERNAME} --password-stdin'
          sh 'cd base-image && make -f Makefile build-alpine-edge'
        }
      }
     }
   }
}