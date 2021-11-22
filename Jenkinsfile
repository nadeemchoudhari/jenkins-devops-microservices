
pipeline {
        agent any 

	environment {
		dockerHome = tool 'mydocker'
		mavenHome = tool 'mymaven'
		PATH="$dockerhome/bin:$mavenhome/bin:$PATH"
	stages { 
	   stage('Build') {
	     steps {

		sh 'mvn --version'
		sh 'docker --version'
                			
		echo "Build"
		echo "$PATH"
		echo "BUILD_NUMBER - $env.BUILD_NUMBER"
		echo "BUILD_ID - $env.BUILD_ID"
		echo "JOB_NAME - $env.JOB_NAME"
		echo "BUILD_TAG - $env.BUILD_TAG"
		echo "BUILD_URL - $env.BUILD_URL"
	     }
	   }
	   stage('Test') {
	      steps {
		echo "Test"
	      }
	   }

	   stage('Integration Test') {
              steps { 
	 	echo " TEst"
              }
	   }

	   stage('unknown test') {
              steps {
                 echo " Its happening " 
              }
           }	
 
        } 
        post {
	   always { 
		echo ' I run always ' 
	   }

	   success {
		echo ' I run when you success ' 
           }

           failure {

                echo ' I run when you fail ' 
           }
        } 
 }



