pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/Harshita100/CC_Lab-6.git'
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Build successful"'
            }
        }
    }
}
