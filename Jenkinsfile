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
        step([
          $class: 'GitHubCommitStatusSetter',
          errorHandlers: [[$class: "ChangingBuildStatusErrorHandler", result: "UNSTABLE"]],
          contextSource: [
            $class: 'ManuallyEnteredCommitContextSource',
            context: 'continuous-integration/jenkins/branch'
          ],
          statusResultSource: [
            $class: 'ConditionalStatusResultSource',
            results: [
              [$class: 'AnyBuildResult', message: 'Pipeline result', state: currentBuild.getResult()]
            ]
          ]
        ])
      }
    }
  }
}
// comment 5
