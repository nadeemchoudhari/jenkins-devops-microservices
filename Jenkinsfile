
pipeline {
        agent any 

	environment {
		dockerHome = tool 'mydocker'
		mavenHome = tool 'mymaven'
		PATH="$dockerHome/bin:$mavenHome/bin:$PATH"
	}	
	stages { 
	   stage('Checkout') {
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
	   stage('Compile') {
	      steps {
		
		sh 'mvn clean compile'
	      }
	   }

	   stage('Test') {
              steps { 
	 	sh 'mvn test'
              }
	   }

	   stage('Integration test') {
              steps {
                 sh 'mvn failsafe:integration-test failsafe:verify'
              }
           }	

	   stage('Package'){
		steps {
			sh 'mvn package -DskipTests'
		}
	   }
		
           stage('Build Docker Image') {
		steps {
		   // 'docker build -t nach1116/currency-exchange-devops:$env.BUILD_TAG'
		   script {
			dockerImage = docker.build("nach1116/currency-exchange-devops:${env.BUILD_TAG}")
		   }
		
		}
           }
	   stage('Push Docker Image'){
		steps {
			script {
				docker.withRegistry('','dockerhub') {
					dockerImage.push();
					dockerImage.push('latest');
				}
			}       
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



