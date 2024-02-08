pipeline {
   agent {
       label "docker-agent-python"
  }
  tools{
    'sonar-scanner'
  }      
    
    stages {       
         stage('CHECK OUT') {
            steps {
               checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/emk-github-organization/sonarqube-test.git/']]])       
            }
        }    
      
         stage('RUN TEST') {
            steps {
               sh 'pytest -v'
            }
         }
/*
       stage('SonarQube Analysis') {
            steps {
               withSonarQubeEnv('sonarqube') {
                 sh "${scannerHome}/bin/sonar-scanner"
            }
         }
                
        stage('slack notification sent'){
           steps{
               echo ' sending slack notification....'
               echo 'Slack notification sent'               
           }
         }  
         */
    }    
}



/*
node ("docker-agent-python") {
  stage('SCM') {
    git branch: 'main', url: ' https://github.com/emk-github-organization/sonarqube-test.git'
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'sonar-scanner';
    withSonarQubeEnv('sonarqube') {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
*/




