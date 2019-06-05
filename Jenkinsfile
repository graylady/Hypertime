pipeline {
    agent  any
    tools {nodejs "node"}
       
    stages {
        stage('install dependencies') { 
            steps {
                sh 'cd hypertime-frontend && npm install && cd ..' 
                sh 'cd hypertime-e2e && npm install && cd ..'
            }
        }
        stage('Lintify') { 
            steps {
                sh 'cd hypertime-frontend && npm run lint:eslint && cd ..' 
            }
            
        }
        stage('Build production files') { 
            steps {
                sh 'cd hypertime-frontend && npm run build && cd ..' 
                sh 'cd hypertime-e2e && npm run build && cd ..' 
            }
        }
        stage('Test'){
            steps {
                sh 'cd hypertime-frontend && npm run test && cd ..'
            }
        }
        stage('Deploy'){
            steps {
                echo 'Deploying.....'
        }
    }
}
}