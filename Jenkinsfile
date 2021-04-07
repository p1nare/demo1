pipeline {
  agent {
    kubernetes {
      cloud "kubernetes1"
      defaultContainer "docker-build"
      //inheritFrom "jnlp"
      yamlFile "build-pod.yaml"
    }
  }
  stages {
    stage('Setup parameters') {
            steps {
                script { 
                    properties([
                        parameters([
                          string( 
                                name: 'user', 
                                trim: true
                            )
                        ])
                    ])
                }
            }
    }
    
    stage("demo2") {
        steps{
            script{
            try {
        container("docker-build1") {
            sh """
            python3 /tmp/r.py $user
            cat file.txt
            """
            }
            env.a='True'
            }
            catch (Exception e) {
            echo 'Something failed, I should sound the klaxons!'
            env.a='False'
            
            }
        }
      }
    }//stage
    
    stage("demo5") {
          when {
              expression { "${a}" == 'True' }
          }
        steps{
        container("docker-build1") {
            sh """
            echo $hostname
            cat file.txt
            """
            
        }
      }
    }//stage
    
    
  }
}
