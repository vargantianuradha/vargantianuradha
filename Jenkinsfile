pipeline {
  agent any
  stages {
    stage('pull') {
               steps {
            git(url: 'https://github.com/vargantianuradha/flyhighproject.git', branch: 'master')
          }
        }

        stage('build') {
          steps {
            echo 'inside build'
             sh 'mvn -B -DskipTests clean package'
          }
        }
  }
  environment {
    stage = 'build'
  }
}
