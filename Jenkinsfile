pipeline {
    agent{
        kubernetes {
            label "dockerbuild-${UUID.randomUUID().toString()[0..10]}"
            defaultContainer "docker-build"
            inheritFrom "jnlp"
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

stages {
    stage("Build") {
      steps {
        container("docker-build") {
            sh """
            echo $hostname
            echo "GIT_BRANCH=${env.GIT_BRANCH}" >> /etc/environment
             echo "GIT_COMMIT=${env.GIT_COMMIT}" >> /etc/environment
              //docker login -username pavan123456788 -password Pavan@1234 
              //docker build --tag pavan123456788/demo1:v8 .
              //docker push ${tag}
            """
            }
      }
        
    }
}
}
