pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git credentialsId: 'your-jenkins-credentials-id',
                    branch: 'master',
                    url: 'https://github.com/Ram10072001/project-build.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                sh '''
                    ansible-playbook -i host.txt install playbook.yml
                '''
            }
        }
    }
}

