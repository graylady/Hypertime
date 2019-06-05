pipeline {
    agent  any
    tools {nodejs "node"}
       
    stages {
        stage ('Build') {
             stages{
                 stage ('install dependencies') { 
                    steps {
                      sh 'cd hypertime-frontend && npm install && cd ..' 
                       }
             }
                 stage('Build dist files') { 
                    steps {
                         sh 'cd hypertime-frontend && npm run build && cd ..' 
                    }
            
                }
            }
        }
        stage('Test') { 
            steps {
                sh 'cd hypertime-frontend && npm run test' 
               
            }
        }   
    }
}