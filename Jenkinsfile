pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                git 'https://github.com/VootlaSaiCharan/mern-application-ec2.git'
            }
        }
        stage('Installing Dependencies and Running the Frontend application') {
            steps {
                sh 'cd registration-mern-app && rm -rf node_modules && npm install && nohup npm start &'
            }
        }
        stage('Install Dependencies and Running the Backend application') {
            steps {
                sh 'cd registration-server && npm install && nohup npm start &'
            }
        }
    }
}
