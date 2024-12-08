      // This adds install and test stages before static code analysis
pipeline {
  agent any

  stages {
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'Sonarqube-scanner'
        }
        steps {
            withSonarQubeEnv('sonarqube-localhost') {        
              sh "${scannerHome}/bin/sonar-scanner"
        }
    }
    }
  }
}