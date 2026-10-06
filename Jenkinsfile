   pipeline {
       agent any
       stages {
           stage('Checkout') {
               steps {
                   checkout scm
               }
           }
           stage('SonarQube Analysis') {
               steps {
                   script {
                       def scannerHome = tool 'SonarQube Scanner'
                       withSonarQubeEnv('SonarQube') {
                           bat "\"${scannerHome}\\bin\\sonar-scanner.bat\" -Dsonar.projectKey=Jenkins-Practice -Dsonar.sources=."
                       }
                   }
               }
           }
       }
   }
