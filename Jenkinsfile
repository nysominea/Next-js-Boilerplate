pipeline {
  agent {
    kubernetes {
      yaml """
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: nodejs
    image: node:18-alpine
    command:
    - cat
    tty: true
"""
    }
  }

  stages {
    stage('Install') {
      steps {
        container('nodejs') {
          sh 'npm install'
        }
      }
    }
  }
}
