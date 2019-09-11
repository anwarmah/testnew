node('maven-label') {
  stage('clone') {
    git branch: '$branch_name', credentialsId: '3a73c489-e460-4d8b-8cb3-aa6eb5e2d2ad', url: 'https://github.com/anwarmah/testnew.git/'
  }
  stage('mvn-install') {
    sh label: '', script: 'mvn clean install'
  }
  stage('3') {
    echo 'Hello World'
  }
  stage('4') {
    echo 'Hello World'
  }
}
