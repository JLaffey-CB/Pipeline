pipeline {
  agent any
  stages {
    stage('stageone') {
      environment {
        localvar = 'onlysstageone'
      }
      steps {
        echo 'Hi!  I\'m stage one'
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
      agent {
        node {
          label 'node1'
        }
        
      }
      steps {
        echo 'We\'re limiting this to a specific node because we can'
      }
    }
  }
  environment {
    Global = 'IBeEverywhere'
  }
}