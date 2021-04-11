pipeline {
  agent any
  stages {
    stage('stage 1') {
      steps {
          step([
          $class: 'GitHubSetCommitStatusBuilder',
          contextSource: [
            $class: 'ManuallyEnteredCommitContextSource',
            context: 'continuous-integration/jenkins/branch'
          ],
          statusMessage: [ content: 'Pipeline started' ]
        ])
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
// comment 3
