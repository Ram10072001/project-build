pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False' // Disable SSH host key checking to avoid issues during automation
    }

    stages {
        stage('Checkout Code') {
            steps {
                // Clone the repository using Jenkins credentials
                git credentialsId: 'your-jenkins-credentials-id',  // Use the credentials you have set up in Jenkins for accessing the Git repository
                    branch: 'master',
                    url: 'https://github.com/Ram10072001/project-build.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                // Run the Ansible playbook using the host.txt inventory file and playbook.yml
                sh '''
                    ansible-playbook -i host.txt playbook.yml
                '''
            }
        }
    }
}

