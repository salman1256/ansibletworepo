pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/salman1256/ansibletworepo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-app2:latest ./app'
            }
        }

      stage('Run Container') {
            steps {
                bat '''
                docker rm -f myapp2 || true
                docker run -d -P --name myapp2 my-app2:latest
                '''
            }
        }

    }
}