properties([pipelineTriggers([githubPush()])])

node('linux') {
  stage('Test'){
      git 'https://github.com/yemmene/java-project.git'
      sh 'ant -f test.xml -v'
      
}
}
   
