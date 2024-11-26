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
                // Use nohup and run npm start in the background
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
                // Use nohup and run npm run dev in the background
                sh '''
                    cd registration-server
                    nohup npm run dev > backend.log 2>&1 &
                '''
            }
        }
    }
}