pipeline {
    
    agent any
    
    stages {

	    
        stage('Deploy-SCP') {
           steps {
		   
		      echo "deploying on scp"
			  scm checkout
			  
			  pushToCloudFoundry(
              target: 'https://api.cf.eu10.hana.ondemand.com',
              organization: 'P2001960486trial_trial',
              cloudSpace: 'dev',
              credentialsId: 'cf-scp',
			  manifestChoice: [manifestFile: 'manifest.yml']
              )
            }
        }
       
        
    }
    
}