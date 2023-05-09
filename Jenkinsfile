pipeline {
     agent {
        docker {
          label 'go'
        }
     }

    stages {
        stage('Build') {
            steps {
                container('go') {
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