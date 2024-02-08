pipeline {
    agent any

    stages {
        stage('CHECKOUT') {
            steps {
               checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/emk-github-organization/sonarqube-test.git']]])
            }
        }

        stage('SonarQube Analysis') {
            steps {
                
                withSonarQubeEnv('sonarqube') {
                //sh 'pytest -v' sonar-scanner
                     sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }

    }
}


/*
node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'sonar-scanner';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
*/
