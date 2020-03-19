pipeline {
    
	parameters {
        string(name: 'organisation', defaultValue: 'CLOVE', description: 'org name to deploy app')
		string(name: 'space', defaultValue: 'development', description: 'space name')
		}
	
    agent {label "master"}
    
    stages {

	
        stage('Deploy-PCF') {
           steps {
		      echo "deploying on pcf"
			  
			  cleanWs()
			  checkout scm

		  
			  withCredentials([usernamePassword(credentialsId: 'pcf_zia', passwordVariable: 'cfPassword', usernameVariable: 'cfUser')])
			    {
				    sh '''
                     cf login -a 'https://api.run.pivotal.io' -u ${cfUser} -p ${cfPassword} -o $organisation -s $space
					 #cf delete -r ui5HelloWorld -f
					 cf push
					'''
				}

             }
        }
       
        
    }
    
}
