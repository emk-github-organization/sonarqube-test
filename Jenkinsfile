
node {
  stage('SCM') {
    git 'https://github.com/emk-github-organization/sonarqube-test.git'
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'sonar-scanner';
    withSonarQubeEnv('sonarqube') {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}

