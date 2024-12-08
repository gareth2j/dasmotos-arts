pipeline {
        agent any
        stages {
          stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('sonarqube-localhost') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
          stage("Quality Gate") {
            steps {
              timeout(time: 1, unit: 'HOURS') {
                waitForQualityGate abortPipeline: true
              }
            }
          }
        }
      }