
pipeline {
        agent any 

	environment {
		dockerHome = tool 'mydocker'
		mavenHome = tool 'mymaven'
		PATH="$dockerHome/bin:$mavenHome/bin:$PATH"
	}	
	stages { 
	   stage('Build') {
	     steps {
		echo "Build"
		echo "$PATH"
		sh 'mvn --version'
		sh 'docker --version'
		
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



