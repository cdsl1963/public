pipeline {
  agent any
  stages {
    stage('stage 1') {
       steps {
         echo 'running stage 1'
         if (env.enable_rerun) {
           echo 'could rerun'
         }
       }
    }
  }
}
