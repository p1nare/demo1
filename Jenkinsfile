pipeline {
  agent none

  stages {
    stage("Test back end") {
      agent {
        dockerfile {
          filename "Dockerfile"
          label "webapps"
        }
      }

      steps {
        sh "echo hostname"
      }

    }
}

}
