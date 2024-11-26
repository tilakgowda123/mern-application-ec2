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
                // Use nohup to run npm start in the background and redirect output to a log file
                sh '''
                    cd registration-mern-app
                    nohup npm start > frontend.log 2>&1 &
                '''
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
                sh 'cd registration-server && rm -rf node_modules && nohup npm run dev &'
            }
        }
    }
}