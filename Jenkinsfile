pipeline {
    agent{
        kubernetes {
            yaml """
apiVersion: v1
kind: Pod
metadata:
        labels:
          l: "skd"
        name: test-ebs
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
      image: pavan123456788/demo1:latest
      command:
        - cat
      tty: true
  volumes:
     - hostPath:
        path: /var/run/docker.sock
       name: docker-sock
    """
    }
    }
    environment { 
        user = "${name}"
    }

stages {
    stage("Build") {
      steps {
        container("docker-build") {
            sh """
            echo $hostname
            """
            {
            script {

              sh """
              docker login -u "pavan123456788" -p "Pavan@1234" "https://hub.docker.com/repository/docker/pavan123456788/demo1"
              docker build --tag pavan123456788/demo1:v8 .
              docker push ${tag}
            """
            }
            }
          
        }
        
          
      }
        
    }
      stage("demo1") {
        steps{
            script{
            try {
        container("docker-build1") {
            sh """
            python3 /root/r.py $user
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
      }
      stage("demo2") {
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
    }
}
}
