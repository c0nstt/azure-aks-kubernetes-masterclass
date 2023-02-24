pipeline {
  agent any
  stages {
    stage('Stage 1') {
      parallel {
        stage('Stage 1') {
          steps {
            sh 'echo "Stage 1 (From VisualStudioCode)"'
            sh 'echo $GLOBAL_VAR'
            sh 'echo $SECRET_VAR'
            sh 'echo $SECRET_VAR_PSW'
          }
        }

        stage('Stage 1-2') {
          steps {
            sh 'echo "Stage 1-2-3"'
            sh 'env | sort'
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
        sh 'echo "$SECRET_VAR"'
        sh 'echo "$SECRET_VAR_PSW"'
      }
    }

  }
  environment {
    GLOBAL_VAR = 'Global'
    GLOBAL_RANDOM_VAR = sh(returnStdout:true,script:'openssl rand -base64 19' ).trim()
    SECRET_VAR = credentials('id')
  }
}