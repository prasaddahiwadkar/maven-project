
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
  {steps {
  withMaven(jdk: 'localjdk', maven: 'localmaven')
    { sh 'mvn package'}
 }

}

}
  
  {stage ('Deploy To Tomcat')
  { steps { 
    sshagent(['fa94cbcd-db05-4fdf-beb6-c4ffaed2476c']) {
    sh 'scp -o StrictHostKeyChecking=no */target/webapp.war ec2-user@172.31.26.172: /var/lib/tomcat/webapps'
}
}
  
  
  }
  
  }

}
