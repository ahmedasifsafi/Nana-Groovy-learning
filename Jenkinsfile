def gv
pipeline{
    agent any
     parameters {
	choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
	booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }						
    stages{
        stage ("init"){
             steps {
		 script {
		      gv = load "script.groovy"
			}
                echo "building the application"
            }
            
        }

	stage ("build"){
             steps {
                echo "building the application"
            }
            
        }
        stage ("test"){
	when {
	        expression {
			params.executeTests
	}
	    }
             steps {
                echo "testing the application "
            }
            
        }
        stage ("Deploy"){
             steps {
                echo "Deploying the application"
	   echo "Deploying the version ${params.VERSION}"
            }        
        }
    }
}
