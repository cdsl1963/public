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
          sh 'ls not_there'
        }
	sleep 240
      }
    }
  }
}
// comment 6
