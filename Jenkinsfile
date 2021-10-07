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
  cron('* * * * *')
 }
  stages{
       stage("message")
   {
          steps{
                  echo "hello world! "
                  echo "buid number : $BUILD_NUMBER is triggered by user : $name"
                  echo "build triggers"  
               }
  }
 }
}
