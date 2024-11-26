pipeline {
    agent any
    
    stages {
        stage('clone') {
            steps {
                git 'https://github.com/VootlaSaiCharan/mern-application-ec2.git'
            }
        }
        stage('Installing Dependencies in Frontend application') {
            steps {
                sh 'cd registration-mern-app && rm -rf node_modules && npm install'
            }
        }
        stage('Running the Frontend application') {
            steps {
                // sh 'cd registration-mern-app && npm start'
                sh 'cd registration-mern-app && nohup npm start &'
            }
        }
        stage('Install Dependencies in Backend application') {
            steps {
                sh 'cd registration-server && npm install'
            }
        }
        stage('Run the Backend application') {
            steps {
                // sh 'cd registration-server && npm run dev'
                sh 'cd registration-server && nohup npm run dev &'
            }
        }
    }
}