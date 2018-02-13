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
    }
    stage('stagethree') {
      agent any
      steps {
        echo 'We could limit this to a specific node for just this step'
      }
    }
  }
  environment {
    Global = 'IBeEverywhere'
  }
}