pipeline{
 agent any
 
 // for timestamp and  discard old builds we use options 
 options{
  timestamps()
  buildDiscarder(logRotator(numToKeepStr: '10'))
 }
 
 // user defined variable 
 environment{
  name="punitha"
 }
 
 //trigger build we use triggers cron or poll scm 
 triggers{
  /*cron('* * * * *')*/
  pollSCM('* * * * *')
 }
 
 
 stages{
  stage("message")
  {
   steps{
    echo "hello world! "
    echo "buid number : $BUILD_NUMBER is triggered by user : $name"
   }
  
  
  stage("cron")
  {
   steps {
    echo "build triggers"
    git url :"https://github.com/punithannnn/maven-web-application.git"
   }
 }
  }
}
}
