pipeline {
    agent any

    stages {
        stage('CHECKOUT') {
            steps {
                echo ' checking out'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                
                withSonarQubeEnv('sonarqube') {
                sh 'pytest -v' sonar-scanner
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
