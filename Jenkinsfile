#!groovy
pipeline{
  agent {label "master"}
    stages
      {
        stage('Docker Build') 
         {
    	      steps 
           {
      	     print("building docker image") 
             sudo chmod 777 /var/run/docker.sock
             sh 'docker build -t pav537/cs2:latest .'
      }
    }
  }
}
