pipeline {
  agent {
	docker{
		image "narepavan/pavannew:v3"
}
}

  stages {
    stage("Test back end") {
      
      steps {
        sh "python /tmp/setup.py"
      }

    }
}

}
