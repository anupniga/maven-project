pipeline
{
 agent any
 stages{
   stage('scm checkout')
   {
    steps{
	  git branch: 'master', url: 'https://github.com/anupniga/maven-project'
	}
   }
   stage('validate code')
   {
   steps{
     withMaven(maven: 'localmaven')
	 {
	  sh 'mvn validate'
	 }
   }
   }
   stage('compile code')
   {
   steps{
    sh 'mvn compile'
   }
   }
   stage('clean the package code')
   {
   steps{
    sh 'mvn clean package'
   }
   }
 }
}
