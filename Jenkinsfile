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
      stage('Sonarqube'){
        steps{
          sh "${scannerHome}/bin/sonar-scanner"
        }
      }
    }
}
