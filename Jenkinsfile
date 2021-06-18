pipeline {
    agent {
        docker{
        cloud "docker"
        label "demo-slave1"
        }
    }
    stages {
        stage('Back-end') {
            sh"echo hostname"
        }
            
    }
}
