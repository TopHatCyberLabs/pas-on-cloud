pipeline {
  agent {
    node {
      label 'ansible'
    }

  }
  stages {
    stage('Syntax Validation') {
      steps {
        s3Upload(bucket: 'jenkins-temp-poc', file: 'aws/Vault-Single-Deployment.json', acl: 'PublicRead')
        cfnValidate(url: 'https://s3.eu-west-2.amazonaws.com/jenkins-temp-poc/Vault-Single-Deployment.json')
      }
    }
  }
}