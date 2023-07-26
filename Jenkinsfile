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
             sh 'docker build -t pav537/cs2:latest .'
      }
    }
  }
}
