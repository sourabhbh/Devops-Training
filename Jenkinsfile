pipeline {
    agent any
	    tools {
		   maven 'MAVEN_HOME'
		   jdk 'JDK10'
		}
		
   stages{
      stage('Checkout')
	  {
	      checkout(checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'ce16a624-66e7-4960-beed-ff651f954740', url: 'https://github.com/sourabhbh/Devops-Training.git']]]))
	  }
	  stage('Static Code Analysis')
	  {
	      echo "Static Code Analysis"
	  }
	  stage('Initialize')
	  {
	      steps {
		      sh '''
			     echo "PATH = $(PATH)"
			     echo "M2_HOME = $(M2_HOME)"
			  '''
		  }
	  }
	  stage('Build'){
	     steps {
		     sh 'mvn -Dmaven.test.failure.ignore=true install'
	     }
		 post{
		    success{
			   junit 'target/surfire-reports/**/*.xml'
			}
		 }
	  stage('Unit Testing')
	  {
	      echo ""
	  }
	  stage('Deployment')
	  {
	      echo ""
	  }
   }
}
}