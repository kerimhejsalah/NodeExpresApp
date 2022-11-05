def dockerimage
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
        stage('Build image with docker') {
             steps{
                script{
                   
                   dockerImage = docker.build("hajsalahkarim/myproject")
                    
                }
             }
                    
          }
        stage('Push image') {
            steps{
                script{
           
                      withCredentials([usernamePassword( credentialsId: 'docker-hub', usernameVariable: 'hajsalahkarim', passwordVariable: 'Azertyazerty123@')])
               {
                    dockerImage.push()
                    
              }
               }
             }
        }
        
        
        /*stage('Docker Build and Push'){
            steps{
                withDockerRegistry([credentialsId: "docker-hub", url:""]){
                    //sh 'printenv'
                    sh 'docker build -t karydock/appnode-oct:""$GIT_COMMIT"" .'
                    sh 'docker push karydock/appnode-oct:""$GIT_COMMIT"" '
                }
            }
            
        }*/
        
         
        
    }
}
