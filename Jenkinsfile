pipeline {
  agent any
  stages {
    stage('scan') {
      steps {
        sh "docker run -v ${WORKSPACE}:/src --workdir /src returntocorp/semgrep semgrep ci --config auto --json --output snipe-it-findings.json"
        sh "mv snipe-it-findings.json /bitnami/jenkins/home/workspace/semgrep_output/"
      }
    }
  }
}
