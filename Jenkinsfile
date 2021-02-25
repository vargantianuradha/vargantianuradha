pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
      }
    }

    stage('Build') {
      post {
        success {
          echo 'build finished sucessfully'
        }

      }
      steps {
        sh 'mvn -Dmaven.test.failure.ignore=true install'
      }
    }

    stage('ArchiveArtifacts') {
      steps {
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
        archiveArtifacts(artifacts: 'target/flyhighwebapp.war', fingerprint: true)
      }
    }

  }
  tools {
    maven 'M2_HOME'
    jdk 'JAVA_HOME'
  }
}