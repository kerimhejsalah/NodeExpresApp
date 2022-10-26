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
        /* stage('Test') {
          steps {
            sh 'npm test'
          }
        }*/
        
        stage('Docker Build and Push'){
            steps{
                withDockerRegistry([credentialsId: "docker-hub", url:""]){
                    sh 'printenv'
                    sh 'docker build -t karydock/appnode-oct:""$GIT_COMMIT"" .'
                    sh 'docker push karydock/appnode-oct:""$GIT_COMMIT"" '
                }
            }
            
        }
        
         
        
    }
}
