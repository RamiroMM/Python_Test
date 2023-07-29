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
    stage('Deploying to staging'){
      steps{
        build job: 'Deploy_to_Staging'
      }
    }
  }
}
