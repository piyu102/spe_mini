pipeline {
  agent any
  tools {nodejs "node"}
  stages {
    stage('Build') {
      steps {
        git 'https://github.com/piyu102/spe_mini.git'
        sh 'npm install'
      }
     }
    
    stage('Test') {
      steps {
       sh "chmod u+x test.sh" 
       sh './scripts/test.sh'
       }
    }
   stage('Deliver') {
    steps {
     sh "chmod u+x deliver.sh" 
     sh './scripts/deliver.sh'
      input message: 'Finished using the web site? (Click "Proceed" to continue)'
      sh './jenkins/scripts/kill.sh'
     }
    }
      
      
  }    
      
 }
