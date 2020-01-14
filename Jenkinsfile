pipeline {
    
    agent any
    
    stages {

	
        stage('Deploy-SCP') {
           steps {
		      echo "deploying on scp"
			  
			  cleanWs()
			  checkout scm

		  
			  withCredentials([usernamePassword(credentialsId: 'CF-devsecops20', passwordVariable: 'cfPassword', usernameVariable: 'cfUser')])
			    {
				    sh '''
                     cf login -a 'https://api.cf.eu10.hana.ondemand.com' -u ${cfUser} -p ${cfPassword} -o P2001960486trial_trial -s qa
					 cf push
					'''
				}

             }
        }
       
        
    }
    
}
