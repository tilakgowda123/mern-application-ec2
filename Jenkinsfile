pipeline {
    agent any
    
    stages {
        stage('clone') {
            steps {
                git 'https://github.com/VootlaSaiCharan/mern-application-ec2.git'
            }
        }
        stage('enter in to the project') {
            steps {
                sh 'cd registration-mern-app'
            }
        }
        stage('Installing Dependencies in Frontend application') {
            steps {
                sh 'npm install'
            }
        }
        stage('Running the Frontend application') {
            steps{
                sh 'npm start'
            }
        }
        stage('Install Dependencies in Backend application') {
            steps{
                sh 'cd ../registration-server/'
                sh 'npm install'
            }
        }
        stage('Run the Backend application') {
            steps{
                sh 'npm run dev'
            }
        }
    }
}