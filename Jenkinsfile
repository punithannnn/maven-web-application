pipeline{
 agent any
 // user defined variable 
 environment{
  name="punitha"
 }
 
 stages{
  stage("message")
  {
   steps{
    echo "hello world! "
    echo "buid number : $BUILD_NUMBER $name"
   }
  }
 }
}
