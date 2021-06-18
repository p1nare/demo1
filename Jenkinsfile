pipeline {
  agent {
	docker{
		image "narepavan/pavannew:v2"
}
}

  stages {
    stage("Test back end") {
      
      steps {
        sh "python setup.py"
      }

    }
}

}
