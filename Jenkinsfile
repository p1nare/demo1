pipeline {
  agent {
	docker{
		image "narepavan/pavannew"
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
