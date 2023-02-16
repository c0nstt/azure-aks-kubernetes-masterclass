pipeline {
  agent any
  stages {
    stage('Stage 1') {
      parallel {
        stage('Stage 1') {
          steps {
            sh 'echo "Stage 1 (From VisualStudioCode)"'
          }
        }

        stage('Stage 1-2') {
          steps {
            sh 'echo "Stage 1-2"'
          }
        }

      }
    }

    stage('Stage 2') {
      steps {
        sh 'echo "Stage 2"'
      }
    }

    stage('Stage 3') {
      environment {
        VAR = '123'
        username = ''
      }
      steps {
        sh '''echo "Stage 3 (edited) $VAR --$username"


'''
      }
    }

  }
}