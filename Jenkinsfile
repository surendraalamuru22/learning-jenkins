pipeline {

   agent any

   environment {
         USER_NAME = "john"
         USER_ID = 32
   }

   stages {
      stage('list env variables') {
         steps {
             sh 'env'
         }
      }
      stage('access env variable') {
          environment {
              USER_PATH = "/tmp/sample"
          }
          steps {
            echo "BUILD_NUMBER = ${env.BUILD_NUMBER}"
            sh 'echo BUILD_NUMBER = $BUILD_NUMBER'

            echo "user name is ${env.USER_NAME}"
            echo "user id is ${env.USER_ID}"
            echo "user path is ${env.USER_PATH}"

            script {
               env.USER_GROUP = "users"
            }
            sh 'echo current user group is $USER_GROUP'

            withEnv(["USER_PWD=secret", "USER_ID_ADMIN=false"]) {
                 echo "current user password is ${env.USER_PWD}"
                 sh 'echo current user is admin? $USER_ID_ADMIN'
            }

          }

      }


   }

}