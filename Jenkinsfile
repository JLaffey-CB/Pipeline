pipeline {
  agent any
  stages {
    stage('stageone') {
      environment {
        localvar = 'onlysstageone'
      }
      steps {
        echo 'Hi!  I am stage one'
      }
    }
    stage('stagetwo') {
      steps {
        sleep 5
        timeout(time: 6) {
          sh 'ls'
        }

      }
      post {
        always {
        echo 'This is stage two'
        }
        changed {
        echo 'There was a different completion status than the last run'
        }
      }
    }
    stage('stagethree') {
      agent {
        node {
          label 'CentOSAgent'
        }

      }
      steps {
        echo 'We can limit this to a specific node for just this step'
        sh 'ls'
        sh 'ls > listing.txt'
        sh 'ls'

      }


    }


/*    stage('SCM') {
    git 'https://github.com/foo/bar.git'
  }
    stage('SonarQube analysis') {
      withSonarQubeEnv('My SonarQube Server') {
      sh './gradlew --info sonarqube'
    }
  }
*/

}
  post {
    always {
    echo 'The pipeline was started so this will always print'
    }
    success {
    echo 'The pipeline ran successfully'
    }
    failure {
    echo 'Something went wrong and the run failed'
    }

  }

  environment {
    Global = 'IBeEverywhere'
  }

}
