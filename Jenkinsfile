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
	kubernetes {
	  cloud "kubernetes"
	  // label "dockerbuild-${UUID.randomUUID().toString()[0..10]}"
	   defaultContainer "docker-build1"
	   inheritFrom "jnlp"
	  yamlFile "build-pod.yaml"
    	   } // kubernetes
	
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
