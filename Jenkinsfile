pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('steps-from-blue-ocean') {
      parallel {
        stage('steps-from-blue-ocean') {
          steps {
            sh '''echo "hello world"
ls -ltra
pwd'''
            echo 'hello wold from print message!!!!'
          }
        }

        stage('run parallel with above steps') {
          steps {
            sh 'echo this is running from step2'
          }
        }

      }
    }

    stage('run after step 1') {
      steps {
        sh 'echo run after setp1!!!!!!!!!!!!!!!!'
      }
    }

    stage('final1') {
      parallel {
        stage('final1') {
          steps {
            sh 'echo final'
          }
        }

        stage('after final1') {
          steps {
            sh 'echo run after final1'
          }
        }

      }
    }

  }
  environment {
    project_name = 'pipeline-poc'
    sample = 'true'
  }
}