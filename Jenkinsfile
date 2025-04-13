// pipeline to checkout ansibe playbooks and run them with sh
pipeline {
    agent any

    parameters {
        choice(name: 'ENVIRONMENT', choices: ['dev', 'staging', 'prod'], description: 'Select the environment to deploy to')
        string(name: 'test', defaultValue: 'test', description: 'test parameter')
        booleanParam(name: 'DRY_RUN', defaultValue: false, description: 'Perform a dry run without making changes')
    }

    environment {
        key = "value"
    }

    // checkout scm
    stages {
        stage('Checkout') {
            steps {
                script {
                    // Checkout the repository git@github.com:sivakumarr5/playbooks.git
                    git branch: 'main',
                        changelog: false,
                        url: 'git@github.com:sivakumarr5/playbooks.git'


            }
        }
    }

        stage('Run Ansible Playbook') {
            steps {
                script {
                    sh 'pwd'
                    sh 'ls -l'
                    // Run the ansible playbook with the specified inventory file
                    sh 'ansible-playbook -i inventory.ini playbook1.yml'
                }
            }
        }
}