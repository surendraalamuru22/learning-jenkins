pipeline {
    agent any
    environment {
        NEWRELIC_API_KEY = credentials('ansible1')
    }
    stages {
        stage('Foo') {
            steps {
              echo 'Hello world'
            }
        }
    }
}