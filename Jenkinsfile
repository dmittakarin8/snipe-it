pipeline {
  agent any
  stages {
    stage('scan') {
      steps {
        catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
          sh "docker run -v ${WORKSPACE}:/src --workdir /src returntocorp/semgrep semgrep ci --config auto --json --output FISMAID12345-Snipe.json"
        }
      }
    }
    stage('Move Output') {
      steps {
        sh 'mv FISMAID12345-Snipe.json /bitnami/jenkins/home/workspace/semgrep_output/'
      }
    }
  }
}
