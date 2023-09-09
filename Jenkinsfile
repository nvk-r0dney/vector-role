pipeline {
    agent {
        label 'linux'
    }
    
    stages {
        stage('Prepare to test Vector Role') {
            steps {
                sh 'rm -rf /home/cloud-user/vector_role'
                sh 'pip3 install molecule molecule_docker molecule_podman'
            }
        }
        stage('Clone Vectore Role from Git Repo') {
            steps {
                sh 'mkdir -p /home/cloud-user/vector_role'
                sh 'git clone https://github.com/nvk-r0dney/vector-role.git /home/cloud-user/vector_role'
            }
        }
        stage('Run Molecule Test') {
            steps {
                sh 'cd /home/cloud-user/vector_role && molecule converge'
            }
        }
    }
}