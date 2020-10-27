pipeline {
  agent any
  tools {nodejs "node"}
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
      stage('Test') {
                    steps {
                        echo 'test started'
                        echo 'test ended'
                    }
                }
     
    stage('SonarQube analysis') {
      steps {
        script {
          // requires SonarQube Scanner 2.8+
          scannerHome = tool 'sonar'
        }
        withSonarQubeEnv('SonarQube Scanner') {
          sh "${scannerHome}/bin/sonar-scanner"
           }
        }
      }
  
    }
}
