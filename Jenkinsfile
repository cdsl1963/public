pipeline {
  agent any
  stages {
    stage('init') {
      steps {
        step([
          $class: 'GitHubCommitStatusSetter',
          reposSource: [$class: 'ManuallyEnteredRepositorySource', url: 'https://github.com/cdsl1963/public'],
          contextSource: [
            $class: 'ManuallyEnteredCommitContextSource',
            context: 'continuous-integration/jenkins/branch'
          ],
          statusMessage: [ content: 'Pipeline startedeeee' ]
        ])
      }
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
        }
	sleep 240
      }
    }
  }
}
// comment 6
