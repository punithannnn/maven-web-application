pipeline {
              agent any
                    options{
                                   timestamps()
                                   buildDiscarder(logRotator(numToKeepStr: '1')
                            }
                      tools{
                       maven 'maven-3.8.1'
                      }
                       post{
                       cleanup{
                                  echo "wipe out"
                               }
                            }
                         environment{
                            name="punitha"
                           }
                          triggers{
                                   cron('* * * * *') 
                                  /*pollSCM('* * * * *') */
                                } 
                         stages{
                                       stage("message")
                           {
                                  parallel
                                {
                                     stage("job1")
                                    {
                                           steps{
                                                   echo "hello world! "
                                                   echo "buid number : $BUILD_NUMBER is triggered by user : $name"  
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
                                     stage('cleanws)
                               {
                                 steps{
                                         dir('build_one')
                                         {
                                                script{
                                                                 currentBuild.displayName="JenkinsJob"
                                                                 sh "echo build name changing > hello.txt"
                                                }
                                         }
                                 }
                               }
                                          }
                                      }
             }
                            
                                     
   
 
 
