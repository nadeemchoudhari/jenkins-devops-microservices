pipeline {
        agent { 
           docker { 
               image 'maven:3-alpine' 
           } 
        }
	stages { 
	   stage('Build') {
	     steps {	
		sh 'mvn --version'
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
