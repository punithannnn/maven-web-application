pipeline{
 agent any
 
 // for timestamp and  discard old builds we use options 
 options{
  timestamp()
  builddiscarder(logRotator(numToKeepStr: '2'))
 }
 
 // user defined variable 
 environment{
  name="punitha"
 }
 
 stages{
  stage("message")
  {
   steps{
    echo "hello world! "
    echo "buid number : $BUILD_NUMBER is triggered by user : $name"
   }
  }
 }
}
