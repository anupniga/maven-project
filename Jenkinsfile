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
   stage('genearate the war file using package')
   {
   steps{
    sh 'mvn clean package'
   }
   }
   stage('archive the artifacts')
   {
    steps{
	 archiveArtifacts '**/*.war'
	}
   }
 }
}
