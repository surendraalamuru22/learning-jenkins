pipeline {

   agent any

   environment {
         USER_NAME = "john"
         USER_ID = 32
   }

   stages {
      stage('list env variables') {
         environment {
            USER_ID = 42
         }
         steps {
             sh 'env'
             echo "now the user id is ${USER_ID}"
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
               env.USER_NAME = "joe"
            }
            sh 'echo current user group is $USER_GROUP'
            echo "user name after overriding is ${USER_NAME}"

            withEnv(["USER_PWD=secret", "USER_ID_ADMIN=false", "USER_NAME=bob"]) {
                 echo "current user password is ${env.USER_PWD}"
                 sh 'echo current user is admin? $USER_ID_ADMIN'
                 echo "user name after overriding in Env block ${USER_NAME}"
            }

          }

      }


   }

}