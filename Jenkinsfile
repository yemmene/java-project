properties([pipelineTriggers([githubPush()])])

node('linux') {
  stage('Test'){
      git 'https://github.com/yemmene/java-project.git'
      sh 'ant -f test.xml -v'    
}
  stage('Build') {
     sh 'ant -f build.xml -v'
}
  stage('Results'){
    junit'reports/result.xml'
}
 stage('Deploy'){
   

withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'cd21c5ec-bf34-4742-b7d3-157aab504759', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
    // sh 'aws --region us-east-1 ssm start-automation-execution \
    --document-name rectangle-2.jar \
    --parameters \
        "sourceAMIid='{{ssm:latestAmi}}'" 
} 

}
   
