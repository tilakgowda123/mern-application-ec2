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
                // Start the frontend application in the background and detach it from the shell
                sh '''
                    cd registration-mern-app
                    nohup npm start > frontend.log 2>&1 &
                    disown
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
                // Start the backend application in the background and detach it from the shell
                sh '''
                    cd registration-server
                    nohup npm run dev > backend.log 2>&1 &
                    disown
                '''
            }
        }
    }
}