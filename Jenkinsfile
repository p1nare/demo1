pipeline {
  agent {
	docker{
		image "narepavan/pavannew:v2"
}
}

  stages {
    stage("Test back end") {
      
      steps {
        sh "sudo python /root/setup.py"
      }

    }
}

}
