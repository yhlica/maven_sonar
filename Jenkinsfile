pipeline {
        agent any
        stages {
                 stage("prepare") {
                steps {
                 sh 'cat .scannerwork/report-task.txt'
                  // copy to a properties file so we can ingest as variables
                 sh 'cp .scannerwork/report-task.txt .scannerwork/report-task.properties'
                }
                 }
                
          stage("build & sonarqube") {
            steps {
              withSonarQubeEnv('Sonarqube_server') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
        }
      }
