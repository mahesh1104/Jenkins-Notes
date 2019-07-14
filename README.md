# Jenkins-Notes

How to Parameterize job's in jenkins 

java -jar jenkins.war => default it start's with 8080 port
java -jar jenkins.war --httpPort=9191 => for different port

Start Jenkins
Create a new freestyle job
Parametrize job
syntax
 windows - %parametername%
 linux/mac - $parametername
             ${parametername}
             "${parametername}"
            
string parameter
choice parameter            

how to run a job from command line
how to run a job from command line with user authentication
(with username and password)
how to show progress/results on commandline

java -jar jenkins-cli.jar -s http://localhost:8080/ build samplejob -s -v
java -jar jenkins-cli.jar -s http://localhost:8080/ build samplejob -s --username=admin --password=admin

How to run parametrized job from command line

java -jar jenkins-cli.jar -s http://localhost:8080/ build samplejob --username=admin --password=admin -s -v -p MESSAGE=hello

--> How to create parameters with checkboxes, radio buttons, dropdown

          Extended Choise Parameter -plugin
             Basic parameter types-> check box, radio buttion
             choose source for value --> value , a,b,c,d,e
             execute shell --> command --> echo $automation 
             

Poll mailbox trigger plugin


Jenkins Tips:-
1) Dont Use Maven Project- They Drastically reduces the configuration.
   and also they have reduced the flexiability . When ever Maven project fails
   pritty hard to reproduce locally . it really diffrernt what happend in jenkins and 
   and what happen in maven locally . Go with Pipelines
   
2) How to set up jenkinsfile - the standard way to step is jenkinsfile should be there
   in you are resposity 
          pipeline {
             agent any
             stages {
                stage('Hello World') {
                    steps {
                     sh 'echo Hello World'
                     }
                   }
                 }
               }
 
 10) Jobs: Pipeline:
             Do work on agents....
             
 12) Jobs: Pipeline:
             Stages are groups of steps
             
             stages {
                 stage('Build') {...}
                 stage('Test')   {...}
                 stage('Deploy') {...}
                 stage('perf test') {...}
                 stage('Acc') {...}
                 stage('prod') {...}
              }
             
  13) Jobs: Pipeline:
             Don't mess with Environment variables
             $env -- dont change, since it is set a globally
             
             use like this
             
             withEnv (["HELLO=world"]) {
                 sh "echo HELLO"
               }
                  or
                  
              pipeline {
                  agent any
                  environment {
                      HELLO = 'world'
                  }
                  
                  stages {
                     ...
                  }
               }
               
     14) Jobs: Pipeline: Parameters are an option
           
           pipeline {
              agent any
              parameters {
                 string(description: 'foo', name: 'bar')
           }
           environment {
              baz = params.bar
           }
           When you run a build it will check for parameters -make sure use perfetly 
           
     15) Jobs: Pipeline: Parallelism
     
           
                  
                 
                

