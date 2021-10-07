pipeline {
              agent any
                    options{
                                   timestamps()
                                   buildDiscarder(logRotator(numToKeepStr: '1'))
                            }
                      tools{
                       maven 'maven-3.8.1'
                      }
                       post{
                       cleanup{
                                  echo "wipe out"
                               }
                         success{
                           archiveArtifacts artifacts:"pip/target/*.war"
                                }
                            }
                         environment{
                            name="punitha"
                           }
                          triggers{
                                   cron('* */5 * * *') 
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
                                                   sh 'mvn --version'
                                                   sh "ls -l"
                                                   git url :"https://github.com/punithannnn/maven-web-application.git"
                                                   sh "mvn clean install"   
                                                  
                                           }
                                    }
                                  
                                     stage('cleanws')
                                    {
                                      steps{
                                               dir('build_one')
                                              {
                                                script{
                                                                 currentBuild.displayName="JenkinsJob"
                                                                 sh "echo build name changing > hello.txt"
                                                                 sh "cat hello.txt"
                                                       }
                                               }
                                           }
                                      }
                                   stage('userInput')
                                  {
                                                  input{
                                                           message "press ok"
                                                           submitter "puni, lead"
                                                            parameters{
                                                                       string(name: 'user', description: "only puni")
                                                                      }
                                                  }
                                                   steps{
                                                    echo "user: ${user} said ok"                   
                                                   }
                                    } 
                                  }
                              }
                        }
                }
                            
                                     
   
 
 
