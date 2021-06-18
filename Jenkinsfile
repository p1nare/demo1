pipeline {
  agent none

  stages {
    stage("Test back end") {
      agent {
        
    docker {
        dockerfile true
        label 'docker'
    }
}
        

      steps {
        sh "echo hostname"
      }

    }
}

}
