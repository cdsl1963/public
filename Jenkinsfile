pipeline {
  agent any
  stages {
    stage('Load') {
      code = load 'lib/lib.groovy'
    }
    stage('Execute') {
      code.example1()
    }
    stage('stage 1') {
      steps {
        script {
          echo 'running stage 1'
          echo "could rerun ${env.enable_rerun}"
          if (env.enable_rerun == "true") {
             echo 'nearly'
          }
          //sh 'ls not_there'
          echo $(env.BRANCH_NAME)
          if (env.BRANCH_NAME == "develop") {
       	    sleep 240
          }
        }
      }
    }
  }
}
// comment 6
