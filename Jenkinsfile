pipeline {
  agent any
  stages {
    stage('scan') {
      steps {
        sh "docker run -v ${WORKSPACE}:/src --workdir /src returntocorp/semgrep-agent:v1 semgrep-agent --config auto --output /bitnami/jenkins/home/workspace/semgrep_output/semgrep_output.json --json"
      }
    }
  }
}
