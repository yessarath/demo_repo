pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
		git branch: 'develop', changelog: false, credentialsId: 'jenkins_for_aws_infra_mgmt', poll: false, url: 'git@github.com:yessarath/demo_repo.git'            }
        }
        stage('deploy') {
            steps {
		sh '''ansible-playbook -i /etc/ansible/inventory/hosts.ini ansible/webserver.yml -e "hosts=dev"'''
            }
        }
    }
}

