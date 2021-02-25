pipeline {
  agent any
  stages {
    stage('pull') {
      parallel {
        stage('pull') {
          steps {
            git(url: 'https://github.com/vargantianuradha/flyhighproject.git', branch: 'master')
          }
        }

        stage('build') {
          steps {
            echo 'inside build'
          }
        }

      }
    }

    stage('build') {
      steps {
        sh 'mvn clean install'
        sh './build.sh'
      }
    }

  }
  environment {
    stage = 'build'
  }
}