String registryUrl = "asidjklds"
String registryNamespace = "platformasddas"
String buildContainerName = "devops-python-joba"
String buildImageName = "ayusdhxz"
String buildMemoryLimit = "1024Mi"
String buildRequestsLimit = "256Mi"
String buildLabelNamespace = "platforma"
String buildLabelType = "job"
String registryCredentialId = "buildpipeline-acr-credaslk"
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
