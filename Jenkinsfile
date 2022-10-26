pipeline {
    
     agent any
    
  tools {nodejs "NodeJS 18.4.0"}
    stages {
        
        stage('Deployer app node'){

          steps {
           echo 'test'
          }
        }
        
        stage('Build') {
          steps {
              
            sh 'npm --version'  
            sh 'npm install express'
            sh 'npm install mongo'
            sh 'npm install mocha -g'
            
          }
        }  
        stage('Test') {
          steps {
            sh 'npm test'
          }
    }
        
         
        
    }
}
