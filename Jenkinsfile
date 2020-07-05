
pipeline
{
  agent any
  stages
  {
    stage ('scm checkout')
    {
      steps{
        git branch:'master', url: 'https://github.com/prasaddahiwadkar/maven-project'
      }
      
    }
    
         stage('please compile code')
       { steps {
           withMaven(jdk: 'locakjdk-1.8', maven: 'localmaven') {
            sh 'mvn compile'
}
    
  }
  
}
