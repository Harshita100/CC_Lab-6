pipeline {
    agent any

    stages {

        stage('Build Backend Image') {
            steps {
                sh '''
                docker build -t backend-app ./backend
                '''
            }
        }

        stage('Deploy Backend') {
            steps {
                sh '''
                docker rm -f backend1 backend2 || true
                docker run -d --name backend1 backend-app
                '''
            }
        }

        stage('Build NGINX Image') {
            steps {
                sh '''
                docker build -t nginx-lb ./nginx
                '''
            }
        }

        stage('Deploy NGINX') {
            steps {
                sh '''
                docker rm -f nginx-lb || true
                docker run -d \
                  --name nginx-lb \
                  -p 80:80 \
                  nginx-lb
                '''
            }
        }
    }
}
