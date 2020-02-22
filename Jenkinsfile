pipeline {
 agent any
 stages {
  stage('SCM checkout') {
   steps {
    git branch: 'master', url: 'https://github.com/anupniga/maven-project'
   }
  }
  stage('sonar and maven package') {
   steps{
   withSonarQubeEnv(credentialsId: 'sonar') {
      withMaven(maven:'localmaven') {
	    sh 'clean mvn install sonar:sonar'
	  }
   }
   }
  }
}
}
