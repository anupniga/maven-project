pipeline {
 agent any
 stages {
  stage('SCM checkout') {
   steps {
	   withCredentials([usernamePassword(credentialsId: 'githublocal', passwordVariable: 'pass', usernameVariable: 'user')]) {
    

    git branch: 'master', url: 'https://github.com/anupniga/maven-project'
   }
  }
  }
  stage('sonar and maven package') {
   steps{
   withSonarQubeEnv('sonar') {
      withMaven(maven:'localmaven') {
	    sh 'mvn package sonar:sonar'
	  }
   }
   }
  }
}
}
