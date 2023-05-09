pipeline {
     agent {
        base {
          label 'base'
        }
     }

    stages {
        stage('Build') {
            steps {
                container('base') {
                    echo 'Building..'
                    sh 'cd base-image && make -f Makefile build-alpine-edge'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}