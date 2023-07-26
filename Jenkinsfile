#!groovy
pipeline{
  agent master
 stages {
    stage('Docker Build') {
    	agent any
      steps {
      	sh 'docker build -t pav537/cs2:latest .'
      }
    }
  }
}
