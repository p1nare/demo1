pipeline {
  agent none

  stages {
    stage("Test back end") {
      agent {
                docker { image 'maven:3.8.1-adoptopenjdk-11' }
            
}
       
      steps {
        sh "echo hostname"
      }

    }
}

}
