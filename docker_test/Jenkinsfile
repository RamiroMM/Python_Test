pipeline {
  agent any
  stages {
    stage('Initialize'){
      steps{
        echo 'Executing commands...'
        sh 'python3 test.py'
      }
      post {
        success {
          echo 'Now Archiving the artifacts...'
          archiveArtifacts artifacts: '**/*.html'
        }
      }
    }
    stage('Create Tomcat Docker Image'){
      steps {
        sh "docker build . -t tomcatsamplewebapp:${env.BUILD_ID}"
      }
    }
  }
}
