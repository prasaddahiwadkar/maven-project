
pipeline

{

agent any

stages{  

stage ('scm checkout')

{ 

steps {
git branch: 'master', url: 'https://github.com/prasaddahiwadkar/maven-project'

} 


}
  
  stage ('Please Compile My Code')
  { steps { 
    withMaven(jdk: 'localjdk', maven: 'localmaven') {
    sh 'mvn compile'
}
  
  
  }
  
  }
  
    stage ('Please Test My Code')
  { steps { 
    withMaven(jdk: 'localjdk', maven: 'localmaven') {
    sh 'mvn test'
}
  
  
  }
  
  }
  
  stage ('Please Package My Code')
  steps {
  withMaven(jdk: 'localjdk', maven: 'localmaven')
    { sh 'mvn package'}
 }

}

}
