pipeline{
	agent{label 'master'}
	stages{
		stage('Checkout!'){
			steps{
				git branch: 'master', url: 'https://github.com/jewdas1984/Media99.git'
			}
		}
   		stage('invoke playbook'){
			steps{
				ansiblePlaybook credentialsId: 'default_cisco', installation: 'ansible', inventory: './tests/inventory/inventory', playbook: './tests/ansible-vpn.yml'	}
   		}
	}
}