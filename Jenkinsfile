
pipeline {
        agent { docker { image 'node:13.8' } }
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
		sh '''
                    #!/bin/bash
		    node --version
		'''
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



