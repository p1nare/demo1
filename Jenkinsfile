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
          sh '$hostname'
        }
        container('busybox') {
          sh '/bin/busybox'
        }
      }
    }
  }
}
