pipeline {
  agent any
  options {
        timeout(time: 1, unit: 'HOURS')
        ansiColor('xterm')
    }
  parameters {
    gitParameter branchFilter: 'origin/(.*)', defaultValue: 'master', name: 'BRANCH', type: 'PT_BRANCH'
  }
  stages {
    stage('Build') {
      steps {
        git branch: "${params.BRANCH}", url: 'https://github.com/katacoda/golang-http-server.git'
        sh 'make build'
      }
    }
  }
}