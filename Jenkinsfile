pipeline
{
agent any
stages { 
     
      stage ('scm checkout')
      {
          steps{

                git branch: 'master', url: 'https://github.com/prasaddahiwadkar/maven-project'

          }

      }
     
     stage ('compile code')
     { steps {
            withMaven(jdk: 'localjdk', maven: 'localmaven') {
            sh 'mvn compile'
           }  
     }
      }
     
    stage ('test code')
      { 
          steps {withMaven (jdk: 'localjdk', maven: 'localmaven')
          {sh 'mvn test'}
          
          }
      }

      stage ('build code')
      {
          steps {withMaven (jdk: 'localjdk', maven: 'localmaven')
          {sh 'mvn package'}
          }
      }
     
     stage ('deploy to tomcat server')
{
steps
{

sshagent(['7d178bf8-1fbc-4353-b377-cf573b50d066']) {
     sh 'scp -o StrictHostKeyChecking=no */target/webapp.war ec2-user@172.31.55.171:/var/lib/tomcat/webapps'
}
}
}
     
  }


}
