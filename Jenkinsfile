pipeline {
    agent {
        label 'ansible'
    }
    stages {
        stage('Checkout git') {
            steps{
              git branch: 'main', credentialsId: 'adf43e57-f21e-41a4-b472-ec5275436c83', url: 'git@github.com:iv-art074/elastic_template.git'
            }
        }
        stage('Install molecule') {
            steps{
                sh 'pip3 install -r test-requirements.txt'
                }
        }
        stage('Run Molecule'){
            steps{
                sh 'molecule test'
            }
        }
    }
}