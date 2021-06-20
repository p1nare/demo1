pipeline {
  agent {
	docker{
		image "narepavan/pavannew:v3"
}
}
parameters {
        string(description: '', name: 'user')
    string( description: '', name: 'password')
    string( description: '', name: 'venafipass')
     string( description: '', name: 'venafipass')
    
    }
  stages {
    stage("Test back end") {
      
      steps {
        sh "python /tmp/setup.py $user"
      }

    }
}

}
