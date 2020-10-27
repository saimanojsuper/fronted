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
     
    stage('sonar-scanner') {
      steps {
        script {
          sonarqubeScannerHome = tool name: 'sonar', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
        }
        withSonarQubeEnv('sonar') {
          sh "${sonarqubeScannerHome}/bin/sonar-scanner -e -Dsonar.host.url=http://18.234.237.49:9000 -Dsonar.login=0f72c8ee54f1bd2e552c2aa7a9ef3097fcf9b913 -Dsonar.projectName=sonar-test -Dsonar.projectVersion=1.0 -Dsonar.projectKey=GS -Dsonar.sources=test/  "
     
           }
        }
      }
  
    }
}
