pipeline {
  agent {
        label 'AGENT-1'
  }

    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }

    environment {
      def appVersion = ''
        nexusUrl = 'nexus.surisetty.online:8081'
    }
    parameters {

        string(name: 'appVersion', defaultValue: '1.0.0', description: 'what is the application version?')
  
    }

    stages {
    stage('Print the version') {
      steps {
        script {
          echo "Application version : ${params.appVersion}"
        }
      }
    }
    }
      post {
        always {
      echo 'I will always say hello again'
      deleteDir()
        }
        success {
      echo 'I will say hello only when success'
        }
        failure {
      echo 'I will say hello only when failure'
        }
      }
}
