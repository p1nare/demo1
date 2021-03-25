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
          - name: maven
            image: docker
            command:
            - cat
            tty: true
          - name: busybox
            image: busybox
            command:
            - cat
            tty: true
        """.stripIndent()
    }
  }
  stages {
    stage('Run maven') {
      steps {
        container('maven') {
          sh """
            echo $hostname
            """
          
         script {

              sh """
              docker login -username pavan123456788 -password Pavan@1234
              docker build --tag pavan123456788/demo1:v8 .
              docker push pavan123456788/demo1:v8
            """
            }
          
        }
        container('busybox') {
          sh '/bin/busybox'
        }
      }
    }
  }
}
