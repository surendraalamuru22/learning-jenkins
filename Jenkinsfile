pipeline {
  agent { label 'workstation' }
    environment {
        NEWRELIC_API_KEY = credentials('ansible')
    }
    stages {
        stage('Foo') {
            steps {
              echo 'Hello world'
            }
        }
    }
}
