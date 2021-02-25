pipeline {
  agent any
  tools {
        maven 'M2_HOME 3.6.3'
        jdk 'JAVA_HOME'
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
  }
}
