pipeline {
  agent any
  tools {
        maven 'Maven 3.6.3'
        jdk 'jdk1.8'
    }
  stages {
    stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }
    stage('pull') {
               steps {
            git(url: 'https://github.com/vargantianuradha/flyhighproject.git', branch: 'master')
          }
        }

        stage('build') {
          steps {
            echo 'inside build'
             sh 'mvn -Dmaven.test.failure.ignore=true install'
          }
        }
  }
  environment {
    stage = 'build'
  }
}
