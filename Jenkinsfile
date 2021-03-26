pipeline {
  agent {
    kubernetes {
      yaml """\
        apiVersion: v1
        kind: Pod
        metadata:
          labels:
            some-label: some-label-value
        spec:
          containers:
          - name: docker-build
            image: docker
            command:
            - cat
            tty: true
            volumeMounts:
               - mountPath: /var/run/docker.sock
                 name: docker-sock
          - name: docker-build1
            image: pavan123456788/demo1:v7
            command:
             - cat
            tty: true
            volumeMounts:
               - mountPath: /var/run/docker.sock
                 name: docker-sock
          volumes:
           - hostPath:
               path: /var/run/docker.sock
             name: docker-sock
        """.stripIndent()
    }
  }
  stages {
    stage('demo1') {
      steps {
        container('docker-build') {
          sh """
            echo $hostname
            """
          
         script {

              sh """
              docker login --username pavan123456788 --password Pavan@1234 
              docker build --tag pavan123456788/demo1:latest .
              docker push pavan123456788/demo1:latest
            """
            }
          
        }
       
      }
    }//stage
    
    stage("demo2") {
        steps{
            script{
            try {
        container("docker-build1") {
            sh """
            python3 /root/r.py $user
            """
            }
            env.a='False'
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
            """
            
        }
      }
    }//stage
    
    
  }
}
