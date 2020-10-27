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
                        sh 'npm run test'
                        echo 'test ended'
                    }
                }
      stage('Sonarqube'){
        steps{
          sh 'sonar-scanner'
        }
      }
    }
}
