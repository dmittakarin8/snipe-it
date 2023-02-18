pipeline {
  agent any
  stages {
    stage('scan') {
      steps {
        sh "docker run -v ${WORKSPACE}:/src --workdir /src returntocorp/semgrep semgrep ci --config auto --json --output snipe-it-findings.json"
      }
    }
  }
}
