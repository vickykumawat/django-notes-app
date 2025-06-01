@Library('Shared@') _
pipeline{
    
    agent {label 'agent1'}
    
    stages{
        
         stage('Hello'){
            steps{
               script {
                   hello()
               }
            }
        }
        stage('Code'){
            steps{
             script{
                checkout('https://github.com/vickykumawat/django-notes-app.git', 'main')
                }
            }
        }
        stage('Build'){
           steps{
                script {
                    build('vickykumawat','notes-app','latest')
                }
            } 
        }
        stage('Push to DockerHub'){
          steps{
              script {
                  docker_push('vickykumawat','notes-app','latest','dockerhublogin')
              }  
            } 
        }
        
        stage('Deploy'){
            steps{
                script {
                    deploy()
                }
            }
        }
        
        
    }
}
