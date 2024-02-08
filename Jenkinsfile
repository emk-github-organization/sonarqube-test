
node {
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

