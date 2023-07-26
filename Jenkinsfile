#!groovy
pipeline{
  agent {label "master"}
    environment {
    DOCKERHUB_CREDENTIALS = credentials('dockerhun')
  }
    stages
      {
        stage('Docker Build') 
         {
    	      steps 
           {
      	     print("building docker image") 
             sh "sudo chmod 777 /var/run/docker.sock"
             sh "docker build -t pav537/cs2:latest ."
      }
    }
    stage('Login') {
        steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
      }
    }
    stage('Push') {
      steps {
        sh "docker push pav537/cs2"
      }
    }
     stage('create nodeport service')
        {
          steps {
            sh "kubectl create -f kubernetes.yml"
          }
        }

  }
  post {
    always {
      sh 'docker logout'
    }
  }
}
