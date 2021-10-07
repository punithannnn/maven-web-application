pipeline{
 agent any
 // for timestamp and  discard old builds we use options
 options{
  timestamps()
  buildDiscarder(logRotator(numToKeepStr: '10'))
 }
 //to run specific version of tools we use tools block 
 tools{
  maven 'Maven3.6.1'
 }
 //to wipeout workspace 
 post{
       cleanup{
                echo "wipe out"
              }
     }
 // user defined variable 
 environment{
  name="punitha"
 }
 //trigger build we use triggers cron or poll scm 
 triggers{
  cron('* * * * *') 
  /* pollSCM('* * * * *') */
 }
stages{
    stage("message")
   {
    //parallel will trigger the build parallely 
      parallel
     {
     
         stage("job1")
          {
                   steps{
                          echo "hello world! "
                          echo "buid number : $BUILD_NUMBER is triggered by user : $name"
                          echo "build triggers"  
                        }
            }
      
      stage("job2")
          {
                   steps{
                          echo "hello world 2 "
                          sh "echo this is punitha" 
                          sh "ls -l"
                        }
            }
      stage("tool_version")
            {
              steps{
                    sh 'mvn --version'
                   }
            }
      
      
      
       }
  }
 
  
 }
}
