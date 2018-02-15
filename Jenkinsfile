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
    stage('demoPipleline') {
      steps {
      demoPipeline {
          projectName = "Project1"
          serverDomain = "Project1 Server Domain"
      }
      }
    }
}

  environment {
    Global = 'IBeEverywhere'
  }
  @Library("demoPipeline") _
}
