pipeline {
  agent any
  environment {
    GLOBAL_VAR = 'Global'
    SECRET_VAR = credentials('id')
  }
  stages {
    stage('Stage 1') {
      parallel {
        stage('Stage 1') {
            steps {
                withCredentials([usernameColonPassword(credentialsId: 'id', variable: 'id')]) {
                // some block
            }
            sh 'echo "Stage 1 (From VisualStudioCode)"'
            sh 'echo $GLOBAL_VAR'
          }
        }

        stage('Stage 1-2') {
          steps {
            sh 'echo "Stage 1-2-3"'
          }
        }

      }
    }

    stage('Stage 2') {
      steps {
        sh 'pwd'
        sh 'df'
        sh 'ls -la'
        sh 'touch 123.txt'
        sh 'ls -la'
      }
    }

    stage('Stage 3') {
      environment {
        VAR = '123'
      }
      steps {
        sh 'echo "Stage 3 (edited) $VAR --$test"'
        sh 'ls -la'
      }
    }
  }

}