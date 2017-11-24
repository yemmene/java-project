pipeline {
    agent any
    stage('Test'){
      git 'https://github.com/yemmene/java-project.git'
      sh 'ant -f test.xml -v'
      
}
   stage('Build') {
     sh 'ant -f build.xml -v'
}
stage('Deploy'){
   cp 	jenkins-stack-s3bucket-1gawjlmyalaas.s3.amazonaws.com
}

stage('Results'){
    junit'reports/result.xml'
