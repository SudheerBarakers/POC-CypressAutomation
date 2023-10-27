pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Assuming you're using Git for version control
                git branch: 'main', url: 'https://github.com/SudheerBarakers/POC-CypressAutomation.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Install npm dependencies
                    bat 'npm install'
                }
            }
        }

        stage('Run Cypress Tests') {
            parallel {
                stage('Spec1') {
                    steps {
                        script {
                            bat "npx cypress run --spec cypress/integration/examples/Test1.js"
                        }
                    }
                }
                stage('Spec2') {
                    steps {
                        script {
                            bat "npx cypress run --spec cypress/integration/examples/Test2.js"
                        }
                    }
                }
            }
        }
    }

 }
