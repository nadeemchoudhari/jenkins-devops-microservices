pipeline {
	agent any
	stages { 
	   stage('Build') {
	     steps {	
		echo "Build"
	     }
	   }
	   stage('Test') {
	      steps {
		echo "Test"
	      }
	   }

	   stage('Integration Test') {
              steps { 
		echo "Test"
              }
	   }
 
        } post {
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
