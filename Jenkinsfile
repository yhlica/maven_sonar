pipeline {
        agent any
        stages {
         
          stage("build & sonarqube") {
            steps {
              withSonarQubeEnv('Sonarqube_server') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
        }
      }
