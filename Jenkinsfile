pipeline {
     agent {
        go {
          label 'golang'
        }
     }

    stages {
        stage('Build') {
            steps {
                container('golang') {
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