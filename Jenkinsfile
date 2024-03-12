pipeline {

  agent {
    node { label 'workstation' }
  }

  environment {
    NEWRELIC_API_KEY = credentials('ssh_connection')
    SAMPLE_URL = "google.com"
  }

  stages {

    stage('Foo') {
      steps {
        echo "this is a username- $NEWRELIC_API_KEY_USR"
        echo "this is a centos password- $NEWRELIC_API_KEY_PSW"
      }
    }

    stage('Bar') {
      steps {
        echo 'Hello world'
      }
    }

  }

  post {
    always {
      echo 'I will always say Hello again!'
    }
  }

}