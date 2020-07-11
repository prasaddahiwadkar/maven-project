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
  }


}
