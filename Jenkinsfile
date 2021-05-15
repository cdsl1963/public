pipeline {
  agent any
  stages {
    stage('stage 1') {
      steps {
        script {
          code = load 'libs/lib.groovy'
          code.example2()
          echo 'running stage 1'
          //sh 'ls not_there'
          echo env.BRANCH_NAME
          if (env.BRANCH_NAME == "develop") {
       	    sleep 240
          }
        }
      }
    }
  }
}
// comment 6
