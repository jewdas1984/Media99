pipeline{
	agent{label 'master'}
	stages{
		stage('Checkout!'){
			steps{
				git branch: 'master', url: 'https://github.com/jewdas1984/Media99.git'
			}
		}
    	stage('Setup!'){
      		steps{
				sh 'chmod +x install.sh'
        		sh './install.sh'
      			}
    		}
   		stage('invoke playbook'){
			steps{
				ansiblePlaybook credentialsId: 'default_cisco', installation: 'ansible', inventory: '/etc/ansible/hosts', playbook: './tests/ansible.yml'	}
   		}
	}
}