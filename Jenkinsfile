@Library('pipeline-library-demo')_
def my_ref_method(String name = 'human') {
  echo "Hello, ${name}."
  echo "Hello, ${name}."
}
node('maven-label') {
   def mvnHome
   stage('Preparation') { 
      
    git branch: '$branch_name', credentialsId: '3a73c489-e460-4d8b-8cb3-aa6eb5e2d2ad', url: 'https://github.com/anwarmah/testnew.git/'
                 
      mvnHome = tool 'maven-3.5.4'
   }
   stage('Build') {
      
      withEnv(["MVN_HOME=$mvnHome"]) {
         if (isUnix()) {
            sh '"$MVN_HOME/bin/mvn" -Dmaven.test.failure.ignore clean package'
         } else {
            bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean package/)
         }
      }
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archiveArtifacts 'target/*.jar'
   }
   stage('my-ref-meth'){
     my_ref_method "Intellipath"
   }
  stage('my-shared-lib'){
     sayHello "devopsi-"
   }
      
}
