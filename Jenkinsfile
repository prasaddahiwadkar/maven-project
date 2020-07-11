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
     
     stage ('complile code')
      steps {
            withMaven(jdk: 'localjdk', maven: 'localmaven') {
            sh 'mvn complile'
           }  

      }
     
  }

}
