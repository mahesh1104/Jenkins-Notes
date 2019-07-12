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


