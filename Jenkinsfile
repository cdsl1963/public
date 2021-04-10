pipeline {
  agent any
  stages {
    stage('stage 1') {
      steps {
        script {
          echo 'running stage 1'
          echo "could rerun ${env.enable_rerun}"
          if (env.enable_rerun == "true") {
             echo 'nearly'
	     build job: env.BRANCH_NAME, wait: false
          }
        }
      }
    }
  }
}
// comment 2
